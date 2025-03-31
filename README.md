# COS30049 Trading Platform

This project is a comprehensive trading platform integrating a MySQL database, Express.js API, React.js front-end, and Solidity smart contracts. The platform supports real-time trading operations, portfolio management, and secure on-chain transactions via MetaMask.

## Table of Contents

- [Installation](#installation)
- [Project Structure](#project-structure)
- [Dependencies](#dependencies)
- [Setup & Run](#setup--run)
- [Development](#development)
- [Contributing](#contributing)
- [Troubleshooting](#troubleshooting)
- [License](#license)

## Installation

### 1. Clone the Repository

```sh
git clone https://github.com/your-repo/trading-platform.git
cd trading-platform
```

### 2. Configure Environment Variables

Create a `.env` file in the `backend` folder (use the provided `.env.example` as a template):

```ini
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_DATABASE=trading_platform
BLOCKCHAIN_URL=http://localhost:8545
```

### 3. Install Dependencies

#### Backend

```sh
cd backend
npm install
```

#### Frontend

```sh
cd ../frontend
npm install
```

## Project Structure

```
/group-project-spr-2025-g12
│
├── /backend
│   ├── hardhat.config.js
│   ├── package.json
│   ├── importData.js
│   ├── /api
│   │   ├── index.js
│   │   ├── api-endpoints.js
│   ├── /db
│   │   ├── schema.sql
│   │   └── archive/csv files
│   ├── /contracts
│   │   ├── TradingPlatform.sol
│   ├── /script
│   │   ├── deploy.js
│   └── .env
│
└── /frontend
    ├── package.json
    └── /src
        ├── App.css
        ├── index.js
        ├── Wallet.css
        ├── WalletContext.css
        ├── /components
        │   ├── Header.js
        │   ├── Home.js
        │   ├── Login.js
        │   ├── TradingPlatform.js
        │   ├── App.js
        │   ├── WalletContext.js
        │   ├── Wallet.js
        └── ... (other components)
```

## Dependencies

### Backend (Node.js + MySQL)

- `dotenv`: Loads environment variables.
- `mysql2`: MySQL database connector (promise-based).
- `csv-parser`: Parses CSV files for data import.
- `express`: Web framework for building RESTful APIs.
- `bcrypt`: For password hashing.

#### Sample `package.json` dependencies:

```json
{
  "dependencies": {
    "express": "^4.18.2",
    "mysql2": "^3.5.2",
    "csv-parser": "^3.0.0",
    "dotenv": "^16.3.1",
    "bcrypt": "^5.1.0"
  }
}
```

### Manually added dependencies:
```sh
cd backend
npm install express@4.18.2
npm install mysql2@3.5.2
npm install csv-parser@3.0.0
npm install dotenv@16.3.1
npm install bcrypt@5.1.0
```

### Smart Contracts (Hardhat & Ethers.js)

- `hardhat`: Ethereum development framework.
- `ethers`: Library to interact with the Ethereum blockchain.
- `@nomicfoundation/hardhat-ethers`: Hardhat plugin for ethers.js.

#### Sample `package.json` dependencies:

```json
{
  "dependencies": {
    "hardhat": "^2.17.0",
    "ethers": "^5.7.2",
    "@nomicfoundation/hardhat-ethers": "^2.2.3"
  }
}
```

### Manually added dependencies:
```sh
npm install hardhat@2.17.0
npm install ethers@5.7.2
npm install @nomicfoundation/hardhat-ethers@2.2.3
```

### Frontend (React)

- `react`: UI framework.
- `react-dom`: For rendering React components.
- `react-router-dom`: Routing library for React.
- `ethers`: For blockchain integration.
- `react-chartjs-2`: React wrapper for Chart.js.
- `chart.js`: Charting library.

#### Sample `package.json` dependencies:

```json
{
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-router-dom": "^6.14.2",
    "ethers": "^5.7.2",
    "react-chartjs-2": "^5.2.0",
    "chart.js": "^4.3.0"
  }
}
```

### Manually added dependencies:
```sh
cd ../frontend
npm install react@18.2.0
npm install react-dom@18.2.0
npm install react-router-dom@6.14.2
npm install ethers@5.7.2
npm install react-chartjs-2@5.2.0
npm install chart.js@4.3.0
```

## Setup & Run

### 1. Backend

#### Set up the database:

- Ensure MySQL is running.
- Execute the `schema.sql` file in the `/backend/db` folder to create the necessary tables.
- Run `node importData.js` to seed the database with initial asset data.

#### Start the backend server:

```sh
cd backend
node index.js  # or npm start
```

### 2. Smart Contracts

#### Start a local blockchain:

```sh
npx hardhat node
```

#### Deploy the smart contracts:

```sh
npx hardhat run script/deploy.js --network localhost
```

### 3. Frontend

#### Start the React application:

```sh
cd frontend
npm start
```

Open your browser and navigate to `http://localhost:3000`.

## Development

#### Run tests for smart contracts:

```sh
npx hardhat test
```

#### For local development:

- You can run the backend server and frontend concurrently.
- Consider using tools like `concurrently` for easier management.

## Contributing

1. Fork the repository.
2. Create a feature branch:
   ```sh
   git checkout -b feature/your-feature
   ```
3. Commit your changes:
   ```sh
   git commit -m 'Add new feature'
   ```
4. Push to the branch:
   ```sh
   git push origin feature/your-feature
   ```
5. Create a Pull Request.

## Troubleshooting

### MySQL Connectivity

- Ensure the credentials in `.env` are correct and that MySQL is running.

### Blockchain Integration

- Verify that the Hardhat node is running before deploying smart contracts.
- Ensure MetaMask is connected to the correct network.

### Dependency Issues

- If you encounter `module not found` errors, try removing `node_modules` and reinstalling dependencies:
  ```sh
  rm -rf node_modules package-lock.json
  npm install
  ```
- If you still can't run the project, consider going to each folder README.md file for a more detailed dependencies installation:


## License

This project is licensed under the MIT License.

