#include <iostream>
using namespace std;

class Stack {
private:
    int top;        // Tracks the top element of the stack
    int* arr;       // Pointer for dynamically allocated array
    int maxSize;    // Maximum size of the stack

public:
    // Constructor to initialize the stack with a dynamic array
    Stack(int size) {
        top = -1;  // Stack is initially empty
        maxSize = size;  // Set the maximum size of the stack
        arr = new int[maxSize];  // Dynamically allocate memory for the stack array
    }

    // Destructor to free dynamically allocated memory
    ~Stack() {
        delete[] arr;  // Free the allocated memory when the stack is destroyed
    }

    // Push function to add an element to the stack
    void push(int value) {
        if (top == maxSize - 1) {
            cout << "Stack Overflow! Cannot push " << value << endl;
        } else {
            arr[++top] = value; // Increment top and assign value
            cout << "Pushed " << value << " onto the stack." << endl;
        }
    }

    // Pop function to remove and return the top element of the stack
    int pop() {
        if (top == -1) {
            cout << "Stack Underflow! Cannot pop." << endl;
            return -1;  // Indicates the stack is empty
        } else {
            cout << "Popped " << arr[top] << " from the stack." << endl;
            return arr[top--]; // Return the current top element, then decrement top
        }
    }

    // Peek function to view the top element without removing it
    int peek() {
        if (top == -1) {
            cout << "Stack is empty." << endl;
            return -1;
        } else {
            return arr[top];
        }
    }

    // Function to check if the stack is empty
    bool isEmpty() {
        if (top == -1) {
            cout << "Stack is empty." << endl;
            return true; // Returns true if stack is empty
        } else {
            cout << "Stack is not empty." << endl;
            return false; // Returns false if stack has elements
        }
    }

    // Function to return the size of the stack
    int size() {
        return top + 1; // Return the number of elements in the stack
    }

    // Function to display all elements in the stack
    void display() {
        if (top == -1) {
            cout << "Stack is empty. Nothing to display." << endl;
        } else {
            // Display the top element first
            cout << "Top element: " << arr[top] << endl;

            // Then display the other elements from bottom to top
            cout << "Stack elements (from bottom to top): ";
            for (int i = 0; i <= top; i++) {
                cout << arr[i] << " ";
            }
            cout << endl;
        }
    }

    // Function to get the element from a specified position
    int elementFromPos(int pos) {
        if (pos < 1 || top - pos + 1 < 0) { // Check if the position is valid
            cout << "Invalid position." << endl;
            return -1; // Indicates an invalid position
        } else {
            return arr[top - pos + 1]; // Return the element at the specified position
        }
    }
};

int main() {
    int n, choice, value, pos;

    // Take the stack size from the user
    cout << "Enter the size of the stack: ";
    cin >> n;

    Stack myStack(n);  // Create a stack with dynamic size

    do {
        // Display the menu of operations
        cout << "\nChoose an operation:\n";
        cout << "1. Push\n";
        cout << "2. Pop\n";
        cout << "3. Peek\n";
        cout << "4. Check if empty\n";
        cout << "5. Check stack size\n";
        cout << "6. Display stack\n";
        cout << "7. Display element from position\n";
        cout << "8. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                // Push operation
                cout << "Enter value to push: ";
                cin >> value;
                myStack.push(value);
                break;

            case 2:
                // Pop operation
                myStack.pop();
                break;

            case 3:
                // Peek operation
                cout << "Top of stack: " << myStack.peek() << endl;
                break;

            case 4:
                // Check if the stack is empty
                myStack.isEmpty();
                break;

            case 5:
                // Get the current size of the stack
                cout << "Current stack size: " << myStack.size() << endl;
                break;

            case 6:
                // Display the stack
                myStack.display();
                break;

            case 7:
                // Display the element from position
                cout << "Enter the position of the element to be displayed (1-indexed): ";
                cin >> pos;
                value = myStack.elementFromPos(pos); // Call the function to get the element
                if (value != -1) { // Only print if a valid element was returned
                    cout << "Element at position " << pos << ": " << value << endl;
                }
                break;

            case 8:
                // Exit
                cout << "Exiting..." << endl;
                break;

            default:
                cout << "Invalid choice! Please try again." << endl;
        }
    } while (choice != 8);  // Loop until user chooses to exit

    return 0;
}
