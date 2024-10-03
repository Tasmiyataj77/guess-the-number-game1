# guess-the-number-game1
#include<iostream>
#include<cstdlib> // For rand() and srand()
#include<ctime>   // For time()
using namespace std;

int main() {
    int randomNumber, guess, attempts = 0;

    // Seed random number generator
    srand(time(0));  
    randomNumber = rand() % 100 + 1;  // Generates a random number between 1 and 100

    cout << "Welcome to the Guess the Number game!\n";
    cout << "I have selected a number between 1 and 100. Can you guess it?\n";

    // Game loop
    do {
        cout << "Enter your guess: ";
        cin >> guess;
        attempts++;

        if (guess > randomNumber) {
            cout << "Too high! Try again.\n";
        } else if (guess < randomNumber) {
            cout << "Too low! Try again.\n";
        } else {
            cout << "Congratulations! You guessed the number in " << attempts << " attempts.\n";
        }

    } while (guess != randomNumber);

    return 0;
}
