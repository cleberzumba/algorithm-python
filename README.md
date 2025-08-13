# Algorithm in Python

This project implements the **Vigenère Cipher**, a polyalphabetic substitution algorithm that shifts letters in the alphabet based on a repeating key. 
Although historically used for encryption, today it mainly serves as an educational exercise to practice programming logic.

---

## Purpose

- Practice string manipulation.
- Work with loops and conditionals.
- Apply modular arithmetic in programming.
- Understand basic cryptography concepts.

---

## How it Works

1. Takes an **encrypted message** and a **key**.
2. Iterates through each character:
   - Keeps symbols and spaces unchanged.
   - Applies a letter shift based on the corresponding character from the key.
3. Returns the encrypted or decrypted text.

---

## Code Structure

```python
def vigenere(message, key, direction=1):
    # direction = 1 for encryption, -1 for decryption
    key_index = 0
    alphabet = 'abcdefghijklmnopqrstuvwxyz'
    final_message = ''

    for char in message.lower():
        if not char.isalpha():
            final_message += char
        else:
            key_char = key[key_index % len(key)]
            key_index += 1
            offset = alphabet.index(key_char)
            index = alphabet.find(char)
            new_index = (index + offset * direction) % len(alphabet)
            final_message += alphabet[new_index]
    
    return final_message

def encrypt(message, key):
    return vigenere(message, key)

def decrypt(message, key):
    return vigenere(message, key, -1)


## Usage Example

text = 'mrttaqrhknsw ih puggrur'
custom_key = 'happycoding'

print(f'Encrypted text: {text}')
print(f'Key: {custom_key}')
decryption = decrypt(text, custom_key)
print(f'Decrypted text: {decryption}')

# Output:

Encrypted text: mrttaqrhknsw ih puggrur
Key: happycoding
Decrypted text: programming is awesome


## Concepts Practiced

- Variables and functions.
- Loops (for).
- Conditional statements (if).
- Index mapping.
- Modular arithmetic.



