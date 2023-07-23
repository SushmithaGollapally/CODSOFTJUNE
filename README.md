# CODSOFTJUNE
#number game
import java.util.Random;
import java.util.Scanner;

public class play_again 
{
    public static void main(String[] args) {
        int minValue = 1;
        int maxValue = 100;
        int maxAttempts = 5;
        Random random = new Random();
        Scanner scanner = new Scanner(System.in);

        boolean playAgain;

        do {
            int randomNumber = random.nextInt(maxValue - minValue + 1) + minValue;
            int attempt;

            for (attempt = 1; attempt <= maxAttempts; attempt++) {
                System.out.println("Attempt " + attempt + ": Guess the random number between " + minValue + " and " + maxValue + ":");
                int userGuess = scanner.nextInt();
                if (userGuess == randomNumber) {
                    System.out.println("Congratulations! Your guess is correct.");
                    break;
                } else if (userGuess < randomNumber) {
                    System.out.println("Too low. Try again.");
                } else {
                    System.out.println("Too high. Try again.");
                }
            }
            if (attempt > maxAttempts) {
                System.out.println("Sorry, you've used all your attempts. The correct number was: " + randomNumber);
            }
            System.out.println("Do you want to play again? (true/false):");
            playAgain = scanner.nextBoolean();

        } while (playAgain);

        System.out.println("Thank you for playing!");
        scanner.close();
    }
}
