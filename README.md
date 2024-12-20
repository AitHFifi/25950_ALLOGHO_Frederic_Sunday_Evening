# 25950_ALLOGHO_Frederic_Sunday_Evening
Assignment

Exception Handling Exercises 

This submission demonstrates a practical approach to exception handling in Java. Each exception listed in the assignment is simulated in a specific and meaningful scenario to illustrate its occurrence. The programs employ the following key principles:
Deliberate Triggering: Each exception is intentionally triggered by creating a realistic scenario where it might naturally occur (e.g., accessing a null object, reading a non-existent file, or performing an invalid type cast).
Exception Handling: Each program includes appropriate try-catch blocks to catch and handle the exceptions. In some cases, a finally block is used to ensure resources are released, such as closing files or database connections.
Descriptive Comments: The code is annotated with clear comments explaining the purpose of each block, why the exception occurs, and how it is handled.
Comprehensive Coverage: Both checked and unchecked exceptions are handled, ensuring all exceptions listed in the assignment are addressed.

// ArithmeticExeceptionE Example
```
public class ArithmeticExceptionE {
    public static void main(String[] args) {
        // Purpose: Demonstrates division by zero causing an ArithmeticException.
        try {
            // Trigger ArithmeticException
            int result = 10 / 0;
            System.out.println("Result: " + result);
        }
        catch (ArithmeticException e) {
            // Handle ArithmeticException
            System.err.println("ArithmeticException occurred: Division by zero is not allowed.");
        }
        System.out.println("Program execution continues...");
    }
}
```

// ArrayIndexOutOfBoundsExceptionE Example
```
public class ArrayIndexOutOfBoundsExceptionE {
    public static void main(String[] args) {
        // Purpose: Accessing an invalid index in an array causes ArrayIndexOutOfBoundsException.
        try {
            // Trigger ArrayIndexOutOfBoundsException
            int[] numbers = {1, 2, 3};
            System.out.println(numbers[5]);
        }
        catch (ArrayIndexOutOfBoundsException e) {
            // Handle ArrayIndexOutOfBoundsException
            System.err.println("ArrayIndexOutOfBoundsException occurred: Invalid index accessed.");
        }
        System.out.println("Program execution continues...");
    }
}
```

// ClassCastExceptionE Example
```
public class ClassCastExceptionE {
    public static void main(String[] args) {
        // Purpose: Demonstrates invalid type casting causing a ClassCastException.
        try {
            // Trigger ClassCastException
            Object obj = "This is a string";
            Integer num = (Integer) obj; // Invalid cast
            System.out.println(num);
        }
        catch (ClassCastException e) {
            // Handle ClassCastException
            System.err.println("ClassCastException occurred: Invalid type casting.");
        }
        System.out.println("Program execution continues...");
    }
}
```

// ClassNotFoundExceptionE Example 
```
public class ClassNotFoundExceptionE {
    public static void main(String[] args) {
        // Purpose: Simulate missing class at runtime.
        try {
            // Attempt to load a non-existent class
            Class.forName("com.payment");
        }
        catch (ClassNotFoundException e) {
            // Handle ClassNotFoundException
            System.err.println("ClassNotFoundException occurred: " + e.getMessage());
        }
        System.out.println("Program execution continues...");
    }
}
```

// EOFExceptionE Example
```
import java.io.*;
import java.io.FileNotFoundException;
import java.io.IOException;

public class EOFExceptionE {
    public static void main(String[] args) {
        // Purpose: Demonstrates EOFException by reading beyond available content in a DataInputStream.
        try {
            // Create a file and write some data
            FileOutputStream fos = new FileOutputStream("StudNum.dat");
            DataOutputStream dos = new DataOutputStream(fos);
            dos.writeUTF("Hello, world!");
            // Read beyond the file content
            FileInputStream fis = new FileInputStream("StudName.dat");
            DataInputStream dis = new DataInputStream(fis);
            // Read data correctly
            System.out.println(dis.readUTF());
            // Attempt to read more, triggering EOFException
            System.out.println(dis.readUTF())
        }
        catch (EOFException e) {
            // Handle EOFException
            System.err.println("EOFException occurred: Reached the end of the file unexpectedly.");
        }
        catch (IOException e) {
            // Handle other IOExceptions
            System.err.println("An IOException occurred: " + e.getMessage());
        }
        System.out.println("Program execution continues...");
    }
}
```
// FileNotFoundExceptionE Example
```
import java.io.*;

public class FileNotFoundExceptionE {
    public static void main(String[] args) {
        // Purpose: Demonstrates handling FileNotFoundException (a type of IOException).

        try {
            // Attempt to open a non-existent file
            FileReader fileReader = new FileReader("Readme.txt");

            // If the file existed, this line would read data
            System.out.println("File opened successfully!");
        }
        catch (FileNotFoundException e) {
            // Handle FileNotFoundException (specific IOException)
            System.err.println("FileNotFoundException occurred: The file does not exist.");
        }

        System.out.println("Program execution continues...");
    }
}
```
// IllegalArgumentExceptionE Example 

