# EX 50 C function to delete a node from a Doubly Linked List at the beginning of the list.
## DATE:08/09/2025
## AIM:
To write a C function to delete a node from a Doubly Linked List at the beginning of the list.

## Algorithm
1. Start the program and define a structure for a doubly linked list node.
2. Create a function deleteAtBeginning() to remove the first node.
3. Check if the list is empty; if yes, print a message.
4. Otherwise, update head to point to the next node and free the deleted node. 
5. Display the updated list.  

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
    insertEnd(10);
    insertEnd(20);
    insertEnd(30);
    display();

    deleteAtBeginning();
    display();

    deleteAtBeginning();
    display();

    return 0;
}


## Output:

<img width="1654" height="689" alt="image" src="https://github.com/user-attachments/assets/58c34088-836d-4f6b-96ea-b128bec51314" />


## Result:
Thus the program was executed and the output was verified successfully.
