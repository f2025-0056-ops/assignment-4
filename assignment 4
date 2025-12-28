1) Weather Temperature Analyzer
#include <iostream>
using namespace std;

const int DAYS = 7;
const int TIMES = 4;

void inputTemperature(int temp[DAYS][TIMES]) {
    for (int i = 0; i < DAYS; i++) {
        cout << "Enter temperatures for day " << i + 1 << ":\n";
        for (int j = 0; j < TIMES; j++) {
            cin >> temp[i][j];
        }
    }
}

void highestLowest(int temp[DAYS][TIMES], int &high, int &low) {
    high = temp[0][0];
    low = temp[0][0];
    for (int i = 0; i < DAYS; i++) {
        for (int j = 0; j < TIMES; j++) {
            if (temp[i][j] > high) high = temp[i][j];
            if (temp[i][j] < low) low = temp[i][j];
        }
    }
}

void averagePerDay(int temp[DAYS][TIMES], double avg[DAYS]) {
    for (int i = 0; i < DAYS; i++) {
        int sum = 0;
        for (int j = 0; j < TIMES; j++)
            sum += temp[i][j];
        avg[i] = sum / (double)TIMES;
    }
}

void displayTable(int temp[DAYS][TIMES], double avg[DAYS]) {
    cout << "\nDay\tT1\tT2\tT3\tT4\tAverage\n";
    for (int i = 0; i < DAYS; i++) {
        cout << i + 1 << "\t";
        for (int j = 0; j < TIMES; j++)
            cout << temp[i][j] << "\t";
        cout << avg[i] << "\n";
    }
}

int main() {
    int temp[DAYS][TIMES];
    double avg[DAYS];
    int high, low;

    inputTemperature(temp);
    highestLowest(temp, high, low);
    averagePerDay(temp, avg);
    displayTable(temp, avg);

    cout << "\nHighest Temperature: " << high;
    cout << "\nLowest Temperature: " << low;

    return 0;
}

2) Sales Tracking for a Store
#include <iostream>
using namespace std;

const int DAYS = 7;
const int PRODUCTS = 5;

void inputSales(int sales[PRODUCTS][DAYS]) {
    for (int i = 0; i < PRODUCTS; i++) {
        cout << "Enter sales for product " << i + 1 << ":\n";
        for (int j = 0; j < DAYS; j++) cin >> sales[i][j];
    }
}

void calculateRevenue(int sales[PRODUCTS][DAYS], int revenue[PRODUCTS]) {
    for (int i = 0; i < PRODUCTS; i++) {
        revenue[i] = 0;
        for (int j = 0; j < DAYS; j++)
            revenue[i] += sales[i][j];
    }
}

int findMaxProduct(int revenue[PRODUCTS]) {
    int maxIndex = 0;
    for (int i = 1; i < PRODUCTS; i++)
        if (revenue[i] > revenue[maxIndex]) maxIndex = i;
    return maxIndex;
}

int findBestDay(int sales[PRODUCTS][DAYS]) {
    int bestDay = 0, maxSum = 0;
    for (int j = 0; j < DAYS; j++) {
        int sum = 0;
        for (int i = 0; i < PRODUCTS; i++) sum += sales[i][j];
        if (sum > maxSum) { maxSum = sum; bestDay = j; }
    }
    return bestDay;
}

int main() {
    int sales[PRODUCTS][DAYS], revenue[PRODUCTS];

    inputSales(sales);
    calculateRevenue(sales, revenue);

    cout << "\nWeekly revenue per product:\n";
    for (int i = 0; i < PRODUCTS; i++) cout << "Product " << i+1 << ": " << revenue[i] << "\n";

    cout << "\nProduct with max revenue: Product " << findMaxProduct(revenue)+1;
    cout << "\nBest sales day: Day " << findBestDay(sales)+1;

    return 0;
}

3) Seating Allocation System
#include <iostream>
using namespace std;

const int ROWS = 10, COLS = 10;
int seats[ROWS][COLS] = {0};

void displaySeats() {
    cout << "Seat layout (0=empty, 1=reserved):\n";
    for (int i = 0; i < ROWS; i++) {
        for (int j = 0; j < COLS; j++)
            cout << seats[i][j] << " ";
        cout << "\n";
    }
}

void reserveSeat() {
    int r, c;
    cout << "Enter row and column to reserve (0-9): ";
    cin >> r >> c;
    if (seats[r][c] == 0) { seats[r][c] = 1; cout << "Reserved!\n"; }
    else cout << "Already reserved.\n";
}

void cancelSeat() {
    int r, c;
    cout << "Enter row and column to cancel (0-9): ";
    cin >> r >> c;
    if (seats[r][c] == 1) { seats[r][c] = 0; cout << "Cancelled!\n"; }
    else cout << "Seat is empty.\n";
}

void countRows() {
    int full = 0, partial = 0, empty = 0;
    for (int i = 0; i < ROWS; i++) {
        int sum = 0;
        for (int j = 0; j < COLS; j++) sum += seats[i][j];
        if (sum == COLS) full++;
        else if (sum == 0) empty++;
        else partial++;
    }
    cout << "Full rows: " << full << ", Partial: " << partial << ", Empty: " << empty << "\n";
}

int main() {
    int choice;
    do {
        cout << "\n1.Display Seats\n2.Reserve Seat\n3.Cancel Seat\n4.Count Rows\n5.Exit\nChoice: ";
        cin >> choice;
        switch(choice) {
            case 1: displaySeats(); break;
            case 2: reserveSeat(); break;
            case 3: cancelSeat(); break;
            case 4: countRows(); break;
        }
    } while(choice != 5);
    return 0;
}
4) Crossword Puzzle Validator
#include <iostream>
#include <string>
using namespace std;

