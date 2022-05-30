# game

def nickname2(nickname,life,scores):
    change_id = input("Enter your new nickname:").lower()
    nickname = change_id
    Return(nickname,life,scores)
    return nickname


def Return(nickname,life,scores):
    print(f"profile:"
          f"nickname : {nickname}")
    while True:
        try:
            input_new_nickname = input("Wish to go back to home page? (yes or no): ").lower()

            if input_new_nickname == "yes":
                welcome2(nickname,life,scores)
            elif input_new_nickname == "no":
                Return(nickname,life,scores)
            else:
                print("wrong credentials, please try again...")
        except ValueError:
            print("wrong credentials, please try again...")



def nickname1(nickname,life,scores):
    while True:
        try:
            input_nick = input("Do you want to change your nickname? (yes or no): ").lower()
            if input_nick == "yes":
                nickname2(nickname,life,scores)
                break
            elif input_nick == "no":
                print("turning you back at the previous page...")
                welcome2(nickname,life,scores)
            else:
                print("wrong credentials, please try again...")
        except ValueError:
            print("wrong credentials, please try again...")

def total_score(nickname,life,scores):
    print("========== < SCORE > ==============")
    print(f"total score: ({scores}/5)")

    if scores >= 5:
        print("congrats, you've got perfect! <3")
    elif scores == 4:
        print(" good, you've got almost perfect")
    elif scores == 3:
        print("not bad after all")
    elif scores <=2:
        print("sorry, you fail...")
    else:
        print("sorry, not accurate")

    while True:
        try:
            print("==============================================================")
            input_home = input("wanna go back to home page? (yes or no):").lower()
            if input_home == "yes":
                scores -= scores
                welcome2(nickname, life, scores)
                break
            elif input_home == "no":
                print("thankyou for playing our game, have a nice day! <3")
                break
            else:
                print("wrong credentials,please try again...")
                break
        except ValueError:
            print("wrong credentials, please try again... ")


def question5(nickname,life,scores):
    print("============== < QUESTION4 > =============")
    print("5.) what is the first website of facebook? ")
    print("a.) paypal")
    print("b.) youtube")
    print("c.) facemash")
    print("d.) netflix")

    input_ans5 = input("Enter your answer here: ").lower()
    if input_ans5 == "c":
        print("============================")
        print("correct answer!")
        print("============================")
        scores += 1
        print(f"Nickname:{nickname}")
        print(f"Remaining life:{life}")
        print(f"score: {scores}")
        total_score(nickname,life,scores)

    else:
        print("============================")
        print("correct answer!")
        print("============================")
        scores -= 1
        print(f"Nickname:{nickname}")
        print(f"Remaining life:{life}")
        print(f"score: {scores}")
        total_score(nickname,life,scores)



def question4(nickname,life,scores):
    print("============== < QUESTION4 > =============")
    print("4.) who is the founder of spaceX? ")
    print("a.) Thomas edison")
    print("b.) bill gates")
    print("c.) mark zuckerberg")
    print("d.) elon musk")

    input_ans4 = input("Enter your answer here: ").lower()
    if input_ans4 == "d":
        print("============================")
        print("correct answer!")
        print("============================")
        scores += 1
        print(f"Nickname:{nickname}")
        print(f"Remaining life:{life}")
        print(f"score: {scores}")
        question5(nickname, life, scores)
    else:
        print("============================")
        print("wrong answer!")
        print("============================")
        scores -= 1
        print(f"Nickname:{nickname}")
        print(f"Remaining life:{life}")
        print(f"score: {scores}")
        question5(nickname, life, scores)

