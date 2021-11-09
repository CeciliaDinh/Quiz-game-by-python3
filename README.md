# Quiz-game-by-python3
def new_game():
    guesses = []
    correct_guess = 0
    question_num = 1
    for key in questions:
        print("__________________")
        print(key)
        for i in options[question_num - 1]:
            print(i)
        guess = input("Enter A/B/C/D").upper()
        guesses.append(guess)
        correct_guess += check_q(questions.get(key), guess)
        question_num += 1


def display_score(correct_guess, guesses):
    print("_________________")
    print("Result is:", end="")
    print("__________________")
    print("Answer:", end="")
    for i in questions:
        print(questions.get(i), end="")
    print("_________________________________")
    print("Guesses:", end="")
    for i in guesses:
        print(i, end=" ")
    print()
    scores = int((correct_guess / len(questions)) * 100)
    print(f"Your score is {scores} %")


def score():
    pass


def check_q(answers, guess):
    if answer == guess:
        print("Correct! You snailed it!")
        return 1
    else:
        print("You lost")
        return 0

    pass


def play_again():
    response = input("Shall we play again? YES/NO").upper()
    if response != "YES":
        return True
    return False


answer = input("Your answer is:")
questions = {
    "Who created Python?:": "A",
    "What year was Python created?:": "B",
    "Python is attributed to which comedy group": "C",
    "Is the earth round?:": "A"

}
options = {["A.Guido van Rossum", "B.Elon Musk",
            "C. Mark Zuckerberg", "D. Hang"],
           ["A.1989", "B.1991", "C.2000", "D.2003"],
           ["A.Lonely Island", "B.mosh", "C.Vietnam",
            "D.singapore"],
           ["A.True", "B.False", "C.sometimes",
           "D. What a stupid question"]}

while play_again():
    new_game()
print("bye")