const int ROWS = 5, COLS = 5; // Example size

void inputPuzzle(char grid[ROWS][COLS]) {
    cout << "Enter crossword grid (5x5):\n";
    for (int i = 0; i < ROWS; i++)
        for (int j = 0; j < COLS; j++)
            cin >> grid[i][j];
}

int countHorizontalWords(char grid[ROWS][COLS]) {
    int count = 0;
    for (int i = 0; i < ROWS; i++) {
        int len = 0;
        for (int j = 0; j < COLS; j++) {
            if (grid[i][j] != '.') len++;
            else { if (len >= 3) count++; len = 0; }
        }
        if (len >= 3) count++;
    }
    return count;
}

int countVerticalWords(char grid[ROWS][COLS]) {
    int count = 0;
    for (int j = 0; j < COLS; j++) {
        int len = 0;
        for (int i = 0; i < ROWS; i++) {
            if (grid[i][j] != '.') len++;
            else { if (len >= 3) count++; len = 0; }
        }
        if (len >= 3) count++;
    }
    return count;
}

string findLongestWord(char grid[ROWS][COLS]) {
    string longest = "";
    for (int i = 0; i < ROWS; i++) {
        string temp = "";
        for (int j = 0; j < COLS; j++) {
            if (grid[i][j] != '.') temp += grid[i][j];
            else { if (temp.length() > longest.length()) longest = temp; temp = ""; }
        }
        if (temp.length() > longest.length()) longest = temp;
    }
    for (int j = 0; j < COLS; j++) {
        string temp = "";
        for (int i = 0; i < ROWS; i++) {
            if (grid[i][j] != '.') temp += grid[i][j];
            else { if (temp.length() > longest.length()) longest = temp; temp = ""; }
        }
        if (temp.length() > longest.length()) longest = temp;
    }
    return longest;
}

int main() {
    char grid[ROWS][COLS];
    inputPuzzle(grid);
    cout << "Horizontal words: " << countHorizontalWords(grid) << "\n";
    cout << "Vertical words: " << countVerticalWords(grid) << "\n";
    cout << "Longest word: " << findLongestWord(grid) << "\n";
    return 0;
}

6) Sort a Matrix in All Way Increasing Order
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    int n;
    cout << "Enter matrix size: ";
    cin >> n;
    vector<int> v;
    int mat[n][n];

    cout << "Enter matrix elements:\n";
    for(int i=0;i<n;i++)
        for(int j=0;j<n;j++){
            cin >> mat[i][j];
            v.push_back(mat[i][j]);
        }

    sort(v.begin(), v.end());

    int idx = 0;
    for(int i=0;i<n;i++)
        for(int j=0;j<n;j++)
            mat[i][j] = v[idx++];

    cout << "Sorted matrix:\n";
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++)
            cout << mat[i][j] << " ";
        cout << "\n";
    }

    return 0;
}

7) Print Matrix in Snake Pattern
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter matrix size: ";
    cin >> n;
    int mat[n][n];

    cout << "Enter matrix elements:\n";
    for(int i=0;i<n;i++)
        for(int j=0;j<n;j++)
            cin >> mat[i][j];

    cout << "Snake pattern: ";
    for(int i=0;i<n;i++){
        if(i%2==0)
            for(int j=0;j<n;j++)
                cout << mat[i][j] << " ";
        else
            for(int j=n-1;j>=0;j--)
                cout << mat[i][j] << " ";
    }
    return 0;
}

8) Employee Tracker
#include <iostream>
#include <vector>
using namespace std;

struct Employee {
    string name;
    int age;
    vector<string> skills;
};

int main() {
    int n;
    cout << "Enter number of employees: ";
    cin >> n;
    vector<Employee> employees(n);

    for(int i=0;i<n;i++){
        cout << "Employee " << i+1 << " name: ";
        cin >> employees[i].name;
        cout << "Age: ";
        cin >> employees[i].age;
        int s;
        cout << "Number of skills: ";
        cin >> s;
        employees[i].skills.resize(s);
        for(int j=0;j<s;j++){
            cout << "Skill " << j+1 << ": ";
            cin >> employees[i].skills[j];
        }
    }

    cout << "\nEmployee Details:\n";
    for(auto &e : employees){
        cout << "Name: " << e.name << ", Age: " << e.age << ", Skills: ";
        for(auto &sk : e.skills) cout << sk << " ";
        cout << "\n";
    }

    return 0;
}

9) Course Enrollment System
#include <iostream>
#include <vector>
using namespace std;

struct Student {
    string name;
    string id;
};

struct Course {
    string name;
    string code;
    vector<Student> students;
};

int main() {
    int n;
    cout << "Enter number of courses: ";
    cin >> n;
    vector<Course> courses(n);

    for(int i=0;i<n;i++){
        cout << "Course " << i+1 << " name: ";
        cin >> courses[i].name;
        cout << "Code: ";
        cin >> courses[i].code;
        int m;
        cout << "Number of students: ";
        cin >> m;
        courses[i].students.resize(m);
        for(int j=0;j<m;j++){
            cout << "Student " << j+1 << " name: ";
            cin >> courses[i].students[j].name;
            cout << "ID: ";
            cin >> courses[i].students[j].id;
        }
    }

    cout << "\nCourses and Enrolled Students:\n";
    for(auto &c : courses){
        cout << "Course: " << c.name << " (" << c.code << ")\n";
        for(auto &s : c.students)
            cout << "- " << s.name << " (" << s.id << ")\n";
    }

    return 0;
}
