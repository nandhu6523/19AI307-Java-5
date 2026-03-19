
# Exp No - 5

## TITLE : Multithreading -II

### AIM :
To demonstrate multithreading with synchronization by safely incrementing a shared counter.

### ALGORITHM :
STEP 1 : Start

STEP 2 : Create a Counter class with a variable count

STEP 3 : Create a Worker thread class

STEP 4 : Pass shared counter and increment value to each thread

STEP 5 : Use synchronized block to safely update count

STEP 6 : Create and start multiple threads

STEP 7 : Wait for all threads using join()

STEP 8 : Display final count

STEP 9 : End

### PROGRAM :
```
import java.util.Scanner;

class Counter {
    int count = 0;
}

class Worker extends Thread {
    Counter counter;
    int times;

    Worker(Counter counter, int times) {
        this.counter = counter;
        this.times = times;
    }

    public void run() {
        for (int i = 0; i < times; i++) {
            synchronized(counter) {
                counter.count++;
            }
        }
    }
}

public class Main {
    public static void main(String[] args) throws Exception {

        Scanner sc = new Scanner(System.in);

        int threads = sc.nextInt();      // read number of threads
        int increments = sc.nextInt();   // read increments

        Counter counter = new Counter();
        Worker[] workers = new Worker[threads];

        for (int i = 0; i < threads; i++) {
            workers[i] = new Worker(counter, increments);
            workers[i].start();
        }

        for (int i = 0; i < threads; i++) {
            workers[i].join();
        }

        System.out.println("Final count: " + counter.count);
    }
}
```

### OUTPUT :

<img width="522" height="310" alt="image" src="https://github.com/user-attachments/assets/34bfb062-24fb-476c-ba41-5a1739702281" />

### RESULT :

Thus to demonstrate multithreading with synchronization by safely incrementing a shared counter was successfully created.
