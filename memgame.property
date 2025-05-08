
import tkinter as tk
import random

root = tk.Tk()
root.title("Memory Matching Game")

cards = list("AABBCCDDEEFFGGHH")
random.shuffle(cards)
buttons = []
flipped = []
matched = []

def flip(card_index):
    if card_index in matched or card_index in flipped or len(flipped) == 2:
        return
    buttons[card_index].config(text=cards[card_index])
    flipped.append(card_index)
    if len(flipped) == 2:
        root.after(1000, check_match)

def check_match():
    global flipped
    i, j = flipped
    if cards[i] == cards[j]:
        matched.extend([i, j])
    else:
        buttons[i].config(text="")
        buttons[j].config(text="")
    flipped = []

for i in range(16):
    btn = tk.Button(root, text="", width=4, height=2, command=lambda i=i: flip(i))
    btn.grid(row=i // 4, column=i % 4)
    buttons.append(btn)

root.mainloop()
