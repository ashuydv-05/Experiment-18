# Experiment-18
c plus plus and data structures experiment 18

Aim:- To study and implement stack operation

Software used:- VS code

Theory:-
A stack is a linear data structure that follows the Last In, First Out (LIFO) principle, meaning the last element inserted is the first one to be removed. It operates like a real-life stack (e.g., plates), where you can only add or remove items from the top.
Key Operations:
Push: Adds an element to the top of the stack. If the stack is full, it causes a stack overflow.
Pop: Removes the top element from the stack. If the stack is empty, it leads to a stack underflow.
Peek/Top: Returns the top element without removing it.
isEmpty: Checks if the stack is empty.
isFull: Checks if the stack is full (if a size limit exists).

Code:-
```
//Ashu Yadav
//23070123154

#include <iostream>
using namespace std;

class Stack 
{
private:
    int top;       
    int maxSize; 
    int* stackArray; 

public:

    Stack(int size) 
    {
        maxSize = size;              
        stackArray = new int[maxSize]; 
        top = -1;                    
    }

    ~Stack() {
        delete[] stackArray;
    }

   
    bool isEmpty() 
    {
        return top == -1;
    }

    bool isFull() 
    {
        return top == maxSize - 1;
    }

    void push(int value) 
    {
        if (isFull()) 
        {
            cout << "Stack Overflow! Unable to push " << value << endl;
            return; 
        }
        stackArray[++top] = value;
        cout << value << " pushed to stack." << endl;
    }

    int pop() 
    {
        if (isEmpty()) 
        {
            cout << "Stack Underflow! Unable to pop." << endl;
            return -1;
        }
        return stackArray[top--];
    }

    int peek() 
    {
        if (isEmpty()) 
        {
            cout << "Stack is empty. No top element." << endl;
            return -1;
        }
        return stackArray[top];
    }

    void display() 
    {
        if (isEmpty()) 
        {
            cout << "Stack is empty." << endl;
            return;
        }
        cout << "Stack elements: ";
        for (int i = top; i >= 0; i--) 
        {
            cout << stackArray[i] << " ";
        }
        cout << endl;
    }
};

int main() 
{
    int size, choice, value;

    cout << "Enter the size of the stack: ";
    cin >> size; 
    Stack stack(size);

    do 
    {
        cout << "\nMenu:\n";
        cout << "1. Push\n";
        cout << "2. Pop\n";
        cout << "3. Peek\n";
        cout << "4. Display\n";
        cout << "5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) 
        {
            case 1: 
                cout << "Enter value to push: ";
                cin >> value; 
                stack.push(value);
                break;
            case 2:
                value = stack.pop(); 
                if (value != -1)
                    cout << value << " popped from stack." << endl;
                break;
            case 3:
                value = stack.peek();
                if (value != -1)
                    cout << "Top element is: " << value << endl;
                break;
            case 4:
                stack.display();
                break;
            case 5:
                cout << "Exiting program." << endl;
                break;
            default:
                cout << "Invalid choice! Please try again." << endl;
        }
    } while (choice != 5);

    return 0;
}
```
![exp19](https://github.com/ashuydv-05/Experiment-18/blob/main/Screenshot%202024-10-22%20071845.png)

Conclusin:-in this experiment we learnt about stack and its operations

