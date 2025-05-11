# UTXOracle Patches

This repository contains patches for the UTXOracle Bitcoin price oracle script.

## User Guide

### Getting Started

1. **Find your UTXOracle version:**
   - Open your UTXOracle.py file and look near the top for version information
   - The version will be in the format `UTXOracle.X.py` where X is the version number

2. **Download the appropriate patch:**
   - Find the latest release on the [Releases page](https://github.com/username/misc-utxoracle-patches/releases)
   - Download the `.patch` file for your version (e.g., `9.patch` for version 9)

3. **Apply the patch:**
   ```bash
   # Navigate to your UTXOracle directory
   cd /path/to/utxoracle/

   # Create a backup of your original file
   cp UTXOracle.py UTXOracle.py.backup

   # Apply the patch
   patch UTXOracle.py /path/to/downloaded/X.patch
   ```

4. **Verify the patch:**
   - Check that the patch applied successfully without errors
   - Try running the patched script with your normal parameters
   - Test any new features you intend to use

If you encounter any issues applying the patch, you can restore your backup:
```bash
cp UTXOracle.py.backup UTXOracle.py
```

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
