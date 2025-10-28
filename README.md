# Number-Guessing-Game
In This Project, I added a difficulty level, Hints, and Maximum and minimum numbers.
import random
while True:
    minN = int(input("Choose the Minimum Number"))
    maxN = int(input("Choose the Maximum Number"))
    
    print("\n1.Easy (10chances)")
    print("2.Medium (7chances)")
    print("3.Hard (5chances)")
    
    Deficulty = input("Choose Player Deficulty 1, 2, or 3:")
    
    if Deficulty == '1':
        chances = 10
    elif Deficulty == '2':
        chances = 7
    elif Deficulty == '3':
        chances = 5
    else:
        print("Invaild Deficulty Level, Default Level Is Easy")
        chances = 10
    
    secretN = random.randint(minN,maxN)
    
    print(F"You Choose Number Between {minN} and {maxN}")
    print(F"You Choose Deficulty Level {Deficulty}")
    
    for attempt in range(1, chances + 1):
        guess = int(input(f"Attempt {attempt}/{chances} - Guess The Values: "))
    
        if guess == secretN:
            print(f" 🎉 Congratulation You Have Guessed The Exact Number in {attempt} tries..")
            break
        elif guess > secretN:
            print(" 🔻 You Guessed to High, Hint: Try a Lower Number")
        else:
            print(" 🔺 You Guessed to low, Hint: Try a higher Number")
    
        remaining = chances - attempt
        if remaining:
            print(f"You have {remaining} chances left.\n")
        else:
            print(f"You Have Run out, You have used your All Chances {chances}")
            print(f"The Correct number is {secretN}, Better luck next Time:")

    play_again = input("Do You want to Play Again y/n: ")
    if play_again != 'y':
        print("Thanks You For Playing")
        break
    
