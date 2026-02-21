Queue Implementation Using Array in C

This project demonstrates the implementation of a Queue data structure using an array in C.

📖 Description

The program:

Defines a queue structure using an array

Implements basic queue operations:

✅ Enqueue

✅ Dequeue

✅ Front

✅ isFull

✅ isEmpty

Demonstrates queue operations in the main() function

The queue follows the FIFO (First In, First Out) principle.

🧠 Queue Operations
🔹 1. Enqueue

Adds an element to the rear of the queue.

Checks for overflow (queue full).

Updates rear pointer.

Initializes front when first element is inserted.

⏱ Time Complexity: O(1)

🔹 2. Dequeue

Removes and returns the front element.

Checks for underflow (queue empty).

Increments front pointer.

⏱ Time Complexity: O(1)

🔹 3. Front

Returns the front element without removing it.

⏱ Time Complexity: O(1)

🖥️ Program Code
#include <stdio.h>
#include <stdlib.h>

#define MAX 5

// Queue structure
struct Queue {
    int arr[MAX];
    int front, rear;
};

// Function to initialize queue
void initQueue(struct Queue* queue) {
    queue->front = -1;
    queue->rear = -1;
}

// Check if queue is full
int isFull(struct Queue* queue) {
    return queue->rear == MAX - 1;
}

// Check if queue is empty
int isEmpty(struct Queue* queue) {
    return queue->front == -1 || queue->front > queue->rear;
}

// Enqueue operation
void enqueue(struct Queue* queue, int value) {
    if (isFull(queue)) {
        printf("Queue is full\n");
    } else {
        if (queue->front == -1)
            queue->front = 0;

        queue->arr[++queue->rear] = value;
        printf("%d enqueued to queue\n", value);
    }
}

// Dequeue operation
int dequeue(struct Queue* queue) {
    if (isEmpty(queue)) {
        printf("Queue is empty\n");
        return -1;
    } else {
        return queue->arr[queue->front++];
    }
}

// Get front element
int front(struct Queue* queue) {
    if (isEmpty(queue)) {
        printf("Queue is empty\n");
        return -1;
    } else {
        return queue->arr[queue->front];
    }
}

// Main function
int main() {
    struct Queue queue;
    initQueue(&queue);

    enqueue(&queue, 10);
    enqueue(&queue, 20);
    enqueue(&queue, 30);

    printf("Front element is %d\n", front(&queue));

    printf("%d dequeued from queue\n", dequeue(&queue));
    printf("%d dequeued from queue\n", dequeue(&queue));

    printf("Front element is %d\n", front(&queue));

    return 0;
}
▶️ How to Run
Step 1: Compile the program
gcc queue.c -o queue
Step 2: Run the program
./queue
📝 Sample Output
10 enqueued to queue
20 enqueued to queue
30 enqueued to queue
Front element is 10
10 dequeued from queue
20 dequeued from queue
Front element is 30
⚠️ Queue Limit

Maximum size is defined as #define MAX 5

You can increase the value of MAX to expand queue capacity.

🎯 Features

Simple and modular implementation

Uses structure for queue representation

Handles overflow and underflow conditions

Beginner-friendly code

📚 Author

Ritik Chauhan

If you want, I can also create:

🔹 Circular queue implementation

🔹 Queue using linked list

🔹 Menu-driven queue program

🔹 Full Data Structures mini project README 🚀
