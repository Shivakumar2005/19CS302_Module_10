# EX 47 C function to insert a node in a linked list.
## DATE:08/09/2025
## AIM:
To write a C function to insert a node in a linked list.

## Algorithm
1. Start the program and define a structure for the linked list node.
2. Create a function insertEnd() to insert a new node at the end of the list.
3. Allocate memory for the new node and assign data to it.
4. Traverse the list until the last node and link the new node. 
5. Display the updated linked list.  

## Program:
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

void insertEnd(struct Node** head, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if(*head == NULL) {
        *head = newNode;
        return;
    }

    struct Node* temp = *head;
    while(temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
}

void display(struct Node* head) {
    struct Node* temp = head;
    while(temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;

    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);
    insertEnd(&head, 40);

    display(head);

    return 0;
}


## Output:

<img width="1562" height="667" alt="image" src="https://github.com/user-attachments/assets/5977c18a-23d9-4b89-bf55-c73290af72c3" />


## Result:
Thus the program was executed and the output was verified successfully.
