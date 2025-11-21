## Practice Questions

Q..... Using 2d array print maatrix along with
-> Matrix Addition
-> Matrix Substraction
-> Matrix Multiplication

```cpp
#include <iostream>
using namespace std;
#define ROW_MAX 5
#define COL_MAX 5

void addMatrix();
void readMatrix(int A[][COL_MAX], int r, int c, string name);

int Arr1[ROW_MAX][COL_MAX], Arr2[ROW_MAX][COL_MAX], Result[ROW_MAX][COL_MAX];
int row1, col1, row2, col2, i, j;

int main(){

    cout << "Enter size of Matrix 1 (rows and columns): ";
    cin >> row1 >> col1;
    readMatrix(Arr1, row1, col1, "Matrix 1");

    cout << "\nEnter size of Matrix 2 (rows and columns): ";
    cin >> row2 >> col2;
    readMatrix(Arr2, row2, col2, "Matrix 2");

    addMatrix();


}

void readMatrix(int A[][COL_MAX], int r, int c, string name){

    cout << "Enter the elements for " << name << "\n";

    for(i=0; i<r; i++){
        for(j=0; j<c; j++){
            cin >> A[i][j];
        }
    }

    cout << "\n" << name << "\n";
    for(i=0; i<r; i++){
        for(j=0; j<c; j++){
            cout << A[i][j] << " ";
        }
        cout << "\n";
    }

}

void addMatrix() {

    if(row1 == row2 && col1 == col2){

        cout << "\nResult (Matrix Addition): \n";

        for(i=0; i<row1; i++){
            for(int j=0; j<col1; j++){
                    Result[i][j] = Arr1[i][j] + Arr2[i][j];
                    cout << Result[i][j] << " ";
            }
            cout << "\n";
        }

    }
    else {
        cout << "\nMatrix addition NOT possible!";
        cout << "\nCondition failed: row1 < row2 AND col1 < col2\n";
    }

}
```



