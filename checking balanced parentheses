#include <iostream>
#include <stack> // Include the stack header
using namespace std;

class ExpressionChecker {
    char* expression; // Pointer to store the expression

public:
    // Constructor to allocate memory for the expression
    ExpressionChecker() {
        expression = new char[100]; // Assuming maximum expression length of 100
    }

    // Destructor to free the allocated memory
    ~ExpressionChecker() {
        delete[] expression; // Free the memory
    }

    // Method to get the expression from the user
    void getExpression() {
        cout << "Enter expression: ";
        cin >> expression; // Read the expression
    }

    // Method to check for balanced parentheses
    void checkBalanced() {
        stack<char> s; // Create an inbuilt stack to hold parentheses

        for (int i = 0; expression[i] != '\0'; i++) { // Iterate until the end of the string
            if (expression[i] == '(') {
                s.push('('); // Push '(' onto the stack
            } else if (expression[i] == ')') {
                if (s.empty()) { // If the stack is empty
                    cout << "Unbalanced parentheses." << endl;
                    return; // Exit if unbalanced
                } else {
                    s.pop(); // Pop the matching '('
                }
            }
        }
        // Check if the stack is empty after processing the expression
        if (s.empty()) {
            cout << "Balanced parentheses." << endl;
        } else {
            cout << "Unbalanced parentheses." << endl;
        }
    }
};

int main() {
    ExpressionChecker checker; // Create an instance of ExpressionChecker
    checker.getExpression(); // Get the expression from the user
    checker.checkBalanced(); // Check if the parentheses are balanced
    return 0;
}
