'''mermaid
flowchart TD
    A[Start] -->|Generate a random integer between 1 and 10, ranNum| B{Input User Guess, userInput}
    B --> |Test if userInput is a valid input| C{Test Input}
    C --> |userInput is not a valid input| B
    C--> |userInput > ranNum|D(Guess is too big)
    D --> B
    C --> |userInput < ranNum|E(Guess is too small)
    E --> B
    C ----> |userInput == ranNum|F(Guess is correct!)--> End([End])
'''First, the program generates a random integer between 1 and 10.
'''We will likely use a built-in function that generates a random double between 0 and 1, multiply the value by 10, and get the ceil. We will then convert that to an integer so that we can equate user guesses properly.
'''The user inputs a guess. We only really need to check to ensure that it is an integer and not a string or double here. If the check fails, it goes back to user input.
'''Then we check to see whether it is the correct number. If so, the player wins and they get to the end. Otherwise, they will see whether their input is greater or less than the random integer. If their input is incorrect, they get sent back to user input to try again.