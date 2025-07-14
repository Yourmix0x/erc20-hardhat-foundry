# ERC20 Token Implementation with Hardhat & Foundry

A comprehensive ERC20 token implementation using both Hardhat and Foundry frameworks. This project demonstrates a custom ERC20 token contract with modern development practices, extensive testing, and deployment capabilities.

## 🚀 Features

- ✅ **Custom ERC20 Implementation**: Built from scratch following ERC20 standard
- ✅ **Dual Framework Support**: Hardhat for deployment, Foundry for advanced testing
- ✅ **Standard ERC20 Functions**: `transfer`, `approve`, `transferFrom`, `balanceOf`, `allowance`
- ✅ **Minting & Burning**: Internal functions for token supply management
- ✅ **Comprehensive Test Suite**: Tests in both TypeScript (Hardhat) and Solidity (Foundry)
- ✅ **Mock Contracts**: Testing utilities with public mint function
- ✅ **TypeChain Integration**: Type-safe contract interactions
- ✅ **Gas Reporting**: Built-in gas consumption analysis
- ✅ **Multi-Network Support**: Local, Sepolia testnet configurations

## 📁 Project Structure

```
├── contracts/
│   ├── ERC20.sol               # Main ERC20 token contract
│   └── mocks/
│       └── ERC20Mock.sol       # Mock contract for testing
├── test/
│   ├── ERC20.ts               # Hardhat/TypeScript tests
│   └── ERC20.t.sol            # Foundry/Solidity tests
├── scripts/
│   └── deploy.ts              # Deployment script
├── ignition/
│   └── modules/               # Hardhat Ignition modules
├── typechain-types/           # Generated TypeScript types
├── hardhat.config.ts          # Hardhat configuration
├── foundry.toml              # Foundry configuration
└── package.json              # Node.js dependencies
```

## 🔧 Smart Contracts

### ERC20.sol

The main ERC20 token contract implementing:

- `transfer(address to, uint256 value)` - Transfer tokens to another address
- `approve(address spender, uint256 value)` - Approve spender allowance
- `transferFrom(address from, address to, uint256 value)` - Transfer tokens on behalf of another address
- `_mint(address to, uint256 value)` - Internal function to mint new tokens
- `_burn(address from, uint256 value)` - Internal function to burn tokens
- Standard ERC20 events: `Transfer` and `Approval`

**Key Features:**

- Solidity version: `^0.8.19`
- Gas-optimized implementation
- Proper event emission
- Comprehensive error handling

### ERC20Mock.sol

A mock contract extending the main ERC20 contract with:

- Public `mint(address to, uint256 value)` function for testing
- Same base functionality as ERC20.sol

## 🛠️ Getting Started

### Prerequisites

- Node.js (v16 or later)
- npm or yarn
- Foundry (for Solidity testing)

