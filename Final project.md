# Um-Ramongleng-Final-project-
#include <iostream>
using namespace std;

class sortDataClass {

private:

    int* data;
    int dataSize, maxNum;

public:
    void randomize() {
        for (int i = 0; i < dataSize; i++)
            data[i] = rand() % maxNum;
    }

    sortDataClass(int n, string dataset, int m) {
        dataSize = n;
        maxNum = m;

        data = new int[dataSize];
        if (dataset == "inorder")
            for (int i = 0; i < dataSize; i++) data[i] = i;
        else if (dataset == "reverseorder")
            for (int i = 0; i < dataSize; i++) data[i] = maxNum - i - 1;
        else if (dataset == "random")
            randomize();
        else
            cout << "Error";
    }

    void printData() {
        for (int i = 0; i < dataSize; i++)
            cout << data[i] << endl;
    }
};

int main() 
{
    
    int Data = 15;
    int TopNum = 100;

    cout << "\nIn-order sorted data:" <<endl;
    sortDataClass inorder(Data, "inorder", TopNum);
    inorder.printData();

    cout << "\nReverse-order:" <<endl;
    sortDataClass reverse(Data, "reverseorder", TopNum);
    reverse.printData();

    cout << "\nRandom number such as:" <<endl;
    sortDataClass random(Data, "random", TopNum);
    random.printData();
    return 0;
}
