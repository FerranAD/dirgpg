<h1 align="center">dirgpg 🔐 - simple directory encription with GPG</h1>

**dirgpg** is a simple script for encrypting and decrypting a directory using GPG. It secures your data by encrypting the directory when not in use and decrypting it for temporary access.

> [!WARNING]  
> This project was developed for personal use and is not intended for high-security applications. Use at your own risk.

## Features
- 🔓 Temporarily decrypts the chosen directory.
- ♻️ Automatically re-encrypts on termination.
- 🗂️ Maintains a backup of the previous encryption.
- 🖥️ User-friendly terminal output.

## Requirements
- **GPG** installed and configured.
- A valid GPG key or email ID for encryption.

## Installation
1. Clone or download this repository.
2. Place the `dirgpg` script in your `PATH` or execute it directly.
3. Make the script executable:

   ```bash
   chmod +x dirgpg
   ```

## Configuration
1. Open the script:

   ```bash
   nano dirgpg
   ```

2. Set your GPG key ID or email:

   ```bash
   GPG_RECIPIENT="your-email-or-key-id"
   ```

3. Optionally, update the `DATA_DIR` variable (default: `$HOME/data`).

## Usage
Run the script and the following scenarios will occur:

### First run:
   1. `DATA_DIR` is created if it does not exist.
   2. Add or modify files as needed.
   3. Press any key or `Ctrl+C` to encrypt and exit.

### Regular use:
   1. Decrypts and restores the directory.
   2. Add or modify files as needed.
   3. Press any key or `Ctrl+C` to encrypt and exit.

### Script was finished incorrectly (e.g., due to sudden computer shutdown or terminal window closed):
   1. Detects the `DATA_DIR` not being encrypted, so decryption is skipped and user is warned.
   2. Add or modify files as needed.
   3. Press any key or `Ctrl+C` to encrypt and exit.


## Error Handling
- 🛑 Exits if the GPG recipient is not configured.
- 🚨 Handles decryption errors by cleaning up partial files and exiting.

## Example
```bash
$ ./dirgpg


     ##     ##
     ##
  #####    ###     #####     #####   #####     #####
 ##  ##     ##     ##  ##   ##  ##   ##  ##   ##  ##
 ##  ##     ##     ##        #####   #####     #####
  #####   ######   ##           ##   ##           ##
                            #####    ##       #####

dirgpg - Simple directory encryption with GPG
=================================================================

[INFO] Created directory: /home/your-username/data.

-------------------------------------------------------------------
[INFO] /home/ferran/data is ready.
[INFO] Modify its contents as needed.
[INFO] Press any key or Ctrl-C to finish.
-------------------------------------------------------------------
^C

# Modify contents of `data` directory...

[INFO] Terminating script...
[INFO] Encrypted /home/your-username/data to /home/your-username/.data-encrypted.
[INFO] Cleanup complete. Exiting.
```

## Contributing
Contributions are welcome! Submit issues or pull requests to improve the project. 🙌
