
# Exp No - 1

## TITLE : I/O Streams -I

### AIM : 
To write user input content into a file using FileOutputStream.

### ALGORITHM :
STEP 1 : Start

STEP 2 : Read file name and content from user

STEP 3 : Create FileOutputStream object

STEP 4 : Convert content into byte array

STEP 5 : Write bytes to file

STEP 6 : Close the file

STEP 7 : Display success or error message

STEP 8 : End

### PROGRAM :
```
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.Scanner;

public class WriteFileOutputStream {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        String fileName = scanner.nextLine();

        String content = scanner.nextLine();

        try {
            FileOutputStream fos = new FileOutputStream(fileName);
            byte[] bytes = content.getBytes();
            fos.write(bytes);
            fos.close();
            System.out.println("File written successfully.");
        } catch (IOException e) {
            System.out.println("Error writing to file: " + e.getMessage());
        }

        scanner.close();
    }
}
```

### OUTPUT :

<img width="718" height="300" alt="image" src="https://github.com/user-attachments/assets/e73aed74-dba3-4aca-8116-bf471cd54baa" />

### RESULT :

Thus to write user input content into a file using FileOutputStream was successfully created.
