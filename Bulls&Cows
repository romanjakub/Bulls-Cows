import random

# vygenerovat nahodne cislo od pocitace s podminkama, aby nezacalo nulou a aby se cisla neopakovala
def nahodne_cislo():
    while True:
        cislo = random.sample('1234567890', 4)
        if cislo[0] != '0':
            return ''.join(cislo)

# zkontrolovat pravidla
def kontrola(user):
    if len(user) != 4:
        return "The number must be 4 digits."
    if not user.isdigit():
        return "Digits only."
    if len(set(user)) != len(user):
        return "Digits can not be duplicated."
    if user[0] == '0':
        return "The number must not start with 0."
    return None

# pouzivani spravneho tvaru bulls and cows pro cisla
def vyhodnoceni(user, computer):
    bulls = sum(1 for i in range(4) if user[i] == computer[i])
    cows = sum(1 for i in range(4) if user[i] != computer[i] and user[i] in computer)

    if bulls == 1:
        bulls_text = "bull"
    else:
        bulls_text = "bulls"
    
    if cows == 1:
        cows_text = "cow"
    else:
        cows_text = "cows"
    
    return bulls, bulls_text, cows, cows_text
    

def game():
    print('''Hi there!
-----------------------------------------------
I've generated a random 4 digit number for you.
Let's play a bulls and cows game.
-----------------------------------------------''')
    
    computer = nahodne_cislo()
    attempts = 0
    
    while True:
        user = input("Enter a number: ")
        attempts += 1
        chyba = kontrola(user)
        if chyba:
            print(chyba)
            continue

        
        bulls, bulls_text, cows, cows_text = vyhodnoceni(user, computer)
        
        print(f"{bulls} {bulls_text}, {cows} {cows_text}.")
        
        if bulls == 4:
            print(f"Correct, you've guessed the right number in {attempts} guesses!")
            break

# zacit hru
game()
