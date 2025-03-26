#include <stdio.h>
#include <stdlib.h>
#define DIRECTION_LEFT 0
#define DIRECTION_RIGHT 1
void sort(int arr[], int n) {
    int i, j, temp;
    for (i = 0; i < n - 1; i++) {
        for (j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                // Swap the elements if they are in the wrong order
                temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}
int main() {
    int diskSize, currentPosition, totalRequests;
    printf("Enter the size of the disk: ");
    scanf("%d", &diskSize);
    printf("Enter the current position of the disk arm: ");
    scanf("%d", &currentPosition);
    printf("Enter the total number of disk requests: ");
    scanf("%d", &totalRequests);
    int requests[totalRequests];
    int i;
    printf("Enter the disk request track numbers:\n");
    for (i = 0; i < totalRequests; i++) {
        scanf("%d", &requests[i]);
    }
    // Sort the disk requests in ascending order
    sort(requests, totalRequests);
    int direction;
    printf("Enter the initial direction (0 for left, 1 for right): ");
    scanf("%d", &direction);
    int seekCount = 0;
    if (direction == DIRECTION_LEFT) {
        // SCAN towards the left
        for (i = currentPosition; i >= 0; i--) {
            printf("Servicing track %d\n", i);
            seekCount += abs(currentPosition - i);
            currentPosition = i;
        }
        // Change direction
        direction = DIRECTION_RIGHT;
    }
    // SCAN towards the right
    for (i = currentPosition; i <= diskSize; i++) {
        printf("Servicing track %d\n", i);
        seekCount += abs(currentPosition - i);
        currentPosition = i;
    }
    // Simulate reverse direction towards the left
    if (direction == DIRECTION_RIGHT) {
        for (i = currentPosition; i >= 0; i--) {
            printf("Servicing track %d\n", i);
            seekCount += abs(currentPosition - i);
            currentPosition = i;
        }
    }
    printf("Total seek count: %d\n", seekCount);
    return 0;
}
