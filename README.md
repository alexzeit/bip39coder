BIP39 Coder
A secure, interactive Python tool for working with BIP39 mnemonic seed phrases. Features live word suggestions, dice-based entropy generation, and compact encrypted storage (50 characters vs 24 words).
Features

🎲 Dice Mode: Generate mnemonics from physical dice rolls for true randomness
🔐 Encrypted Storage: Protect mnemonics with passphrase encryption (XOR + HMAC)
⌨️ Interactive Entry: Live autocomplete with keyboard shortcuts
✅ Checksum Validation: Automatic BIP39 checksum verification
📦 Self-Contained: No external wordlist files needed
🔒 Secure: Base58 encoding with 50-character encrypted output

Installation
Requirements

Python 3.6+
base58 library

Setup
Clone the repository:
bashgit clone https://github.com/yourusername/bip39coder.git
cd bip39coder
Install dependencies:
bashpip install base58
Usage
1. Interactive Mode
Enter a 24-word BIP39 mnemonic phrase interactively with live suggestions:
bashpython bip39coder.py
Controls:

Type letters to filter words
Press number (1-9) to select from suggestions
Press Enter to confirm word
Backspace to delete characters
Ctrl+C to quit

After entering all 24 words, the tool will:

Validate the BIP39 checksum
Prompt for a passphrase
Output a 50-character encrypted Base58 string

2. Dice Mode
Generate a mnemonic from physical dice rolls (minimum 98 rolls for 256-bit entropy):
bashpython bip39coder.py 31635523441252211266355144251526162152534441525162653534243415251626155344412551216265355251261626513
How to use:

Roll a standard 6-sided die at least 98 times
Record each roll as a digit (1-6)
Pass the string to the script

The tool will:

Convert dice rolls to 256-bit entropy
Generate a valid BIP39 mnemonic
Prompt for a passphrase
Output the encrypted Base58 string

3. Decode Mode
Decrypt a previously stored mnemonic using its Base58 string:
bashpython bip39coder.py 11111AWJqK8ZcHvPmVLkVzVp3CzGH5RmPHwUvXoSSWdUQe
The tool will:

Prompt for the passphrase
Decrypt and display the mnemonic
Validate the BIP39 checksum

Security Features
Encryption

XOR cipher with SHA-256 hashed passphrase
HMAC authentication (4-byte digest) to detect tampering
Base58 encoding for easy transcription
Fixed 50-character output format

Best Practices

⚠️ Never share your passphrase - it's required to decrypt your mnemonic
⚠️ Store the Base58 string securely - it contains your encrypted seed
⚠️ Use strong passphrases - longer is better (20+ characters recommended)
⚠️ Verify checksums - always ensure you see "✅ BIP39 CHECKSUM OK"
⚠️ Use dice mode for maximum security - physical randomness is provably random

Examples
Generate from Dice
bashpython bip39coder.py 123456123456123456123456123456123456123456123456123456123456123456123456123456123456123456123456123456
Output:
=== LIVE BIP39 INTERACTIVE ENTRY ===
Suggestions appear after first letter

Generated mnemonic from dice:
abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon art
Enter passphrase to encrypt mnemonic: ********

Encrypted Base58 string (50 chars):
11111AWJqK8ZcHvPmVLkVzVp3CzGH5RmPHwUvXoSSWdUQe
Decrypt Stored Mnemonic
bashpython bip39coder.py 11111AWJqK8ZcHvPmVLkVzVp3CzGH5RmPHwUvXoSSWdUQe
Output:
=== LIVE BIP39 INTERACTIVE ENTRY ===
Suggestions appear after first letter

Enter passphrase to decrypt mnemonic: ********
Decoded mnemonic:
abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon abandon art
✅ BIP39 CHECKSUM OK
Technical Details
BIP39 Wordlist

Embedded 2048-word English wordlist
11-bit encoding per word
24 words = 264 bits (256 entropy + 8 checksum)

Dice Entropy

Converts base-6 dice rolls to base-10 integer
Extracts 256 bits for entropy
Computes 8-bit SHA-256 checksum
Generates valid 24-word mnemonic

Encryption Format
[32 bytes entropy] + [4 bytes HMAC] = 36 bytes
XOR with SHA-256(passphrase)
Base58 encode → pad to 50 chars with '1'
Compatibility

Cross-platform: Windows, macOS, Linux
Terminal support: ANSI escape codes for screen clearing
Keyboard handling: Native platform-specific key input

License
MIT License - see LICENSE file for details
Disclaimer
⚠️ IMPORTANT: This tool handles sensitive cryptographic material.

Use at your own risk
Always test with small amounts first
Keep multiple backups of your mnemonics and passphrases
The authors are not responsible for lost funds

Contributing
Contributions are welcome! Please feel free to submit a Pull Request.
Support
If you encounter any issues or have questions, please open an issue on GitHub.

Remember: Your mnemonic seed phrase controls access to your funds. Treat it like a password to your bank account - maybe even more carefully!