def question3(nickname,life,scores):
    print("============== < QUESTION3 > =============")
    print("3.) what is in the middle of blackhole?")
    print("a.) singularity")
    print("b.) water ")
    print("c.) time")
    print("d.) space ")

    input_ans3 = input("Enter your answer here: ").lower()

    if input_ans3 == "a":
        print("============================")
        print("correct answer!")
        print("============================")
        scores += 1
        print(f"Nickname:{nickname}")
        print(f"Remaining life:{life}")
        print(f"score: {scores}")
        question4(nickname, life, scores)

    else:
        print("============================")
        print("wrong answer!")
        print("============================")
        scores -= 1
        print(f"Nickname:{nickname}")
        print(f"Remaining life:{life}")
        print(f"score: {scores}")
        question4(nickname, life, scores)


input_nickname = input("Enter your nickname here:").lower()
def question2(nickname,life,scores):
    print("============== < QUESTION2 > =============")
    print("2.) Who painted mona lisa?")
    print("a.) leonardo di sir piero da vinci")
    print("b.) albert einstein")
    print("c.) robert hooke")
    print("d.) elon musk")

    input_ans2 = input("Enter your answer here: ").lower()
    if input_ans2 == "a":
        print("============================")
        print("correct answer!")
        print("============================")
        scores += 1
        print(f"Nickname:{nickname}")
        print(f"Remaining life:{life}")
        print(f"score: {scores}")
        question3(nickname,life,scores)
    else:
        print("============================")
        print("wrong answer!")
        print("============================")
        life -= 1
        print(f"Nickname:{nickname}")
        print(f"Remaining life:{life}")
        print(f"score: {scores}")
        question3(nickname,life,scores)


class Game:
    def __init__(self,nickname):
        self.life = 5
        self.nickname = input_nickname
        self.scores = 0



    def welcome(self):
        print("============ Quest4Bot ===============")
        print(f"Welcome to Q/A game!{self.nickname}")
        print("1.) play?")
        print("2.) Nickname")

        while True:
            try:
                input_user = int(input("Enter your input here:"))
                if input_user == 1:
                    play(self.nickname, self.life, self.scores)
                    break
                elif input_user == 2:
                    nickname1(self.nickname,self.life,self.scores)
                    break
                else:
                    print("you inputted a wrong credentials, please try again...")
            except ValueError:
                print("wrong credentials, please try again...")

def welcome2(nickname,life,scores):
    print("============ Quest4Bot ===============")
    print(f"Welcome to Q/A game!{nickname}")
    print("1.) play?")
    print("2.) Nickname")

    while True:
        try:
            input_user = int(input("Enter your input here:"))
            if input_user == 1:
                play(nickname, life, scores)
                break
            elif input_user == 2:
                nickname1(nickname,life,scores)
                break
            else:
                print("you inputted a wrong credentials, please try again...")
        except ValueError:
                print("wrong credentials, please try again...")
def start(nickname,life,scores):
    print("============== < QUESTION1 > =============")
    print("who is the father of classical science?")
    print("a.) isaac newton")
    print("b.) charles darwin ")
    print("c.) leonardo di sir piero da vinci")
    print("d.) nikola tesla ")

    while True:
        try:
            input_ans = input("Enter your answer here: ").lower()

            if input_ans == "b":
                print("============================")
                print("correct answer!")
                scores += 1
                print("============================")
                print(f"Nickname:{nickname}")
                print(f"Remaining life:{life}")
                print(f"score: {scores}")
                question2(nickname,life,scores)
                break
            else:
                print("============================")
                print("wrong answer!")
                print("============================")
                life -= 1
                print("============================")
                print(f"Nickname:{nickname}")
                print(f"Remaining life:{life}")
                print(f"score: {scores}")
                question2(nickname, life, scores)
                break
        except ValueError:
            print("wrong credentials, please try again...")


def play(nickname, life, scores):
    print(f"hello! {nickname}, goodluck! <3")
    while True:
        try:
            input_back = input("start (yes or no): ").lower()

            if input_back == "yes":
                start(nickname,life,scores)
                break
            elif input_back == "no":
                play(nickname, life, scores)
                break
            else:
                print("wrong credentials, please try again...")

        except ValueError:
            print("wrong credentials, please try again...")

p = Game(input_nickname)
p.welcome()
