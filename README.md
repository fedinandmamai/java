import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // Initialize the correct username and password
        String username = "Fedinand";
        String password = "kay";
        // Set login attempts to maximum of 3
        int attempts = 3;
        // Create a loop that continues until either the user successfully logs in or runs out of login attempts
        while (attempts > 0) {
            // Prompt the user to enter their username
            System.out.print("Enter username: ");
            String inputUsername = scanner.nextLine();
            // Prompt the user to enter their password
            System.out.print("Enter password: ");
            String inputPassword = "";
            // Read the password character by character and append a '*' to the inputPassword string
            while (scanner.hasNext()) {
                char c = scanner.next().charAt(0);
                if (c == '\n') {
                    break;
                } else {
                    inputPassword += "*";
                }
            }
            // Check if the input username and password match the correct username and password
            if (inputUsername.equals(username) && inputPassword.equals(password)) {
                // Print a success message and break out of the loop
                System.out.println("Login successful!");
                break;
            } else {
                // Print an error message and decrement the number of attempts
                System.out.println("Incorrect username or password. Try again.");
                attempts--;
            }
        }
        // Check if the user has no more attempts left
        if (attempts == 0) {
            // Print an error message and exit the program
            System.out.println("Too many failed login attempts. Exiting...");
            System.exit(0);
        }
        // Close the scanner
        scanner.close();
    }
}
