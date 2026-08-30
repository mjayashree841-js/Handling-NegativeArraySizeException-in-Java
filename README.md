Objective:

To design and implement a Java program that creates a guest-list array based on user-supplied size,
and to gracefully handle the situation where the user enters a negative number for the array size. In
Java, attempting to create an array with a negative size throws a runtime exception called
NegativeArraySizeException. The objective of this program is to catch this exception using proper
exception-handling constructs, display a meaningful error message to the user instead of letting the
program crash abruptly, and ensure the program terminates gracefully.

2. Concepts Used

• Exception Handling: Using try, catch and finally blocks to handle runtime errors.

• NegativeArraySizeException: An unchecked exception (subclass of RuntimeException)thrown by the JVM when an array is created with a negative size.

• Arrays in Java: Declaration and dynamic creation of arrays using the 'new' keyword.

• Scanner Class: Used to read user input from the console (java.util.Scanner).

• Multi-catch / Specific catch blocks: Catching a specific exception type before a generic Exception, to give precise error messages.

• finally Block: Used to release resources (closing the Scanner) and ensure certain code always
executes, regardless of whether an exception occurred.

3. Algorithm

Step 1: Start the program and create a Scanner object to read input from the console.

Step 2: Prompt the user to enter the number of guests (the size of the guest-list array).

Step 3: Read the integer value entered by the user and store it in a variable 'size'.

Step 4: Inside a try block, attempt to create a String array named 'guestList' of the given size
using the statement: String[] guestList = new String[size];

Step 5: If 'size' is negative, the JVM throws a NegativeArraySizeException at this statement, and
control immediately jumps to the matching catch block.

Step 6: In the catch(NegativeArraySizeException e) block, print a user-friendly error message
along with the exception's message obtained via e.getMessage().

Step 7: If 'size' is zero or positive, the array is created successfully; prompt the user to enter
each guest's name and store it in the array.

Step 8: Display the complete guest list to the user.

Step 9: In the finally block, close the Scanner object and print a program-completion message so
that this always executes whether or not an exception occurred.

Step 10: End the program.

4. Java Code

import java.util.Scanner;
public class GuestListException {

 public static void main(String[] args)
 {
 Scanner sc = new Scanner(System.in);

 try {
 System.out.print("Enter number of guests: ");

 int size = sc.nextInt();
 // May throw NegativeArraySizeException if size < 0

 String[] guestList = new String[size];
 System.out.println("Guest-list array
 created successfully "
 + "with size: " + size);

 for (int i = 0; i < guestList.length; i++) {
 System.out.print("Enter name of guest " + (i + 1) + ": ");

 guestList[i] = sc.next();
 }

 System.out.println("\n--- Guest List ---");

 for (String guest : guestList) {
 System.out.println(guest);
 }
 } catch (NegativeArraySizeException e) {
 System.out.println("Error: Cannot create guest-list array. "
 + "Array size cannot be negative.");
 System.out.println("Exception message: " + e.getMessage());
 } catch (Exception e) {
 System.out.println("An unexpected error occurred: " + e);
 } finally {
 sc.close();
 System.out.println("Program execution completed.");
 }
 }
}
5. Output

Test Case 1: Negative size entered

Enter number of guests: -5

Error: Cannot create guest-list array.
 Array size cannot be negative.

Exception message: -5

Program execution completed.

Test Case 2: Valid (positive) size
 entered

Enter number of guests: 3

Guest-list array created successfully
 with size: 3

Enter name of guest 1: Arjun

Enter name of guest 2: Priya

Enter name of guest 3: Kabir

--- Guest List ---

Arjun

Priya

Kabir
Program execution completed.


6. Reference

 Oracle Java Documentation – NegativeArraySizeException,
docs.oracle.com/javase/8/docs/api/java/lang/NegativeArraySizeException.html

• Oracle Java Tutorials – 'Exceptions', The Java Tutorials,
docs.oracle.com/javase/tutorial/essential/exceptions/

• Herbert Schildt, Java: The Complete Reference, McGraw-Hill Education.

• Oracle Java Documentation – java.util.Scanner class,
docs.oracle.com/javase/8/docs/api/java/util/Scanner.html
 Handling-NegativeArraySizeException-in-Java
handles NegativeArraySizeException when a guest-list array is created with a negative size.
