// # JavaTopperWorldInternshipProject

import java.util.Random;
import java.util.Scanner;

public class NumGuessGame {
    public static void main(String[] args) {
        Scanner scanObj = new Scanner(System.in);
        Random randObj = new Random();
        
        int lowBound = 1; // Minimum value
        int upBound = 100; // Maximum value
        int numToGuess = randObj.nextInt(upBound - lowBound + 1) + lowBound;
        
        int numOfTries = 0;
        boolean hasGuessedCorrectly = false;
        
        System.out.println("Welcome to the Number Guessing Game!");
        System.out.println("I'm thinking of a number between " + lowBound + " and " + upBound + ". Try to guess it.");
        
        while (!hasGuessedCorrectly) {
            System.out.print("Enter your guess: ");
            int userGuess = scanObj.nextInt();
            numOfTries++;
            
            if (userGuess < lowBound || userGuess > upBound) {
                System.out.println("Please guess a number between " + lowBound + " and " + upBound + ".");
            } else if (userGuess < numToGuess) {
                System.out.println("Try higher.");
            } else if (userGuess > numToGuess) {
                System.out.println("Try lower.");
            } else {
                hasGuessedCorrectly = true;
                System.out.println("Congratulations! You've guessed the number " + numToGuess + " correctly in " + numOfTries + " tries.");
            }
        }
        
        scanObj.close();
    }
}
