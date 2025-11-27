# BIP39 Offline Coder

A secure, offline-capable HTML tool for working with BIP39 mnemonic seed phrases. Features live word suggestions, dice-based entropy generation, compact encrypted Base58 storage, and a clever privacy feature to disguise your seed as a fake Linux license.

## Features

- 🎲 **Dice Mode**: Generate mnemonics from physical dice rolls for true randomness
- 🔐 **Encrypted Storage**: Protect mnemonics with passphrase encryption (XOR + HMAC)
- ⌨️ **Interactive Entry**: Live autocomplete with 24-word input fields
- ✅ **Checksum Validation**: Automatic BIP39 checksum verification
- 📦 **Self-Contained**: Embedded 2048-word BIP39 wordlist, no external dependencies
- 🔒 **Secure**: Base58 encoding with compact encrypted output
- 🐧 **Privacy Feature**: Disguise your seed as a "Linux Enterprise License" business card
- 🖨️ **Print-Ready**: Business card format (3.5" x 2") with QR codes
- 💾 **Export Options**: Save as PNG or print directly
- 🌐 **Fully Offline**: Works without internet connection - download and run locally

## Quick Start

### Download and Run

1. Download all files to your computer:
   - `bip39coder.html`
   - `qrcode.min.js`
   - `html2canvas.min.js`

2. **Go offline** - Disconnect WiFi and Bluetooth, or enable airplane mode

3. Open `bip39coder.html` in your web browser (works in Chrome, Firefox, Safari, Edge)

4. Use the tool completely offline for maximum security

⚠️ **SECURITY REMINDER**: Always use this tool offline. Download it, disconnect from the internet, then use it.

## Usage Guide

### 1. Generate BIP39 from Dice Rolls

The most secure method - uses physical dice for true randomness:

1. Roll a standard 6-sided die at least 98 times
2. Record each roll (1-6) as a continuous string
3. Paste into the "Dice Rolls" field
4. Click "Generate BIP39 Mnemonic"

**Example:**
```
123456123456123456123456123456123456123456123456123456123456123456123456123456123456123456123456123456
```

The tool will:
- Generate a valid 24-word BIP39 mnemonic
- Automatically fill the words into the BIP39 Checker
- Validate the checksum
- Display a QR code

### 2. Validate BIP39 Checksum

Enter or verify your 24-word mnemonic:

1. Type words into the 24 input fields
2. Live suggestions appear as you type (press number key or click to select)
3. Click "Validate BIP39 Checksum"
4. See ✅ **BIP39 CHECKSUM OK** or ❌ **CHECKSUM FAILED**

### 3. Encrypt to Base58

Convert your 24-word mnemonic into a compact, encrypted format:

1. Enter your 24-word BIP39 mnemonic
2. Enter a strong passphrase (20+ characters recommended)
3. Click "Encrypt to Base58"
4. Receive a compact Base58 string (formatted in 5-character blocks)
5. QR code is generated for easy scanning

**Output example:**
```
4sHNd ku9Mr U2tKp gXbVm 7YSCA wZzJh nQPRx mT8vF j5LcG eW3Bk
```

⚠️ **IMPORTANT**: The encrypted Base58 string **CANNOT** be used directly in crypto wallets! Its purpose is only for secure storage on paper or electronic devices where it won't be recognized as a wallet seed. To use it in a wallet, you must first decrypt it back to the 24-word mnemonic using section 4 (Decrypt Base58 to BIP39) with your passphrase.

### 4. Privacy Feature: Linux License Disguise

**💡 Privacy Tip**: After encrypting your seed, you can disguise it as a fake "Linux Enterprise License" that looks like a technical business card.

**Why use this?**
- ✅ Carry your seed safely in your wallet
- ✅ Nobody suspects it's a crypto wallet seed
- ✅ Looks like a boring IT license key
- ✅ Plausible deniability
- ✅ Business card size (3.5" x 2")
- ✅ Includes QR code for easy scanning

**How to use:**
1. After encrypting your seed, click "🐧 Show as Linux License"
2. View the professional-looking license card
3. Options:
   - 💾 **Save as PNG** - Download as image file
   - 🖨️ **Print** - Print on business card paper
   - ✕ **Close** - Return to main view

**What it contains:**
- License Type: "Premium Support Subscription"
- License Key: Your encrypted Base58 seed (with line breaks)
- QR Code: Scannable version of your key
- Professional gradient design with warning footer

### 5. Decrypt Base58 to BIP39

Recover your original mnemonic from the encrypted Base58 string:

1. Paste your Base58 string (with or without spaces)
2. Enter the same passphrase you used for encryption
3. Click "Decrypt to BIP39"
4. See your 24-word mnemonic restored
5. Checksum is automatically validated

## Security Features

### Why Encrypted Base58 is Better Than Plain Text

Writing your 24-word seed phrase on paper has significant risks:

- **Physical theft**: Anyone who finds your paper has complete access to your funds
- **Accidental discovery**: Family members, roommates, or visitors could stumble upon it
- **No deniability**: The words are immediately recognizable as a crypto seed phrase
- **Easy to photograph**: Someone can quickly snap a photo without your knowledge
- **Difficult to split**: Splitting 24 words safely requires complex schemes

