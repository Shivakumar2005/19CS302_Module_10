# EX 48 C functions to perform all basic operations in Doubly Linked List.
## DATE:08/9/2025
## AIM:
To write a C functions to perform all basic operations in Doubly Linked List.

## Algorithm
1. Start the program and define a structure for the doubly linked list node with prev, data, and next.
2. Implement insertAtBeginning() and insertAtEnd() to add nodes.
3. Implement deleteAtBeginning() and deleteAtEnd() to remove nodes.
4. Implement display() to traverse and print all nodes in forward order. 
5. Call these functions in main() to demonstrate all basic operations.  

## Program:
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

struct Node* head = NULL;

void insertAtBeginning(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = head;
    if(head != NULL)
        head->prev = newNode;
    head = newNode;
}

void insertAtEnd(int value) {
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

void deleteAtBeginning() {
    if(head == NULL) {
        printf("List is empty\n");
        return;
    }
    struct Node* temp = head;
    head = head->next;
    if(head != NULL)
        head->prev = NULL;
    printf("Deleted: %d\n", temp->data);
    free(temp);
}

void deleteAtEnd() {
    if(head == NULL) {
        printf("List is empty\n");
        return;
    }
    struct Node* temp = head;
    while(temp->next != NULL)
        temp = temp->next;
    if(temp->prev != NULL)
        temp->prev->next = NULL;
    else
        head = NULL;
    printf("Deleted: %d\n", temp->data);
    free(temp);
}

void display() {
    struct Node* temp = head;
    if(temp == NULL) {
        printf("List is empty\n");
        return;
    }
    printf("Doubly Linked List: ");
    while(temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    insertAtEnd(10);
    insertAtEnd(20);
    insertAtBeginning(5);
    display();

    deleteAtBeginning();
    display();

    deleteAtEnd();
    display();

    return 0;
}


## Output:

<img width="1604" height="662" alt="image" src="https://github.com/user-attachments/assets/05a0b591-aa00-43a6-b71c-b376672255b8" />


## Result:
Thus the program was executed and the output was verified successfully.