### Installation

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd erc20-hardhat-foundry
   ```

2. **Install Node.js dependencies**

   ```bash
   npm install
   ```

3. **Install Foundry** (if not already installed)

   ```bash
   curl -L https://foundry.paradigm.xyz | bash
   foundryup
   ```

4. **Set up environment variables**
   ```bash
   cp .env.exmaple .env
   ```
   Edit `.env` with your configuration:
   ```bash
   SEPOLIA_RPC_URL=https://rpc.sepolia.org
   PRIVATE_KEY=your_private_key_here
   ETHERSCAN_API_KEY=your_etherscan_api_key_here
   ```

## 🔨 Usage

### Compile Contracts

**Using Hardhat:**

```bash
npx hardhat compile
```

**Using Foundry:**

```bash
forge build
```

### Run Tests

**Hardhat Tests (TypeScript):**

```bash
npx hardhat test
```

**Foundry Tests (Solidity):**

```bash
forge test
```

**Run tests with verbosity:**

```bash
forge test -vvv
```

**Run specific test:**

```bash
forge test --match-test testTranferTokenCorrectly
```

### Deploy Contracts

**Deploy to Local Hardhat Network:**

```bash
npx hardhat node
npx hardhat run scripts/deploy.ts --network localhost
```

**Deploy to Sepolia Testnet:**

```bash
npx hardhat run scripts/deploy.ts --network sepolia
```

### Additional Commands

**Generate TypeChain types:**

```bash
npx hardhat typechain
```

**Run tests with gas reporting:**

```bash
REPORT_GAS=true npx hardhat test
```

**Run coverage analysis:**

```bash
npx hardhat coverage
```

**Check code formatting:**

```bash
forge fmt --check
```

## 📊 Contract Details

The ERC20 token is deployed with the following default parameters:

- **Name**: YOU
- **Symbol**: Yourmix0x
- **Decimals**: 18
- **Initial Supply**: 0 (tokens must be minted)

## 🧪 Testing

The project includes comprehensive tests in both frameworks:

### Hardhat Tests (`test/ERC20.ts`)

- ✅ Token transfers between accounts
- ✅ Balance updates verification
- ✅ Insufficient balance error handling
- ✅ Transfer event emissions
- ✅ Change token balance assertions

### Foundry Tests (`test/ERC20.t.sol`)

- ✅ Token transfer functionality
- ✅ Balance assertions with decimal precision
- ✅ Error handling for insufficient balance
- ✅ Event emission verification
- ✅ Advanced testing with console logging

**Run all tests:**

```bash
# Hardhat tests
npx hardhat test

# Foundry tests
forge test

# Run both test suites
npm run test:all
```

## 🌐 Networks

This project supports multiple networks:

| Network | RPC URL                   | Chain ID | Purpose           |
| ------- | ------------------------- | -------- | ----------------- |
| Hardhat | `http://localhost:8545`   | 31337    | Local development |
| Sepolia | `https://rpc.sepolia.org` | 11155111 | Ethereum testnet  |

## 📁 Key Files

- `contracts/ERC20.sol` - Main ERC20 implementation
- `contracts/mocks/ERC20Mock.sol` - Mock contract for testing
- `test/ERC20.ts` - Hardhat/TypeScript tests
- `test/ERC20.t.sol` - Foundry/Solidity tests
- `scripts/deploy.ts` - Deployment script
- `hardhat.config.ts` - Hardhat configuration
- `foundry.toml` - Foundry configuration

## 🔒 Security Considerations

⚠️ **Important**: This is a demonstration/learning project. For production use, consider:

- **Access Controls**: Implement role-based permissions
- **Pausable Functionality**: Add emergency stop mechanisms
- **Reentrancy Guards**: Protect against reentrancy attacks
- **Input Validation**: Add comprehensive parameter validation
- **Overflow Protection**: Use SafeMath or Solidity ^0.8.0 built-in checks
- **Security Audits**: Conduct thorough security reviews
- **Standard Libraries**: Consider using OpenZeppelin contracts

## 🛠️ Development Tools

This project uses several development tools:

- **Hardhat**: Development framework and testing
- **Foundry**: Advanced testing and gas optimization
- **TypeChain**: Type-safe contract interactions
- **Ethers.js**: Ethereum library for JavaScript
- **Chai**: Assertion library for testing
- **Solhint**: Solidity linter
- **Prettier**: Code formatting

## 📖 Learning Resources

- [ERC20 Standard](https://eips.ethereum.org/EIPS/eip-20)
- [Hardhat Documentation](https://hardhat.org/docs)
- [Foundry Book](https://book.getfoundry.sh/)
- [Solidity Documentation](https://docs.soliditylang.org/)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines

- Write comprehensive tests for new features
- Follow Solidity style guidelines
- Update documentation for any changes
- Ensure all tests pass before submitting

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Yourmix0x** - [GitHub Profile](https://github.com/Yourmix0x)

---

_This project is for educational purposes and demonstrates modern Solidity development practices with both Hardhat and Foundry frameworks._
