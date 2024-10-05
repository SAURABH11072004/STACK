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

    // Method to check if the opening and closing brackets match
    bool isMatchingPair(char open, char close) {
        if (open == '(' && close == ')') return true;
        if (open == '{' && close == '}') return true;
        if (open == '[' && close == ']') return true;
        return false;
    }

    // Method to check for balanced parentheses, square, and curly brackets
    void checkBalanced() {
        stack<char> s; // Create an inbuilt stack to hold brackets

        for (int i = 0; expression[i] != '\0'; i++) { // Iterate until the end of the string
            if (expression[i] == '(' || expression[i] == '{' || expression[i] == '[') {
                s.push(expression[i]); // Push opening brackets onto the stack
            } else if (expression[i] == ')' || expression[i] == '}' || expression[i] == ']') {
                if (s.empty()) { // If the stack is empty, the expression is unbalanced
                    cout << "Unbalanced brackets." << endl;
                    return; // Exit if unbalanced
                } else if (!isMatchingPair(s.top(), expression[i])) { // Check for matching pairs
                    cout << "Unbalanced brackets." << endl;
                    return;
                } else {
                    s.pop(); // Pop the matching opening bracket
                }
            }
        }

        // Check if the stack is empty after processing the expression
        if (s.empty()) {
            cout << "Balanced brackets." << endl;
        } else {
            cout << "Unbalanced brackets." << endl;
        }
    }
};

int main() {
    ExpressionChecker checker; // Create an instance of ExpressionChecker
    checker.getExpression(); // Get the expression from the user
    checker.checkBalanced(); // Check if the brackets are balanced
    return 0;
}
