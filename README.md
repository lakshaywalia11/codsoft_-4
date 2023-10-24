# codsoft_-4
import tkinter as tk
from tkinter import messagebox
import random

def play_game(player_choice):
    choices = ["Rock", "Paper", "Scissors"]
    computer_choice = random.choice(choices)

    result = ""

    if player_choice == computer_choice:
        result = "It's a tie!"
    elif (player_choice == "Rock" and computer_choice == "Scissors") or \
         (player_choice == "Paper" and computer_choice == "Rock") or \
         (player_choice == "Scissors" and computer_choice == "Paper"):
        result = "You win!"
    else:
        result = "You lose!"

    messagebox.showinfo("Result", f"Your choice: {player_choice}\nComputer's choice: {computer_choice}\nResult: {result}")

root = tk.Tk()
root.title("Rock Paper Scissors")

rock_button = tk.Button(root, text="Rock", padx=20, pady=10, command=lambda: play_game("Rock"))
rock_button.pack(pady=10)

paper_button = tk.Button(root, text="Paper", padx=20, pady=10, command=lambda: play_game("Paper"))
paper_button.pack(pady=10)

scissors_button = tk.Button(root, text="Scissors", padx=20, pady=10, command=lambda: play_game("Scissors"))
scissors_button.pack(pady=10)

root.mainloop()
