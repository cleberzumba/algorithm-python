# Programming Logic with Python

From Algorithm Studies in Python to Problem-Solving Skills. In my studies of algorithms and scientific computing in Python, I developed an algorithm that:

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
```

---

## Usage Example

```python
text = 'mrttaqrhknsw ih puggrur' 
custom_key = 'happycoding'

print(f'Encrypted text: {text}') 
print(f'Key: {custom_key}') 
decryption = decrypt(text, custom_key) 
print(f'Decrypted text: {decryption}')
```

---

## Output:

```python
Encrypted text: mrttaqrhknsw ih puggrur
Key: happycoding
Decrypted text: programming is awesome
```

---

## Concepts Practiced

- Programming logic and problem-solving
- Variables and functions.
- Loops (for).
- Conditional statements (if).
- Index mapping.
- Modular arithmetic.

---

## Conclusion

Although simple, this algorithm was an excellent exercise to strengthen analytical thinking, logical reasoning, and problem decomposition skills, while working with loops, conditionals, string manipulation, and modular arithmetic.



