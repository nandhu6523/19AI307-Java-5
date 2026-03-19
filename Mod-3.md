
# Exp No - 3

## TITLE : File Handling

### AIM :
To write user input to a file and count the number of characters in it.

### ALGORITHM :
STEP 1 : Start

STEP 2 : Read input string from user

STEP 3 : Write the string to a file using FileWriter

STEP 4 : Open the file using FileReader

STEP 5 : Read characters one by one and count them

STEP 6 : Display the total character count

STEP 7 : End

### PROGRAM :
```
import java.io.FileWriter;
import java.io.FileReader;
import java.io.IOException;
import java.util.Scanner;

public class WriteAndCountCharacters {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String fileName = "userinput.txt";

        String input = scanner.nextLine();

        try {
            FileWriter writer = new FileWriter(fileName);
            writer.write(input);
            writer.close();
        } catch (IOException e) {
            System.out.println("Error writing to file.");
            e.printStackTrace();
            scanner.close();
            return;
        }

        int charCount = 0;
        try {
            FileReader reader = new FileReader(fileName);
            int ch;
            while ((ch = reader.read()) != -1) {
                charCount++;
            }
            reader.close();
        } catch (IOException e) {
            System.out.println("Error reading the file.");
            e.printStackTrace();
        }

        System.out.println("Number of characters written to the file: " + charCount);
        scanner.close();
    }
}
```

### OUTPUT :

<img width="1104" height="244" alt="image" src="https://github.com/user-attachments/assets/e74178a2-2b8c-4347-bfde-900164356f37" />


### RESULT :

Thus to write user input to a file and count the number of characters in it was successfully created.
