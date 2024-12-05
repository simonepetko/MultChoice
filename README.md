import random
def create_questions():
    return {
        "Oxygen gas formula?": "O2",
        "How fast is gravity's acceleration?": "9.81 m/s^2",
        "Largest planet?": "Jupiter",
        "Water formula?": "H2O",
        "How fast is the speed of light?":"3.00E8 m/s",
        "How much is 36 ft in meters?":"10.97 m/s",
        "What house pets are considered 'felines?'":"Cats",
        "What house pets are considered 'canines?'":"Dogs",
        "What house pets are considered 'reptiles?'":"Snakes, Lizards, And other scaly creatures.",
        "What planet is considered a dwarf planet?":"Pluto",
        "What is another way to say 9 million?":"9.00E6"
    }
def play_game(questions):
    score = 0
    items = list(questions.items())
    random.shuffle(items)

    for question, correct_answer in items:
        print(question)
        choices = [correct_answer] + random.sample([v for k, v in questions.items() if v != correct_answer], 4)
        random.shuffle(choices)
    
        for i, option in enumerate(choices):
        print(f"{i + 1}. {option}")

        try:
            answer = int(input("Type your choice (1-5): ")) - 1
            if choices[answer] == correct_answer:
                print("Correct!")
                score += 10
            else:
                print(f"Wrong. The answer is {correct_answer}.")
        except (ValueError, IndexError):
            print("Invalid input.")

    print(f"\nFinal score: {score}/{len(questions)}0")
    if score/len(questions)>=10:
        print("Great job!")
    else:
        print("Better luck next time!")
if __name__ == "__main__":
    play_game(create_questions())
