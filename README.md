# SealSui-Auto-Bot

Automate Sui SEAL Protocol interaction for allowlist creation and service subscription management.

## Overview

SealSui-Auto-Bot is a Node.js utility that helps users interact with the Sui SEAL Protocol. This tool allows for easy creation of allowlists and service subscriptions with automated content publication to the Sui blockchain.

## Features

- ✅ Create allowlist entries and publish content
- ✅ Add multiple addresses to allowlists
- ✅ Create service subscription entries
- ✅ Upload blobs to SEAL publishers
- ✅ Support for multiple wallets
- ✅ Proxy support for requests
- ✅ Custom or random image uploads
- ✅ Support for both URL and local image files

## Requirements

- Node.js (v16 or later)
- npm or yarn
- A Sui wallet (mnemonic phrase)

## Installation

```bash
# Clone the repository
git clone https://github.com/itsmesatyavir/SealSui.git

# Navigate to project directory
cd SealSui

# Install dependencies
npm install
```

## Configuration

1. Create a file named `pk.txt` with your Sui wallet mnemonic phrase OR
2. Create `wallets.txt` with multiple wallet mnemonic phrases (one per line)
3. (Optional) Create `proxies.txt` with proxy server details (one per line)
4. (Optional) Place an image file named `image.jpg` in the root directory to use a local image

### Proxy Format

Proxies can be specified in any of these formats:

```
host:port
host:port:username:password
username:password@host:port
```

### Environment Variables

Create a `.env` file with:

```
SUI_RPC_URL=https://sui-testnet.mystenlabs.com # Optional, defaults to testnet
```

## Usage

Run the bot:

```bash
node index.js
```

Follow the interactive prompts to:
1. Choose whether to use multiple wallets (if detected)
2. Select the operation mode (allowlist or service subscription)
3. Select image source (URL or local file)
4. Specify the number of tasks per wallet
5. Add additional addresses to allowlist (for allowlist mode)

## Example Workflow

For allowlist creation:
1. Creates a new allowlist entry
2. Adds your wallet address to the allowlist
3. Adds any specified additional addresses
4. Uploads image content as a blob
5. Publishes the blob to the allowlist

For service subscription:
1. Creates a service entry with specified amount and duration
2. Uploads image content as a blob
3. Publishes the blob to the subscription service

## Advanced Settings

You can modify these constants in the code:
- `PACKAGE_ID`: The Sui package ID for SEAL protocol
- `DEFAULT_IMAGE_URL`: Default image URL if none provided
- `PUBLISHER_URLS`: URLs for SEAL publishers

## Troubleshooting

- **Proxy Issues**: Check your proxy format in proxies.txt
- **Wallet Access**: Ensure your mnemonic phrases are correctly formatted
- **Transaction Failures**: Check your wallet has sufficient SUI for gas fees
- **Blob Upload Failures**: The script will automatically retry uploads

## Disclaimer

This tool is provided for educational purposes only. Use at your own risk.

## License

MIT