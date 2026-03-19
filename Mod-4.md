
# Exp No - 4

## TITLE : Multithreading -I

### AIM :To demonstrate thread creation, setting thread name, and priority in Java.

### ALGORITHM :
STEP 1 : Start

STEP 2 : Create a class extending Thread

STEP 3 : Set thread name using constructor

STEP 4 : Override run() method

STEP 5 : Inside run(), display thread name and priority

STEP 6 : In main(), read thread name

STEP 7 : Create thread object and set priority

STEP 8 : Start the thread

STEP 9 : End

### PROGRAM :
```
import java.util.Scanner;

class MyThread extends Thread
{
    MyThread(String name)
    {
        super(name);   // set thread name
    }

    public void run()
    {
        Thread t = Thread.currentThread();

        System.out.println("Priority of Thread: " + t.getPriority());
        System.out.println("Name of Thread: " + t.getName());
        System.out.println(t);
    }
}

public class Main
{
    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);

        String name = sc.nextLine();   // Read thread name

        MyThread t1 = new MyThread(name);

        t1.setPriority(2);   // Set priority as 2

        t1.start();
    }
}
```

### OUTPUT :
<img width="702" height="221" alt="image" src="https://github.com/user-attachments/assets/6aedc7da-e487-4818-8b39-707366a65987" />

### RESULT :

Thus to demonstrate thread creation, setting thread name, and priority in Java was successfully created.
