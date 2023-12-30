# game
import random
def det_winner(User_choice,comp_choice):
    if User_choice == comp_choice:
        return "its tie!"
    elif(User_choice == 'rock' and comp_choice == 'scissors') or (User_choice == 'scissors' and comp_choice == 'paper') or (User_choice =='paper' and comp_choice == 'rock'):
        return "you win!"
    else:
        return "you lose!"
def play_game():
    User_score = 0
    comp_score = 0
    while True:
        print("\n welcome to rock-paper-scissors!")
        print("choose:rock,paper,scissors.to quit,type,'quit'.")
        User_choice =input("your choice:").lower()
        if User_choice == 'quit':
            break
        if User_choice not in['rock','paper','scissors']:
            print("invalid choice.please choose again.")
            continue
        comp_choice = random.choice(['rock','paper','scissors'])
        print(f"\n you chose:{User_choice}")
        print(f"comp chose:{comp_choice}")
        result=det_winner(User_choice,comp_choice)
        print(result)
    if result == "you win!":
        User_score += 1
    elif result == "you lose!":
        comp_choice += 1
        print(f"score - you:{User_score}comp:{comp_score}")
        print("thanks for playing!")
play_game()
