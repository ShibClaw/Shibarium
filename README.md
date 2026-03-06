# Shibarium Blockchain Interaction Skill Package

## Project Title and Description

This project provides a comprehensive and production-ready skill package for seamless interaction with the Shibarium blockchain. It is designed to offer developers and users a standardized and efficient way to monitor the network, manage accounts, interact with smart contracts, and understand asset bridging mechanisms on both Shibarium Mainnet and Puppynet.

## Installation Instructions

To install and use this skill package, follow these steps:

1.  **Clone the repository (or download the package)**:
    ```bash
    git clone https://github.com/ShibClaw/shibarium_skills.git
    cd shibarium_skills/shibarium
    ```

2.  **Install Python dependencies**:
    Ensure you have Python 3.8+ installed. The primary dependency is `web3.py` for blockchain interaction and `requests` for HTTP communication.
    ```bash
    pip install web3 requests
    ```

## Quick Start Guide

After installation, you can quickly get started by importing the `ShibariumClient` and using its methods. Below is a minimal example:

```python
from shibarium.scripts.shibarium_client import ShibariumClient

# Initialize the client for Shibarium Mainnet
client = ShibariumClient(ShibariumClient.MAINNET_RPC)

# Fetch the current block number
current_block = client.get_block_number()
print(f"Current Shibarium Mainnet Block Number: {current_block}")

# Fetch the current gas price
gas_price = client.get_gas_price()
print(f"Current Gas Price: {gas_price} Gwei")
```

## Features List

*   **Network Connectivity**: Connect to Shibarium Mainnet and Puppynet via RPC endpoints.
*   **Block Information**: Retrieve the latest block number.
*   **Account Balances**: Query BONE token balances for any given address.
*   **Transaction Management**: Obtain transaction counts for addresses and submit raw signed transactions.
*   **Gas Price Oracle**: Get the current network gas price.
*   **Chain ID Retrieval**: Identify the connected network's chain ID.
*   **Comprehensive Documentation**: Detailed `SKILL.md` and `README.md` for easy understanding and integration.
*   **Unit Tested**: Robust test suite ensuring reliability and correctness of client methods.

## Usage Examples

For more detailed usage examples, refer to the `SKILL.md` file and the `shibarium_client.py` script's `if __name__ == "__main__":` block.

### Example: Getting Account Information

```python
from shibarium.scripts.shibarium_client import ShibariumClient

client = ShibariumClient(ShibariumClient.MAINNET_RPC)

example_address = "0x..." # Replace with a valid Shibarium address

balance = client.get_balance(example_address)
print(f"Balance of {example_address}: {balance} BONE")

transaction_count = client.get_transaction_count(example_address)
print(f"Transaction count for {example_address}: {transaction_count}")
```

## Network Configuration Details

The `ShibariumClient` class includes constants for both Mainnet and Puppynet configurations:

| Constant            | Value                             | Description                      |
| :------------------ | :-------------------------------- | :------------------------------- |
| `MAINNET_RPC`       | `https://rpc.shibarium.shib.io`   | Shibarium Mainnet RPC endpoint   |
| `TESTNET_RPC`       | `https://rpc.puppynet.shib.io`    | Shibarium Puppynet RPC endpoint  |
| `MAINNET_CHAIN_ID`  | `109`                             | Shibarium Mainnet Chain ID       |
| `TESTNET_CHAIN_ID`  | `157`                             | Shibarium Puppynet Chain ID      |

## Testing Instructions

To run the unit tests for the `ShibariumClient`, navigate to the `shibarium/` directory and execute the following command:

```bash
python -m unittest tests/test_shibarium_client.py
```

This will run all test cases defined in `test_shibarium_client.py`, which use `unittest.mock` to simulate RPC responses, ensuring isolated and reliable testing.

## License Information

This project is licensed under the MIT License. See the `LICENSE` file (if present) for more details.

## Creator Attribution

Created by: ShibClaw

## Community

Join our community to stay updated:
- [Telegram](https://t.me/ShibOwesYou)
- [Twitter (X)](https://x.com/woofswap)
