# linked-list
This program is about linked list to insert and delete node
#include <stdio.h>
#include <stdlib.h>

// Define a structure for a node in the linked list
struct Node {
    int data;
    struct Node* next;
};

// Function to insert a new node at the beginning of the linked list
struct Node* insertNode(struct Node* head, int value) {
    // Create a new node
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) {
        printf("Memory allocation failed!\n");
        exit(1);
    }

    // Set the data and next pointer of the new node
    newNode->data = value;
    newNode->next = head;

    // Update the head to point to the new node
    head = newNode;

    return head;
}

// Function to print the linked list
void printList(struct Node* head) {
    while (head != NULL) {
        printf("%d -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

// Main function to test the linked list
int main() {
    // Initialize an empty linked list
    struct Node* head = NULL;

    // Insert nodes at the beginning
    head = insertNode(head, 3);
    head = insertNode(head, 7);
    head = insertNode(head, 11);

    // Print the linked list
    printf("Linked List: ");
    printList(head);

    return 0;
}
