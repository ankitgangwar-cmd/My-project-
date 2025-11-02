import random

w = random.choice(["python", "coding", "hangman", "dev", "game"])
g, t = [], 6

print("_ " * len(w))

while t:
    x = input("Letter: ").lower()
    if len(x) != 1 or not x.isalpha() or x in g:
        continue
    g.append(x)
    if x not in w:
        t -= 1
        print("Tries:", t)
    print(" ".join(c if c in g else "_" for c in w))
    if all(c in g for c in w):
        print("Win!", w)
        break
else:
    print("Lose!", w)
