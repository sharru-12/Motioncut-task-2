import time

def welcome():
    print("Welcome to the Text Adventure Game!")
    time.sleep(1)
    print("You are in a mysterious place with choices to make.")

def make_choice(question, options):
    print(question)
    for i, option in enumerate(options, 1):
        print(f"{i}. {option}")

    while True:
        try:
            user_input = int(input("Enter the number of your choice: "))
            if 1 <= user_input <= len(options):
                return user_input
            else:
                print("Invalid choice. Please try again.")
        except ValueError:
            print("Invalid input. Please enter a number.")

def main():
    welcome()

    choice1 = make_choice("You see a path splitting in two. What do you want to do?", ["Go left", "Go right"])

    if choice1 == 1:
        print("You chose to go left. You find a magical forest.")
        time.sleep(1)
        choice2 = make_choice("A rabbit approaches you. What will you do?", ["Talk to the rabbit", "Ignore it"])
        if choice2 == 1:
            print("The rabbit gives you a magical key.")
        else:
            print("You decide to ignore the rabbit and continue your journey.")
    else:
        print("You chose to go right. The path leads to a dark cave.")


if __name__ == "__main__":
 main()
