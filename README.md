# tkinter-and-web-projets-
<!-- that is a source code for tic tac toe game -->
from tkinter import *
import random
def prnt(row,col):
    global player
    if player==players[0] and buttons[row][col]["text"]=="":
        buttons[row][col]["text"]=players[0]
        if check_winner() is False:
            label.config(text=(players[1]+"   turn"))
            player=players[1]
        elif check_winner()is True:
            label.config(text=(players[0]+"  wins"))
        else:
            label.config(text=("Tie"))
            for row in range(3):
                for col in range(3):
                    buttons[row][col].config(bg="yellow")
    else:
        if player==players[1] and buttons[row][col]["text"]=="":
            buttons[row][col]["text"]=players[1]
            if check_winner() is False:
                label.config(text=(players[0]+"   turn"))
                player=players[0]
            elif check_winner()is True:
                label.config(text=(players[1]+"  wins"))
                # for row in range(3):
                #     for col in range(3):
                print(buttons[0]["text"])
            elif check_winner() is "tie":
                label.config(text=("Tie"))
                for row in range(3):
                    for col in range(3):
                        buttons[row][col].config(bg="yellow")

def check_winner():
    if buttons[0][0]["text"]==player and buttons[0][1]["text"]==player and buttons[0][2]["text"]==player:
        buttons[0][0].config(bg="green")
        buttons[0][1].config(bg="green")
        buttons[0][2].config(bg="green")
        return True
    elif buttons[1][0]["text"]==player and buttons[1][1]["text"]==player and buttons[1][2]["text"]==player:
        buttons[1][0].config(bg="green")
        buttons[1][1].config(bg="green")
        buttons[1][2].config(bg="green")
        return True
    elif buttons[2][0]["text"]==player and buttons[2][1]["text"]==player and buttons[2][2]["text"]==player:
        buttons[2][0].config(bg="green")
        buttons[2][1].config(bg="green")
        buttons[2][2].config(bg="green")
        return True
    if buttons[0][0]["text"]==player and buttons[1][0]["text"]==player and buttons[2][0]["text"]==player:
        buttons[0][0].config(bg="green")
        buttons[1][0].config(bg="green")
        buttons[2][0].config(bg="green")
        return True
    elif buttons[0][1]["text"]==player and buttons[1][1]["text"]==player and buttons[2][1]["text"]==player:
        buttons[0][1].config(bg="green")
        buttons[1][1].config(bg="green")
        buttons[2][1].config(bg="green")
        return True
    elif buttons[0][2]["text"]==player and buttons[1][2]["text"]==player and buttons[2][2]["text"]==player:
        buttons[0][2].config(bg="green")
        buttons[1][2].config(bg="green")
        buttons[2][2].config(bg="green")
        return True
    elif buttons[0][0]["text"]==player and buttons[1][1]["text"]==player and buttons[2][2]["text"]==player:
        buttons[0][0].config(bg="green")
        buttons[1][1].config(bg="green")
        buttons[2][2].config(bg="green")
        return True
    elif buttons[0][2]["text"]==player and buttons[1][1]["text"]==player and buttons[2][0]["text"]==player:
        buttons[0][2].config(bg="green")
        buttons[1][1].config(bg="green")
        buttons[2][0].config(bg="green")
        return True
    elif isempty() is False:
        return "tie"
    else:
        return False
def isempty():
    for row in range(3):
        for col in range(3):
            if buttons[row][col]["text"]=="":
                return True
    return False
def new_game():
    global player
    player=random.choice(players)
    label.config(text=(player+"    turn"))
    for row in range(3):
        for col in range(3):
            buttons[row][col]["text"]=""
            buttons[row][col].config(bg="#F0F0F0")
root=Tk()
root.title("tic-tac-toe")
players=["x","y"]
player=random.choice(players)
label=Label(root,text=player+"    turn",font="Arial 14 bold")
label.pack()
reset=Button(root,text="restart",command=new_game,font="Arial 14 bold",fg="red")
reset.pack()
buttons=[[0,0,0],
         [0,0,0],
         [0,0,0]]
frame=Frame(root)
frame.pack()
for row in range(3):
    for col in range(3):
        buttons[row][col]=Button(frame,text="",command=lambda row=row,col=col:prnt(row,col),font="Arial 14 bold",fg="red",height=4,width=5)
        buttons[row][col].grid(row=row,column=col)

root.mainloop()


hy