```
public class IllegalArgumentExceptionE {
    public static void main(String[] args) {
        // Purpose: Pass an invalid argument to a method to cause IllegalArgumentException.
        try {
            // Trigger IllegalArgumentException
            setAge(-5);
        }
        catch (IllegalArgumentException e) {
            // Handle IllegalArgumentException
            System.err.println("IllegalArgumentException occurred: " + e.getMessage());
        }

        System.out.println("Program execution continues...");
    }

    public static void setAge(int age) {
        if (age < 0) {
            throw new IllegalArgumentException("Age cannot be negative.");
        }
        System.out.println("Age set to: " + age);
    }
}
```

// IOExceptionE Example 
```
import java.io.*;

public class IOExceptionE {
        public static void main(String[] args) {
            // Purpose: Demonstrates how to handle an IOException when attempting to read a file.
            try {
                // Attempt to read a non-existent file
                FileReader fileReader = new FileReader("Registration.txt");
                BufferedReader bufferedReader = new BufferedReader(fileReader);
                // Simulate reading the file
                String line;
                while ((line = bufferedReader.readLine()) != null) {
                    System.out.println(line);
                }
            }
            catch (IOException e) {
                // Handle IOException (file not found or reading error)
                System.err.println("An IOException occurred: " + e.getMessage());
            }
            System.out.println("Program execution continues...");
        }

}
```

// NullPointerExceptionE Example
```
public class NullPointerExceptionE {
    public static void main(String[] args) {
        // Purpose: Accessing a method on a null reference causes a NullPointerException.

        try {
            // Trigger NullPointerException
            String str = null;
            System.out.println(str.length());
        }
        catch (NullPointerException e) {
            // Handle NullPointerException
            System.err.println("NullPointerException occurred: Attempted to access a method on a null object.");
        }

        System.out.println("Program execution continues...");
    }
}
```

// NumberFormatExceptionE Example
```
public class NumberFormatExceptionE {
    public static void main(String[] args) {
        // Purpose: Demonstrates an invalid string-to-number conversion causing NumberFormatException.
        try {
            // Trigger NumberFormatException
            String invalidNumber = "123abc";
            int number = Integer.parseInt(invalidNumber);
            System.out.println("Converted number: " + number);
        }
        catch (NumberFormatException e) {
            // Handle NumberFormatException
            System.err.println("NumberFormatException occurred: Invalid number format.");
        }
        System.out.println("Program execution continues...");
    }
}
```

// SQLExceptionE Example 
``` 
import java.sql.*;

public class SQLExceptionE {
    public static void main(String[] args) {
        // Purpose: Simulate a database error (invalid query or connection issue).
        Connection connection = null;
        try {
            // Load database driver (Assume no valid driver for demonstration)
            Class.forName("com.invalid.Manager");

            // Attempt to connect to a database (Invalid URL)
            connection = DriverManager.getConnection("jdbc:invalid:url", "fifi", "fifi");

            // Execute an invalid SQL query
            Statement statement = connection.createStatement();
            statement.executeQuery("INVALID SQL");
        }
        catch (SQLException e) {
            // Handle SQLException
            System.err.println("SQLException occurred: " + e.getMessage());
        }
        catch (ClassNotFoundException e) {
            // Handle missing driver
            System.err.println("ClassNotFoundException: Database driver not found.");
        }
        finally {
            try {
                if (connection != null) {
                    connection.close();
                }
            } catch (SQLException e) {
                System.err.println("Error closing connection: " + e.getMessage());
            }
        }
        System.out.println("Program execution continues...");
    }
}
```
