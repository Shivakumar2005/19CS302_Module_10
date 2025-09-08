# EX 49 C function to search an element in the doubly linked list.
## DATE:08/09/2025
## AIM:
To write a C function to search an element in the doubly linked list.

## Algorithm
1. Start the program and define a structure for the doubly linked list node.
2. Create nodes and link them together.
3. Define a function search() to traverse the list.
4. Compare each node’s data with the key element. 
5. If found, return position; otherwise, display not found.  

## Program:
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

struct Node* head = NULL;

void insertEnd(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    if(head == NULL) {
        newNode->prev = NULL;
        head = newNode;
        return;
    }
    struct Node* temp = head;
    while(temp->next != NULL)
        temp = temp->next;
    temp->next = newNode;
    newNode->prev = temp;
}

void search(int key) {
    struct Node* temp = head;
    int pos = 1, found = 0;
    while(temp != NULL) {
        if(temp->data == key) {
            printf("Element %d found at position %d\n", key, pos);
            found = 1;
            break;
        }
        temp = temp->next;
        pos++;
    }
    if(!found)
        printf("Element %d not found in the list\n", key);
}

void display() {
    struct Node* temp = head;
    printf("Doubly Linked List: ");
    while(temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    insertEnd(10);
    insertEnd(20);
    insertEnd(30);
    insertEnd(40);

    display();
    search(30);
    search(50);

    return 0;
}


## Output:

<img width="1715" height="676" alt="image" src="https://github.com/user-attachments/assets/3aa21c44-7caa-40b4-bfda-3faaeadc080f" />


## Result:
Thus the program was executed and the output was verified successfully.
