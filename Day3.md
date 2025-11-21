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

void transposeMatrix();
void mulltiplyMatrix();
void substractMatrix();
void addMatrix();
void readMatrix(int A[][COL_MAX], int r, int c, string name);

int Arr1[ROW_MAX][COL_MAX], Arr2[ROW_MAX][COL_MAX], Result[ROW_MAX][COL_MAX];
int row1, col1, row2, col2, i, j;

int main(){

    cout << "Enter size of Matrix 1 (rows and columns): \n";
    cin >> row1 >> col1;
    readMatrix(Arr1, row1, col1, "Matrix 1");

    cout << "\nEnter size of Matrix 2 (rows and columns): \n";
    cin >> row2 >> col2;
    readMatrix(Arr2, row2, col2, "Matrix 2");

    int choice;
    do {
        cout << "\n===== MATRIX MENU =====\n";
        cout << "1. Add Matrices\n";
        cout << "2. Subtract Matrices\n";
        cout << "3. Multiply Matrices\n";
        cout << "4. Transpose of Matrix\n";
        cout << "5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch(choice) {
            case 1: 
                addMatrix();
                break;

            case 2: 
                substractMatrix();
                break;
            case 3:
                mulltiplyMatrix();
                break;
            case 4:
                transposeMatrix();
                break;
            case 5:
                cout << "\nExiting program...\n";
                break;
            default: 
                cout << "\nInvalid choice! Please enter again.\n";
        }
    } while(choice != 5);


    return 0;
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
        cout << "\nCondition failed: row1 = row2 AND col1 = col2\n";
    }

}

void substractMatrix(){

    if(row1 == row2 && col1 == col2){

        cout << "\nResult (Matrix Substraction): \n";

        for(i=0; i<row1; i++){
            for(j=0; j<col1; j++){
                Result[i][j] = Arr1[i][j] - Arr2[i][j];
                cout << Result[i][j] << " ";
            }
            cout << "\n";
        }
    } else {
        cout << "\nMatrix substraction NOT possible!";
        cout << "\nCondition failed: row1 = row2 AND col1 = col2\n";
    }
}

void mulltiplyMatrix(){

    if(col1 == row2){

        cout << "\nResult (Matrix Multiplication): \n";

        for(i=0; i<row1; i++){
            for(j=0; j<col2; j++){
                Result[i][j] = 0;
                for(int k=0; k<col1; k++){
                    Result[i][j] += Arr1[i][k] * Arr2[k][j];
                }
                cout << Result[i][j] << " ";
            }
            cout << "\n";
        }
    } else {
        cout << "\nMatrix multiplication NOT possible!";
        cout << "\nCondition failed: col1 == row2\n";
    }
}

void transposeMatrix(){

    int mChoice;
    cout << "\nSelect Matrix to Transpose:\n";
    cout << "1. Matrix 1\n";
    cout << "2. Matrix 2\n";
    cout << "Enter your choice: ";
    cin >> mChoice;

    if(mChoice == 1){
        cout << "\nTranspose of Matrix 1:\n";
        for(i=0; i<col1; i++){
            for(j=0; j<row1; j++){
                cout << Arr1[j][i] << " ";
            }
            cout << "\n";
        }
    }

    else if(mChoice == 2){
        cout << "\nTranspose of Matrix 2:\n";
        for(i=0; i<col2; i++){
            for(j=0; j<row2; j++){
                cout << Arr2[j][i] << " ";
            }
            cout << "\n";
        }
    }

    else {
        cout << "\nInvalid Matrix Choice\n";
    }


}

```



