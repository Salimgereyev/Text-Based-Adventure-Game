# Text-Based-Adventure-Game
This is a basic version of the Adventure game. It is completely text-based. In this version of the game, users can move about through different rooms within a single setting, and based on the user input, it will provide descriptions for each room.


def game_over(reason):
    print("\n" + reason)
    print("Game over!")
    play_again()

def play_again():
    print("\nDo you want to play again? (yes or no)")

    answer = input(">").lower().strip()

    if answer == "yes":
        start()
    else:
        exit()

def diamond_room():
    print("\nYou are now in a room filled with diamonds!")
    print("And there is a door too!")
    print("What would you do? (1 or 2)")
    print("1). Take some diamonds and go through the door.")
    print("2). Just go through the door.")

    answer = input(">")

    if answer == "1":
        game_over("They were cursed diamonds! The moment you touched it, the building collapsed, and you die!")
    elif answer == "2":
        print("\nNice, you're are an honest man! Congrats you win the game!")
        play_again()
    else:
        game_over("Incorrect number choice.")


def monster_room():
    print("\nNow you entered the monster room.")
    print("The monster is sleeping.\nBehind the monster, there is another room. What would you do? (1 or 2) ")
    print("1) Go through the door silently.")
    print("2) Kill the monster and then go through the door.")

    answer = input(">").strip()

    if answer == "1":
        diamond_room()
    elif answer == "2":
        game_over("The monster was hungry and ate you.")
    else:
        game_over("Incorrect number choice. You lost.")


def bear_room():
    print("\nThere is a bear in this room.")
    print("Behind the bear is another door.\nThe bear is eating a tasty honey.\nWhat would you do? (1 or 2)")
    print("1) Take the honey.")
    print("2) Taunt the bear.")

    answer = input(">").strip()

    if answer == "1":
        game_over("The bear killed you.")
    elif answer == "2":
        diamond_room()
    else:
        game_over("Invalid choice(number). You lost.")

def start():
    print("You are standing in a dark room.")
    print("There is a door to your left, which do you take? (l or r)")

    answer = input("Which one do you take? (l or r)").lower().strip()

    if "l" in answer:
        bear_room()
    elif "r" in answer:
        monster_room()
    else:
        game_over("Invalid choice. You lost.")

start()












