# GistChat – Encrypted Messaging Using GitHub Gists

GistChat is a lightweight, open-source terminal messenger that uses GitHub Gists to exchange encrypted messages. It uses the NaCl (libsodium) cryptography library to provide strong end-to-end encryption with Ed25519 and X25519 keys. No central server is involved, giving you full control over your messages and encryption keys.

---

## Features

- End-to-end encryption using Ed25519 and X25519
- Uses GitHub Gists instead of a central server
- Private keys are never shared or stored online
- Minimal dependencies and runs in the terminal
- Works on Windows, Linux, macOS, and Android (via Termux)
- Fully open-source and auditable

---

## Why Use GistChat?

GistChat is designed for users who value privacy and self-hosting. There are no phone numbers, no third-party servers, and no metadata tracking. It may not be as beginner-friendly as modern messengers and does not support group chats, but it prioritizes full control and minimalism.

---

## Installation

1. Clone the repository and install dependencies:

```
git clone https://github.com/roseler/GistChat.git
cd GistChat
pip install -r requirements.txt
```

2. If you don't already have a GitHub account, create one at [https://github.com](https://github.com)

---

## Set Up

### Step 1: Create a GitHub Token

1. Go to [https://github.com/settings/tokens](https://github.com/settings/tokens)
2. Click "Generate new token (classic)"
3. Enable the "Gist" permission (read, write, delete)
4. Copy and save the token somewhere secure

### Step 2: Create a Gist

1. Visit [https://gist.github.com/](https://gist.github.com/)
2. Click "New Gist"
3. Name the file `chat.txt` (public or secret is fine)
4. Click "Create Gist"
5. Copy the Gist ID (the last part of the URL)

---

## Running the Program

Run the main script:

```
python GistChat.py
```

The first time you run it, you'll be asked to enter:

- Your GitHub token
- The Gist ID

These will be saved to `config.txt` for future use.

---

## Sharing `config.txt` With a Friend

Both users must have the same `config.txt` to communicate.

### Option 1: Send the file manually

You can share the `config.txt` file using any secure method.

### Option 2: Use the built-in encrypted sharing

To send the config:

```
python send.py
```

To receive the config:

```
python receiver.py
```

This will download and decrypt the file, then automatically delete the temporary Gist.

---

## How to Use

Run:

```
python GistChat.py
```

To send a message:
- Type your message and press Enter.
- The message will be encrypted and posted to the Gist.

To receive messages:
- The script checks the Gist every 3 seconds.
- New messages are automatically decrypted and displayed.

---

## Security Overview

- Uses NaCl cryptography (Ed25519 and X25519)
- No passwords or secrets stored remotely
- Messages are encrypted before being uploaded
- GitHub cannot read your messages
- Only encrypted data is shared
- Fully self-hosted and auditable

