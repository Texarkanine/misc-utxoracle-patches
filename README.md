# UTXOracle Patches

This repository contains patches for the UTXOracle Bitcoin price oracle script.

## Patch Features

### Version 9 Patches

- **Command-line Options:**
  - Added short flags for better command-line usability:
    - `-c` - Custom Bitcoin configuration file location
    - `-o` - Custom output HTML file name (use `-o false` to skip HTML output)
    - `-n` - Non-interactive mode (no browser, no prompts)
    - `-t` - Custom HTML template file
    - `-s` - Silent mode (output only final price)

- **Authentication:**
  - Added support for rpcauth authentication:
    - username extracted from rpcauth entry in bitcoin.conf
    - Password supplied via BITCOIN_RPC_PASSWORD environment variable

- **Custom Template Support:**
  - Added ability to use custom HTML template files
  - Fallback to default template on errors

- **Silent Mode:**
  - Implemented `-s` flag for outputting only the final price
  - Added conditional_print() function to suppress regular output in silent mode
  - Added error_print() function to ensure error messages still show on stderr

- **Output Control:**
  - Added ability to skip HTML generation entirely with `-o false`
  - Improved error handling to use proper exit codes

All patches maintain backward compatibility with the original UTXOracle functionality.