**Encrypted Base58 advantages:**

- ✅ **Useless without passphrase**: The Base58 string is worthless to anyone who doesn't know your passphrase
- ✅ **Plausible deniability**: Looks like random characters, not obviously a crypto wallet
- ✅ **Compact**: ~50 characters vs 200+ characters for 24 words
- ✅ **Tamper detection**: HMAC ensures any modification is immediately detected
- ✅ **Memory-based security**: Your passphrase can be memorized or stored separately
- ✅ **Easy to split**: Store the Base58 string in one location and passphrase in another
- ✅ **Disguisable**: Use the Linux License feature to hide in plain sight

**Best practice**: 
1. Write down the Base58 string (or print as Linux License)
2. Store your passphrase separately (or memorize it)
3. An attacker needs BOTH to access your funds

### Encryption Details

- **XOR cipher** with SHA-256 hashed passphrase
- **HMAC authentication** (4-byte digest) to detect tampering
- **Base58 encoding** for easy transcription and QR compatibility
- **Format**: `[32 bytes entropy] + [4 bytes HMAC] = 36 bytes → Base58 encoded`

### Best Practices

- ⚠️ **Go offline before use** - Disconnect WiFi and Bluetooth, or enable airplane mode
- ⚠️ **Never share your passphrase** - it's required to decrypt your mnemonic
- ⚠️ **Store backups securely** - Keep multiple copies in separate locations
- ⚠️ **Use strong passphrases** - 20+ characters recommended (mix letters, numbers, symbols)
- ⚠️ **Verify checksums** - always ensure you see "✅ BIP39 CHECKSUM OK"
- ⚠️ **Use dice mode for maximum security** - physical randomness is provably random
- ⚠️ **Test before trusting** - Practice the full encrypt/decrypt cycle with test data first
- ⚠️ **Clear browser cache** - After use, clear browser history and cached data
- ⚠️ **Print on private printer** - If printing the Linux License, use a personal printer

## Technical Details

### BIP39 Wordlist

- Embedded 2048-word English wordlist
- 11-bit encoding per word
- 24 words = 264 bits (256 entropy + 8 checksum)
- Full wordlist included in HTML file

### Dice Entropy

- Converts base-6 dice rolls to base-10 integer
- Uses last 99 digits for 256-bit entropy extraction
- Computes 8-bit SHA-256 checksum
- Generates valid 24-word mnemonic

### QR Code Generation

- Uses `qrcode.min.js` library
- Error correction level: High (H)
- Display version: 150x150px
- Print version: 64x64px (optimized for business card)
- Encodes Base58 string without spaces

### Linux License Card Format

