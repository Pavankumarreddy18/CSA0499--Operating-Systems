#include <stdio.h>
#include <stdlib.h>
struct Block {
    int blockNumber;
    struct Block *next;
};
void addBlock(struct Block **head, int blockNumber) {
    struct Block *newBlock = (struct Block *)malloc(sizeof(struct Block));
    newBlock->blockNumber = blockNumber;
    newBlock->next = NULL;
    if (*head == NULL) {
        *head = newBlock;
    } else {
        struct Block *temp = *head;
        while (temp->next != NULL)
            temp = temp->next;
        temp->next = newBlock;
    }
}
void displayFile(struct Block *head) {
    printf("File blocks: ");
    while (head != NULL) {
        printf("%d -> ", head->blockNumber);
        head = head->next;
    }
    printf("NULL\n");
}
int main() {
    int n, blockNumber;
    struct Block *head = NULL;
    printf("Enter the number of blocks in the file: ");
    scanf("%d", &n);
    printf("Enter the block numbers: ");
    for (int i = 0; i < n; i++) {
        scanf("%d", &blockNumber);
        addBlock(&head, blockNumber);
    }
    displayFile(head);
    return 0;
}
