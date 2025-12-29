# AssetFavorite

A Python tool for favoriting Roblox assets using authentication cookies with multi-threading support and proxy rotation.

## Features

-  Secure authentication token generation
-  Multi-threaded processing for faster execution
-  Proxy support with automatic rotation
-  Real-time performance tracking
-  Automatic retry mechanism with exponential backoff
-  Colored console output for better visibility

## Requirements

- Python 3.7+
- Valid Roblox authentication cookies
- (Optional) Proxy list for better performance

## Installation

1. Clone the repository:
```bash
git clone https://github.com/spokeoner/AssetFavorite.git
cd AssetFavorite
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Setup

1. Create `cookies.txt` and add your Roblox authentication cookies (one per line):
```
your_roblox_cookie_here_1
your_roblox_cookie_here_2
```

2. (Optional) Create `proxies.txt` and add your proxies (one per line):
```
http://proxy1:port
http://proxy2:port
socks5://proxy3:port
```

## Usage

Run the script:
```bash
python favoriteasset.py
```

You will be prompted to enter:
- **Thread count**: Number of concurrent threads to use
- **Asset ID**: The Roblox asset ID you want to favorite


## How It Works

1. Loads cookies and proxies from text files
2. Distributes cookies across multiple threads
3. For each cookie:
   - Generates authentication tokens using ECDSA signatures
   - Obtains CSRF tokens from Roblox API
   - Sends favorite request to Roblox API
   - Retries on failure (up to 3 attempts)
4. Tracks and displays real-time statistics

## Security Notice

⚠️ **Important**: Never commit `cookies.txt` or `proxies.txt` to version control. These files contain sensitive information and are already included in `.gitignore`.

## License

MIT License - see [LICENSE](LICENSE) file for details

## Author

[SpokeOner](https://github.com/spokeoner)

## Disclaimer

This tool is for educational purposes only. Use responsibly and in accordance with Roblox's Terms of Service.

