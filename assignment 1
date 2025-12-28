Q1. Data Type Operations & Precision Control
#include <iostream>
#include <iomanip> // for setprecision
using namespace std;

int main() {
    double num1, num2;

    cout << "Enter two floating-point numbers: ";
    cin >> num1 >> num2;

    cout << fixed << setprecision(3); // format to 3 decimal places

    cout << "Floating-point results:\n";
    cout << "Sum: " << num1 + num2 << "\n";
    cout << "Difference: " << num1 - num2 << "\n";
    cout << "Product: " << num1 * num2 << "\n";
    cout << "Quotient: " << num1 / num2 << "\n";

    // Cast to integers
    int n1 = static_cast<int>(num1);
    int n2 = static_cast<int>(num2);

    cout << "\nInteger results (after casting):\n";
    cout << "Sum: " << n1 + n2 << "\n";         // fractional part is removed
    cout << "Difference: " << n1 - n2 << "\n";  
    cout << "Product: " << n1 * n2 << "\n";
    cout << "Quotient: " << n1 / n2 << "\n";   // integer division truncates result

    return 0;
}

Q2. Conditional Logic Challenge – Grade Analyzer
#include <iostream>
#include <iomanip>
using namespace std;

int main() {
    int marks[5];
    int total = 0;
    
    cout << "Enter marks for 5 subjects: ";
    for(int i=0;i<5;i++) {
        cin >> marks[i];
        total += marks[i];
    }

    double percentage = total / 5.0;

    char grade;
    if(percentage >= 90) grade = 'A+';
    else if(percentage >= 80) grade = 'A';
    else if(percentage >= 70) grade = 'B';
    else if(percentage >= 60) grade = 'C';
    else if(percentage >= 50) grade = 'D';
    else grade = 'F';

    cout << "\nReport Card\n";
    cout << setw(10) << "Subject" << setw(10) << "Marks\n";
    for(int i=0;i<5;i++)
        cout << setw(10) << i+1 << setw(10) << marks[i] << "\n";

    cout << "Total Marks: " << total << "\n";
    cout << "Percentage: " << fixed << setprecision(2) << percentage << "%\n";
    cout << "Grade: " << grade << "\n";

    // Pass/Fail using ternary
    string status = (percentage >= 50) ? "Pass" : "Fail";
    cout << "Status: " << status << "\n";

    return 0;
}

Q3. Logical Flow with Conditions
#include <iostream>
using namespace std;

int main() {
    int a, b, c;
    cout << "Enter three integers: ";
    cin >> a >> b >> c;

    int largest, smallest;

    // Check largest
    if(a >= b && a >= c) largest = a;
    else if(b >= a && b >= c) largest = b;
    else largest = c;

    // Check smallest
    if(a <= b && a <= c) smallest = a;
    else if(b <= a && b <= c) smallest = b;
    else smallest = c;

    cout << "Largest number: " << largest << "\n";
    cout << "Smallest number: " << smallest << "\n";

    if(a == b && b == c)
        cout << "All numbers are equal.\n";
    else
        cout << "Numbers are not equal.\n";

    return 0;
}

Q4. Flowchart Implementation (Sum & Average of 5 Numbers)
#include <iostream>
using namespace std;

int main() {
    int sum = 0, count = 1, num;

    while(count <= 5) {
        cout << "Enter number " << count << ": ";
        cin >> num;
        sum += num;
        count++;
    }

    double average = sum / 5.0;

    cout << "Total sum: " << sum << "\n";
    cout << "Average: " << average << "\n";

    return 0;
}
