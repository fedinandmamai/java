import java.util.Scanner;
public class Main {
//initialize the correct username and password
//set login attempts to maximum of 3
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String username = "admin";
        String password = "password";
        int attempts = 3;
//create a loop that continues until either the user successfully logs in or runs out of login attempts
        while (attempts > 0) {
            System.out.print("Enter username: ");
            String inputUsername = scanner.nextLine();

            System.out.print("Enter password: ");
            String inputPassword = "";
            while (scanner.hasNext()) {
                char c = scanner.next().charAt(0);
                if (c == '\n') {
                    break;
                } else {
                    inputPassword += "*";
                }
            }

            if (inputUsername.equals(username) && inputPassword.equals(password)) {
                System.out.println("Login successful!");
                break;
            } else {
                System.out.println("Incorrect username or password. Please try again.");
                attempts--;
            }
        }

        if (attempts == 0) {
            System.out.println("Too many failed login attempts. Exiting...");
        }

        scanner.close();
    }
}
