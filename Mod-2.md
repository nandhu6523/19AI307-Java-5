
# Exp No - 2

## TITLE :  I/O Streams -II

### AIM :
To store and retrieve multiple strings in memory using byte streams (ByteArrayOutputStream and ByteArrayInputStream) with UTF format.

### ALGORITHM :
STEP : Start

STEP 1 : Read number of strings n

STEP 2 : Create ByteArrayOutputStream and DataOutputStream

STEP 3 : Write each string using writeUTF()

STEP 4 : Convert output stream to byte array

STEP 5 : Display byte array and total bytes

STEP 6 : Create ByteArrayInputStream and DataInputStream

STEP 7 : Read strings using readUTF()

STEP 8 : Display the strings

STEP 9 : End

### PROGRAM :
```
import java.io.*;
import java.util.Scanner;

public class UTFStringsInMemoryUserInput {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            ByteArrayOutputStream baos = new ByteArrayOutputStream();
            DataOutputStream dos = new DataOutputStream(baos);

            int n = scanner.nextInt();
            scanner.nextLine();

            for (int i = 0; i < n; i++) {
                String str = scanner.nextLine();
                dos.writeUTF(str);
            }

            byte[] byteData = baos.toByteArray();

            System.out.println("Byte array contents:");
            for (byte b : byteData) {
                System.out.print(b + " ");
            }
            System.out.println("\nTotal bytes: " + byteData.length);

            ByteArrayInputStream bais = new ByteArrayInputStream(byteData);
            DataInputStream dis = new DataInputStream(bais);

            System.out.println("\nStrings read from memory:");
            for (int i = 0; i < n; i++) {
                String readStr = dis.readUTF();
                System.out.println(readStr);
            }

            dos.close();
            dis.close();
            baos.close();
            bais.close();

        } catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        }

        scanner.close();
    }
}
```

### OUTPUT :

<img width="1188" height="714" alt="image" src="https://github.com/user-attachments/assets/c6441009-7510-47fd-b6a6-5ea62ffa286e" />

### RESULT :

Thus to store and retrieve multiple strings in memory using byte streams (ByteArrayOutputStream and ByteArrayInputStream) with UTF format was successfully created.
