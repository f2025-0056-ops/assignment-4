Q1) Cinema Seats Booking
#include <iostream>
using namespace std;

void displaySeats(char seats[][10], int R, int C) {
    cout << "\nSeat Layout (R = Reserved, F = Free):\n";
    for (int i = 0; i < R; i++) {
        for (int j = 0; j < C; j++) {
            cout << "(" << i+1 << "-" << j+1 << " " << seats[i][j] << ") ";
        }
        cout << "\n";
    }
}

void bookSeat(char seats[][10], int R, int C) {
    int row, col;
    cout << "Enter row and seat number to book: ";
    cin >> row >> col;
    if(row >= 1 && row <= R && col >= 1 && col <= C) {
        if(seats[row-1][col-1] == 'F') {
            seats[row-1][col-1] = 'R';
            cout << "Seat booked successfully!\n";
        } else {
            cout << "Seat already reserved!\n";
        }
    } else {
        cout << "Invalid seat!\n";
    }
}

int main() {
    int R, C;
    cout << "Enter number of rows and columns: ";
    cin >> R >> C;
    char seats[10][10];

    // Initialize all seats as Free
    for(int i=0; i<R; i++)
        for(int j=0; j<C; j++)
            seats[i][j] = 'F';

    char choice;
    do {
        displaySeats(seats, R, C);
        cout << "\nDo you want to book a seat? (y/n): ";
        cin >> choice;
        if(choice == 'y' || choice == 'Y') {
            bookSeat(seats, R, C);
        }
    } while(choice == 'y' || choice == 'Y');

    cout << "\nFinal Seat Layout:\n";
    displaySeats(seats, R, C);

    return 0;
}


Sample Output:

Enter number of rows and columns: 2 4

(1-1 F) (1-2 F) (1-3 F) (1-4 F) 
(2-1 F) (2-2 F) (2-3 F) (2-4 F) 

Do you want to book a seat? (y/n): y
Enter row and seat number to book: 1 1
Seat booked successfully!

(1-1 R) (1-2 F) (1-3 F) (1-4 F) 
(2-1 F) (2-2 F) (2-3 F) (2-4 F) 

Q2) Reverse Array Using Swap Method
#include <iostream>
using namespace std;

void reverseArray(int arr[], int size) {
    for(int i=0; i<size/2; i++) {
        swap(arr[i], arr[size-1-i]);
    }
}

void printArray(int arr[], int size) {
    for(int i=0; i<size; i++)
        cout << arr[i] << " ";
    cout << "\n";
}

int main() {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;
    int arr[50];

    cout << "Enter elements: ";
    for(int i=0; i<n; i++)
        cin >> arr[i];

    cout << "Original Array: ";
    printArray(arr, n);

    reverseArray(arr, n);

    cout << "Reversed Array: ";
    printArray(arr, n);

    return 0;
}


Sample Output:

Enter number of elements: 6
Enter elements: 3 2 4 1 4 6
Original Array: 3 2 4 1 4 6 
Reversed Array: 6 4 1 4 2 3 
