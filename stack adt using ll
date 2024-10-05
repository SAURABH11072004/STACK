#include <iostream>
using namespace std;

// Node structure for linked list
class Node {
public:
    int data;      // Data stored in the node
    Node* next;    // Pointer to the next node

    Node(int value) {
        data = value; // Initialize node data
        next = nullptr; // Initialize next pointer to nullptr
    }
};

// Stack class using linked list
class Stack {
private:
    Node* top; // Pointer to the top node of the stack

public:
    // Constructor to initialize the stack
    Stack() {
        top = nullptr; // Stack is initially empty
    }

    // Destructor to free all nodes in the stack
    ~Stack() {
        while (top) { // While there are nodes in the stack
            Node* temp = top; // Store the current top node
            top = top->next; // Move the top pointer to the next node
            delete temp; // Free the memory of the old top node
        }
    }

    // Push function to add an element to the stack
    void push(int value) {
        Node* newNode = new Node(value); // Create a new node
        newNode->next = top; // Link the new node to the previous top
        top = newNode; // Update top to the new node
        cout << "Pushed " << value << " onto the stack." << endl;
    }

    // Pop function to remove and return the top element of the stack
    int pop() {
        if (top == nullptr) { // Check if the stack is empty
            cout << "Stack Underflow! Cannot pop." << endl;
            return -1; // Indicates the stack is empty
        } else {
            int poppedValue = top->data; // Get the value from the top node
            Node* temp = top; // Temporary pointer to hold the top node
            top = top->next; // Move top to the next node
            delete temp; // Free memory for the old top node
            cout << "Popped " << poppedValue << " from the stack." << endl;
            return poppedValue; // Return the popped value
        }
    }

    // Peek function to view the top element without removing it
    int peek() {
        if (top == nullptr) { // Check if the stack is empty
            cout << "Stack is empty." << endl;
            return -1;
        } else {
            return top->data; // Return the data of the top node
        }
    }

    // Function to check if the stack is empty
    bool isEmpty() {
        if (top == nullptr) { // Check if stack is empty
            cout << "The stack is currently empty." << endl;
            return true; // Return true if stack is empty
        } else {
            cout << "The stack is not empty." << endl;
            return false; // Return false if stack has elements
        }
    }

    // Function to return the size of the stack
    int size() {
        int count = 0;
        Node* temp = top; // Start from the top
        while (temp) {
            count++; // Count each node
            temp = temp->next; // Move to the next node
        }
        return count; // Return the total count
    }

    // Function to display all elements in the stack
    void display() {
        if (top == nullptr) { // Check if the stack is empty
            cout << "Stack is empty. Nothing to display." << endl;
        } else {
            cout << "Stack elements (from top to bottom): ";
            Node* temp = top; // Start from the top
            while (temp) {
                cout << temp->data << " "; // Print temp node's data
                temp = temp->next; // Move to the next node
            }
            cout << endl;
        }
    }

    // Function to get the element from a specified position
    int elementFromPos(int pos) {
        if (pos < 1) {
            cout << "Invalid position." << endl;
            return -1; // Indicates an invalid position
        }

        Node* current = top; // Start from the top
        for (int i = 1; i < pos && current; i++) {
            current = current->next; // Move to the next node
        }

        if (current) {
            return current->data; // Return the data at the specified position
        } else {
            cout << "Position out of bounds." << endl; // Position is out of bounds
            return -1; // Indicates an invalid position
        }
    }
};

int main() {
    Stack myStack;  // Create a stack

    int choice, value, pos, maxSize;

    // Get the maximum size of the stack from the user
    cout << "Enter the maximum size of the stack: ";
    cin >> maxSize;

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
                if (myStack.size() < maxSize) { // Check if the stack is full
                    cout << "Enter value to push onto the stack: ";
                    cin >> value; // Get value from user
                    myStack.push(value); // Push value onto the stack
                } else {
                    cout << "Stack is full! Cannot push more elements." << endl;
                }
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
                cout << "Enter the position of the element to be displayed. ";
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
