//wap to create a simple game in c

#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    int number_to_guess, player_guess, attempts = 0;
    const int max_attempts = 10;

    // Initialize the random number generator with the current time
    srand(time(NULL));

    // Generate a random number between 1 and 100
    number_to_guess = rand() % 100 + 1;

    printf("Welcome to the Guess the Number Game!\n");
    printf("I've selected a random number between 1 and 100. Try to guess it.\n");

    while (1) {
        printf("Enter your guess: ");
        scanf("%d", &player_guess);
        attempts++;

        if (player_guess < 1 || player_guess > 100) {
            printf("Please enter a number between 1 and 100.\n");
            continue;
        }

        if (player_guess < number_to_guess) {
            printf("Too low! Try again.\n");
        } else if (player_guess > number_to_guess) {
            printf("Too high! Try again.\n");
        } else {
            printf("Congratulations! You guessed the number %d in %d attempts!\n", number_to_guess, attempts);
            break;
        }

        if (attempts >= max_attempts) {
            printf("Sorry, you've reached the maximum number of attempts. The number was %d.\n", number_to_guess);
            break;
        }
    }

    return 0;
}
