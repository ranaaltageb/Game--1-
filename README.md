
# Function to display the current status of the game
def display_status(player, total):
    print("Player {}: Total Score = {}".format(player, total))


# Main function to run the game
def main():
    total, player = 0, 1

    # Display initial game status
    display_status(player, total)

    # Main game loop
    while True:
        # Ask the current player to choose a number
        num_str = input("Player {}, please choose a number from 1 to 10: ".format(player))

        # Check if the input is empty
        if not num_str:
            print("Invalid input! Please enter a number.")
            continue

        # Convert the input to an integer
        try:
            num = int(num_str)
        except ValueError:
            print("Invalid input! Please enter a valid number.")
            continue

        # Validate the chosen number
        if not 1 <= num <= 10:
            print("Invalid input! Please choose a number from 1 to 10.")
            continue

        # Update total score
        total += num

        # Display updated game status
        display_status(player, total)

        # Check if any player wins the game
        if total >= 100:
            print("Congratulations! Player {} wins the game!".format(player))
            break

        # Check if the game ends in a draw
        if total == 100:
            print("The game ended in a draw!")
            break

        # Switch to the other player's turn
        if player == 1:
            player = 2
        else:
            player = 1

# Check if the file is being run directly
if __name__ == "__main__":
    main()
