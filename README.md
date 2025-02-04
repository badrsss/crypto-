# crypto-
git clone https://github.com/badrsss/crypto-project.git
cd crypto-project
mkdir src tests
touch src/main.py tests/test_main.py
def encrypt(text, shift):
    encrypted_text = ""
    for char in text:
        if char.isalpha():
            shift_amount = 65 if char.isupper() else 97
            encrypted_text += chr((ord(char) + shift - shift_amount) % 26 + shift_amount)
        else:
            encrypted_text += char
    return encrypted_text

def decrypt(text, shift):
    return encrypt(text, -shift)

if __name__ == "__main__":
    message = "Hello, World!"
    shift = 4
    encrypted_message = encrypt(message, shift)
    print(f"Encrypted: {encrypted_message}")
    decrypted_message = decrypt(encrypted_message, shift)
    print(f"Decrypted: {decrypted_message}")
import unittest
from src.main import encrypt, decrypt

class TestCrypto(unittest.TestCase):
    def test_encrypt(self):
        self.assertEqual(encrypt("ABCD", 1), "BCDE")
        self.assertEqual(encrypt("abcd", 1), "bcde")
        self.assertEqual(encrypt("Hello, World!", 4), "Lipps, Asvph!")

    def test_decrypt(self):
        self.assertEqual(decrypt("BCDE", 1), "ABCD")
        self.assertEqual(decrypt("bcde", 1), "abcd")
        self.assertEqual(decrypt("Lipps, Asvph!", 4), "Hello, World!")

if __name__ == "__main__":
    unittest.main()
    import unittest
from src.main import encrypt, decrypt

class TestCrypto(unittest.TestCase):
    def test_encrypt(self):
        self.assertEqual(encrypt("ABCD", 1), "BCDE")
        self.assertEqual(encrypt("abcd", 1), "bcde")
        self.assertEqual(encrypt("Hello, World!", 4), "Lipps, Asvph!")

    def test_decrypt(self):
        self.assertEqual(decrypt("BCDE", 1), "ABCD")
        self.assertEqual(decrypt("bcde", 1), "abcd")
        self.assertEqual(decrypt("Lipps, Asvph!", 4), "Hello, World!")

if __name__ == "__main__":
    unittest.main()
    git add .
git commit -m "Initial commit with crypto functions and tests"
git push origin main
# Crypto Project

This is a simple Python project demonstrating encryption and decryption using the Caesar Cipher algorithm.

## Usage

```bash
python src/main.py
python -m unittest discover tests
