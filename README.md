# Lab-Exercise---5---Rail-fence


# AIM

To develop a simple C program to implement Rail Fence Cipher.

# ALGORITHM

1. Start the program.

  
2. Get the plaintext and number of rails from the user.

 
3. Create a matrix based on the number of rails and plaintext length.

   
4. Write the plaintext in a zigzag pattern diagonally downwards.

 
5. When the bottom rail is reached, change the direction upwards.


6. Continue writing the characters in a zigzag pattern.

    
7. When the top rail is reached, change the direction downwards again.

 
8. Read the characters row by row to obtain the encrypted text.

 
9. Display the plaintext and encrypted text.


10. Stop the program.

# PROGRAM

```

def rail_fence_encrypt(text, rails):
    fence = [['\n' for _ in range(len(text))]
             for _ in range(rails)]

    row = 0
    direction = 1

    for col, char in enumerate(text):
        fence[row][col] = char

        if row == 0:
            direction = 1
        elif row == rails - 1:
            direction = -1

        row += direction

    encrypted_text = ""

    for row in fence:
        for char in row:
            if char != '\n':
                encrypted_text += char

    return encrypted_text


message = input("Enter the plaintext: ")
rails = int(input("Enter the number of rails: "))

ciphertext = rail_fence_encrypt(message, rails)

print("Plaintext:", message)
print("Encrypted text:", ciphertext)

```

# OUTPUT


<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/94f5040b-9509-4c9a-864a-9427b552a865" />



# RESULT


The Rail Fence Cipher program is executed successfully.

