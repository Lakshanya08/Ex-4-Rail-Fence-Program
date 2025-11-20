# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM:
```
msg = input("Enter the message: ").replace(" ", "").upper()
rails = int(input("Enter number of rails: "))

zig = list(range(rails)) + list(range(rails-2, 0, -1))
cipher = ""
for r in range(rails):
    for i, ch in enumerate(msg):
        if zig[i % len(zig)] == r:
            cipher += ch

print("Encrypted Text:", cipher)

pattern = [zig[i % len(zig)] for i in range(len(cipher))]

plain = [""] * len(cipher)
idx = 0
for r in range(rails):
    for i in range(len(cipher)):
        if pattern[i] == r:
            plain[i] = cipher[idx]
            idx += 1

print("Decrypted Text:", "".join(plain))
```
# OUTPUT:
<img width="548" height="108" alt="image" src="https://github.com/user-attachments/assets/da9d9d65-6683-433e-a1b5-805f1ee774e0" />


# RESULT:
Thus the implementation of vigenere cipher had been executed successfully.
