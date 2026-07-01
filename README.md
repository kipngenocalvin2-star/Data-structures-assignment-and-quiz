\\# Data-structures-assignment-and-quiz\\
\\**A C program for basic queue using Array using Arrays.**\\
#include <stdio.h>
#define MAX 5

int queue[MAX];
int front = -1, rear = -1;

// Changed return type to void and added 'int' to the parameter
void enqueue(int x) {
    if(rear == MAX - 1) {
        printf("The Q is full!!\n");
    }
    else {
        if(front == -1) front = 0;
        rear++;
        queue[rear] = x;
        printf("%d has been Queued! \n", x);
    }
}

int dequeue() {
    if(rear == -1 && front == -1) {
        printf("The Q is Empty!! \n");
        front = rear = -1;
        return -1; // Added return statement to satisfy the 'int' return type
    }
    else {
        // Fetch the value first, then increment front
        int x = queue[front];
        front++;
        
        if(front > rear) {
            front = rear = -1;
        }
        
        printf("%d has been dequeued! \n", x);
        return x;
    }
}

int main(int argc, char** argv) {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);
    enqueue(50);
    enqueue(60); // Trigger full message
    dequeue();
    dequeue();
    dequeue();
    dequeue();
    dequeue();
    dequeue(); // Trigger empty message
    
    return 0;
}