- **Print size**: 3.5" x 2" (standard US business card)
- **Card dimensions**: 3.1" x 1.7" (with cutting margin)
- **Layout**: Two-column flex layout (text + QR code)
- **QR code**: 0.64" x 0.64" with 0.03" padding
- **Font sizes**: Optimized for readability (5.5pt - 10pt)
- **Cut guides**: Dashed border lines for precision cutting
- **Gradient**: Purple gradient (#667eea to #764ba2)

## Browser Compatibility

- ✅ **Chrome/Edge** (Chromium-based) - Fully supported
- ✅ **Firefox** - Fully supported
- ✅ **Safari** - Fully supported
- ✅ **Opera** - Fully supported
- ⚠️ **Internet Explorer** - Not supported (use modern browser)

## Dependencies

All dependencies are included in the download:

- **qrcode.min.js** - QR code generation library
- **html2canvas.min.js** - PNG export functionality
- No external API calls
- No internet connection required

## File Structure

```
bip39coder.html         - Main application file
qrcode.min.js          - QR code generation library
html2canvas.min.js     - Canvas to PNG conversion
LICENSE                - MIT License
README.md              - This file
```

## Privacy & Security Considerations

### Offline Usage

This tool is designed to work completely offline:

1. Download all files to a USB drive or local folder
2. Disconnect from the internet
3. Open `bip39coder.html` in your browser
4. Use all features without any network connection
5. Clear browser data when finished

### No Data Transmission

- **Zero tracking**: No analytics, no cookies, no external requests
- **Local only**: All computation happens in your browser
- **No storage**: Data is not saved to disk (except when you explicitly save/print)
- **No cloud**: Everything stays on your device

### Threat Model

**What this protects against:**
- ✅ Network attacks (use offline)
- ✅ Physical theft of seed phrase (encrypted + disguised)
- ✅ Casual discovery (looks like a boring license)
- ✅ Data tampering (HMAC verification)
- ✅ Weak randomness (dice-based entropy)

**What this does NOT protect against:**
- ❌ Keyloggers or malware on your computer
- ❌ Screen recording or shoulder surfing
- ❌ Physical theft of BOTH the Base58 string AND passphrase
- ❌ Weak passphrases that can be brute-forced
- ❌ Compromised computer or browser

**Best practice**: Use a clean, offline computer for maximum security.

## Use Cases

### 1. Cold Storage Setup
Generate a new wallet offline, encrypt the seed, print as Linux License, store safely.

### 2. Seed Phrase Backup
Convert existing 24-word seed to encrypted Base58, disguise as license, keep in wallet.

### 3. Travel Security
Carry your encrypted seed disguised as a mundane business card, memorize passphrase.

### 4. Inheritance Planning
Leave the Linux License card in a safe place, store passphrase separately or with trusted person.

### 5. Plausible Deniability
If confronted, it looks like a boring IT license key, not a crypto wallet.

## Frequently Asked Questions

**Q: Is this safe to use?**  
A: Yes, when used offline on a clean computer. Download the files, disconnect from the internet, and use it locally.

**Q: What if I forget my passphrase?**  
A: Your Base58 string is useless without the passphrase. There is NO recovery mechanism. Choose memorable but strong passphrases.

**Q: Can I use any passphrase?**  
A: Yes, but longer is better. Use 20+ characters with a mix of letters, numbers, and symbols.

**Q: Why 98 dice rolls?**  
A: 98 rolls in base-6 provides sufficient entropy for 256 bits of randomness (6^99 > 2^256).

**Q: Is the Linux License feature secure?**  
A: Yes! It's just a different display format for the same encrypted Base58 string. The encryption is identical.

**Q: Can I use the Base58 string directly in my wallet?**  
A: No! The encrypted Base58 string is for secure storage only. You cannot import it directly into any crypto wallet. To use your funds, you must first decrypt the Base58 string back to the 24-word mnemonic using your passphrase (section 4), then import those words into your wallet.

**Q: Can I print multiple copies?**  
A: Yes, but store them securely. Each printed card contains your encrypted seed.

**Q: What paper should I use for printing?**  
A: Standard business card paper (250-300 GSM cardstock) works well. Available at office supply stores.

**Q: Can someone scan the QR code and steal my funds?**  
A: No! The QR code contains the encrypted Base58 string. Without your passphrase, it's useless.

**Q: Should I laminate the printed card?**  
A: Yes, lamination protects against water damage and wear. Just ensure the QR code remains scannable.

**Q: Can I use this for other wallet types?**  
A: This tool works with any BIP39-compatible wallet (Bitcoin, Ethereum, etc.). The mnemonic is standard.

## Troubleshooting

**Issue**: QR code won't scan  
**Solution**: Ensure good lighting, clean camera lens, and hold steady. Try increasing brightness on screen.

**Issue**: Print size doesn't match business card  
**Solution**: In print dialog, ensure "Scale" is set to 100% and margins are set to "None" or "Minimum".

**Issue**: Words don't autocomplete  
**Solution**: Type at least one letter. Suggestions show matches from the BIP39 wordlist.

**Issue**: Checksum validation fails  
**Solution**: Re-check all 24 words carefully. One wrong word will fail validation.

**Issue**: Can't decrypt Base58  
**Solution**: Verify passphrase is exactly the same (case-sensitive). Check for extra spaces in Base58 string.

## License

MIT License - see LICENSE file for details

## Disclaimer

⚠️ **IMPORTANT**: This tool handles sensitive cryptographic material.

- Use at your own risk
- Always test with small amounts first
- Keep multiple backups of your mnemonics and passphrases
- The authors are not responsible for lost funds
- This tool is provided as-is without warranty of any kind

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Support

If you encounter any issues or have questions, please open an issue on GitHub.

---

**Remember**: Your mnemonic seed phrase controls access to your funds. Treat it like a password to your bank account - maybe even more carefully! The Linux License disguise is a privacy feature, but the real security comes from keeping your passphrase secret.

## Python CLI Version

For advanced users who prefer command-line tools, a Python CLI version (`bip39coder.py`) is also included in this repository.

### Installation

```bash
pip install base58
```

### Usage

**Interactive Mode** - Enter 24 words with live suggestions:
```bash
python bip39coder.py
```

**Dice Mode** - Generate from physical dice rolls (98+ rolls):
```bash
python bip39coder.py 123456123456123456123456123456123456123456123456123456123456123456123456123456123456123456123456123456
```

**Decode Mode** - Decrypt a Base58 string:
```bash
python bip39coder.py 11111AWJqK8ZcHvPmVLkVzVp3CzGH5RmPHwUvXoSSWdUQe
```

### Requirements

- Python 3.6+
- `base58` library

### Features

The Python CLI version offers:
- Terminal-based interactive word entry with live autocomplete
- Keyboard shortcuts (number keys 1-9 to select suggestions)
- Same encryption/decryption algorithms as the web version
- Cross-platform support (Windows, macOS, Linux)
- Smaller footprint for command-line workflows

**Note**: The web version (HTML) is recommended for most users as it works completely offline without any installation or dependencies.

## Acknowledgments

- BIP39 standard by Bitcoin community
- QRCode.js library for QR generation
- html2canvas library for PNG export
- Inspired by the need for secure, offline seed phrase management
