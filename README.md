# Kaspa Web Wallet - tickak

The `tickak` Web Wallet is a browser-based cryptocurrency wallet for the Kaspa blockchain, adapted from [kaspa-ng v1.0.1](https://github.com/aspectron/kaspa-ng) by [tickak.com](https://tickak.com). It provides a user-friendly interface to manage Kaspa addresses, view balances, and send transactions, built with Rust, WebAssembly (WASM), and EGUI.

This document explains how to deploy the `tickak` Web Wallet locally using Node.js.

## Prerequisites

- **Rust**: Version 1.80.0 or higher. Install via [rustup](https://rustup.rs/).
- **Node.js**: Version 18.x or higher. Download from [nodejs.org](https://nodejs.org/).
- **Git**: For cloning the repository.
- **Windows, Linux, or macOS**: Tested on Windows 10/11.

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/tickak/tickak-wallet.git
cd tickak-wallet
git checkout v1.0.1
```


### 2. Install Node.js and http-server

```bash
npm install -g http-server
```

Verify installations:

```bash
node --version   # Should show 18.x or higher
http-server --version
```

## Build

```bash
cd tickak-wallet
Extract kaspa-ng-2196f1d3ba817c7f_bg.rar:

```

- `--no-wasm-opt`: Skips WASM optimization to avoid potential errors.
- Output: Static files are generated in the `dist/` directory.

## Run Locally

Host the project directory using `http-server`:

```bash
cd dist
http-server -p 8080
```

- `-p 8080`: Runs the server on port 8080 (customizable, e.g., 80 requires admin privileges).
- The server binds to `0.0.0.0`, allowing access from other devices on the network.

### Access the Wallet

- **Local**: Open `http://localhost:8080` in a modern browser (Chrome 120+, Edge 120+, Firefox 120+).
- **Network**: Access via `http://<your-ip>:8080` (e.g., `http://192.168.1.90:8080`).
  - Ensure port 8080 is open in your firewall:
    ```bash
    netsh advfirewall firewall add rule name="tickak" dir=in action=allow protocol=TCP localport=8080
    ```

Verify:
- The browser tab title should display "tickak Wallet".
- The interface should show the wallet UI (address, balance, transaction form), not just the logo.


### 3. Network Access Issues
- **Cause**: Firewall or port blocking.
- **Fix**:
  - Open port 8080:
    ```bash
    netsh advfirewall firewall add rule name="tick naive dir=in action=allow protocol=TCP localport=8080
    ```
  - Verify server is running: `http://localhost:8080`.

## License

This project is adapted from `kaspa-ng` under a proprietary MIT-style license, restricted to use with the Kaspa network. See [LICENSE](LICENSE) for details.

## Support

- **Issues**: Report bugs or request features at [GitHub Issues](https://github.com/tickak/tickak-wallet/issues).
- **Community**: Join the Kaspa Discord at [discord.gg/kaspa](https://discord.gg/kaspa).
- **Contact**: Visit [tickak.com](https://tickak.com) for more information.