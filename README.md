# symmetrical-spork
import java.util.Scanner;

public class LoopMaster {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        boolean running = true;

        while (running) {
            displayMenu();
            int choice = getUserChoice(scanner);

            switch (choice) {
                case 1:
                    printNumberPattern(scanner);
                    break;
                case 2:
                    validateUserInput(scanner);
                    break;
                case 3:
                    printEnhancedLoopDemo();
                    break;
                case 4:
                    running = false;
                    System.out.println("Exiting Loop Master. Goodbye!");
                    break;
                default:
                    System.out.println("Invalid choice. Try again.\n");
            }
        }

        scanner.close();
    }

    // Modular menu display
    private static void displayMenu() {
        System.out.println("\n=== Loop Master Menu ===");
        System.out.println("1. Generate Number Pattern");
        System.out.println("2. Validate User Input");
        System.out.println("3. Enhanced Loop Demo");
        System.out.println("4. Exit");
        System.out.print("Choose an option: ");
    }

    // Input validation method
    private static int getUserChoice(Scanner scanner) {
        while (!scanner.hasNextInt()) {
            System.out.print("Please enter a valid number: ");
            scanner.next();
        }
        return scanner.nextInt();
    }

    // Nested loop pattern generator
    private static void printNumberPattern(Scanner scanner) {
        System.out.print("Enter number of rows for pattern: ");
        int rows = getUserChoice(scanner);

        System.out.println("\nGenerated Pattern:");
        for (int i = 1; i <= rows; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(j + " ");
            }
            System.out.println();
        }
    }

    // Reusable logic: user input validation
    private static void validateUserInput(Scanner scanner) {
        System.out.print("Enter a number between 1 and 10: ");
        int number = getUserChoice(scanner);

        if (number >= 1 && number <= 10) {
            System.out.println("Valid input!");
        } else {
            System.out.println("Invalid input. Must be between 1 and 10.");
        }
    }

    // Enhanced loop demonstration
    private static void printEnhancedLoopDemo() {
        String[] fruits = {"Apple", "Banana", "Cherry", "Date"};

        System.out.println("\nAvailable Fruits:");
        for (String fruit : fruits) {
            System.out.println("- " + fruit);
        }
    }
}
