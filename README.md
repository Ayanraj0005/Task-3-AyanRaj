# Enterprise Random Password Generator

A secure Python-based password generator that creates cryptographically strong random passwords and calculates their entropy score based on password length and character pool size.

This project uses Python's built-in `secrets` module, which is designed for generating passwords, authentication tokens, and security-sensitive data.

## Features

- Generates secure random passwords
- Uses cryptographically secure randomness (`secrets` module)
- Supports custom password lengths
- Includes:
  - Uppercase letters (A-Z)
  - Lowercase letters (a-z)
  - Numbers (0-9)
  - Special characters (!@#$%^&*)
- Calculates password entropy
- User-friendly command-line interface
- Basic input validation

---

## Technologies Used

- Python 3
- `secrets`
- `string`
- `math`

---

## Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/random-password-generator.git
```

Navigate to the project folder:

```bash
cd random-password-generator
```

Run the program:

```bash
python Random_password_generator.py
```

---

## Usage

When executed, the program asks for the desired password length.

Example:

```text
--- Enterprise Random Password Generator ---
Enter desired password length (Min 15 recommended per NIST 2024): 15

[+] SUCCESS: Credentials Generated
Password: wM@mrdx9S[oe&]
Entropy Score: 98.32 bits
```

---

## Sample Outputs

### Length: 8

```text
Password: 1+Gsu;)0
Entropy Score: 52.44 bits
```

### Length: 9

```text
Password: _\8::!=Il
Entropy Score: 58.99 bits
```

### Length: 15

```text
Password: wM@mrdx9S[oe&]
Entropy Score: 98.32 bits
```

---

## How Entropy Is Calculated

The entropy formula used is:

```text
Entropy = Length × log₂(Character Pool Size)
```

Where:

- Length = Password length
- Character Pool Size = Total available characters

For this project:

```python
letters = string.ascii_letters
digits = string.digits
symbols = string.punctuation
```

Total character pool:

```text
52 letters + 10 digits + 32 symbols = 94 characters
```

Example:

```text
15 × log₂(94) = 98.32 bits
```

Higher entropy means stronger resistance against brute-force attacks.

---

## Project Structure

```text
random-password-generator/
│
├── Random_password_generator.py
└── README.md
```

---

## Functions

### calculate_entropy()

Calculates the theoretical entropy of the generated password.

```python
calculate_entropy(length, pool_size)
```

Returns:

```python
float
```

---

### generate_password()

Generates a secure password using the `secrets` module.

```python
generate_password(length)
```

Returns:

```python
(password, entropy_score)
```

---

## Security Notes

This project uses:

```python
secrets.choice()
```

instead of:

```python
random.choice()
```

because the `secrets` module is specifically designed for cryptographic and security-related applications.

Recommended password length:

```text
15+ characters
```

as suggested by modern security guidelines.

---

## Error Handling

If invalid input is provided:

```text
Enter desired password length (Min 15 recommended per NIST 2024): abc

[!] Input Error: invalid literal for int() with base 10: 'abc'
```

---

## Future Improvements

- Enforce minimum password length
- Allow users to choose character sets
- Exclude ambiguous characters (O, 0, l, I)
- Password strength rating
- Copy password directly to clipboard
- Save generated passwords securely
- GUI version using Tkinter
- Generate multiple passwords at once

---

## Learning Concepts Demonstrated

- Functions
- Cryptographic randomness
- String manipulation
- Mathematical calculations
- User input handling
- Exception handling
- Secure password generation
- Python standard libraries

---

## Example Command

```bash
python Random_password_generator.py
```

---

## Author

Created as a cybersecurity-focused Python project demonstrating secure password generation and entropy analysis using cryptographically secure randomization.
