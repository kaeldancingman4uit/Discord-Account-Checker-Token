#  Discord Account Checker (Python)

A simple and efficient **Python** tool for checking the validity of Discord account tokens.

>  **Disclaimer:** This tool is intended for educational purposes and for checking **your own accounts only**. Misuse may violate the Terms of Service of Discord and can result in account suspension or termination.

---

##  Features

* Validate Discord tokens
* Bulk token checking (from file)
* Displays basic account information:

  * Username
  * User ID
  * Email (if available)
  * Phone (if available)
  * Nitro status
  * 2FA status
* Colored console output
* Optional proxy support

---

##  Requirements

* Python **3.8+**
* pip

###  Dependencies

Install via:

```bash
pip install -r requirements.txt
```

Or manually:

```bash
pip install requests colorama
```

---

##  Project Structure

```
discord-account-checker/
│
├── main.py
├── requirements.txt
├── tokens.txt
└── README.md
```

---

##  Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/discord-account-checker.git
cd discord-account-checker
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Add your tokens to `tokens.txt` (one token per line)

---

##  Usage

Run the script:

```bash
python main.py
```

The program will:

* Load tokens from `tokens.txt`
* Send requests to the Discord API
* Validate each token
* Display results in the console

---

##  Example Output

```
[VALID] user#1234 | ID: 123456789012345678 | Nitro: Yes | 2FA: Enabled
[INVALID] Token is invalid or expired
```

---

##  Proxy Support (Optional)

If proxy support is implemented:

Add proxies in the following format:

```
http://username:password@ip:port
```

Store them in `proxies.txt` (if supported by your implementation).

---

##  How It Works

The script sends a GET request to:

```
https://discord.com/api/v9/users/@me
```

With the header:

```
Authorization: <TOKEN>
```

* `200 OK` → Token is valid
* `401 Unauthorized` → Token is invalid

---

##  Possible Statuses

| Status       | Description                   |
| ------------ | ----------------------------- |
| VALID        | Token is valid                |
| INVALID      | Token is invalid              |
| LOCKED       | Account requires verification |
| RATE LIMITED | Too many requests             |

---

##  Important Notes

* Do not abuse the API.
* Use delays between requests to avoid rate limits.
* Do not check accounts you do not own.
* The author is not responsible for misuse.

---

##  License

MIT License

---

##  Contributing

Pull requests are welcome.
For major changes, please open an issue first.

---

If needed, I can also provide:

* CLI argument version
* Async version (aiohttp)
* GUI version
* Logging to file
* A more professional README with badges

Just let me know your project structure and I’ll tailor it.
