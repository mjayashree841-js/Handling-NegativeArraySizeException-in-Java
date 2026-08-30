public class GuestListException {
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 try {
 System.out.print("Enter number of guests: ");
 int size = sc.nextInt();
 // May throw NegativeArraySizeException if size < 0
 String[] guestList = new String[size];
 System.out.println("Guest-list array created successfully "
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
 Handling-NegativeArraySizeException-in-Java
handles NegativeArraySizeException when a guest-list array is created with a negative size.
