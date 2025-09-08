# EX 46 C function to traverse the linked list and display it in the following format.
## DATE:
## AIM:
To write a C function to traverse the linked list and display it in the following format.

## Algorithm
1. Start the program and define a structure for the linked list node.
2. Create nodes and link them together using pointers.
3. Define a function display() to traverse the linked list.
4. In display(), print each node’s data followed by " -> ". 
5. At the end, print "NULL" to indicate the end of the list.  

## Program:
///
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

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
    struct Node* second = NULL;
    struct Node* third = NULL;

    head = (struct Node*)malloc(sizeof(struct Node));
    second = (struct Node*)malloc(sizeof(struct Node));
    third = (struct Node*)malloc(sizeof(struct Node));

    head->data = 10;
    head->next = second;

    second->data = 20;
    second->next = third;

    third->data = 30;
    third->next = NULL;

    display(head);

    return 0;
}
///

## Output:

<img width="1518" height="662" alt="image" src="https://github.com/user-attachments/assets/357d7272-1ee2-4675-97a6-0d8e5c0982d7" />


## Result:
Thus the program was executed and the output was verified successfully.
