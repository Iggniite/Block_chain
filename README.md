# E-Voting: A Decentralized Voting System

This project is a full-stack decentralized application (dApp) that provides a secure, transparent, and modern platform for conducting elections using blockchain technology. It features a traditional backend for user management and a smart contract on the blockchain to handle the core voting logic, ensuring the integrity of the election process.

---
## Features

- User Authentication: Secure registration and login for voters and admins.
- Role-Based Access Control (RBAC): Distinct capabilities and UI for different user roles (Admin vs. Voter).
- Admin Dashboard: Admins can create new elections and add candidates with details and images.
- Dynamic Voting Portal: Users can view upcoming, live, and ended elections in a tabbed interface.
- Secure Voting: Users can cast their vote for candidates in live elections, with rules enforced by the smart contract.
- Real-Time Results: A results page that shows a live tally for ongoing elections and declares a winner for ended elections.
- Transparency Log: A public history of all voting transactions (with masked voter addresses) to ensure auditability.
- Virtual ID Card: A personalized digital ID for each registered user, which can be downloaded as an image.
- Automated Startup: A single command to launch the entire local development environment.

---
## Tech Stack

### Blockchain
- Solidity: For writing the smart contract.
- Hardhat: For the development environment, testing, and deployment.
- Ethers.js: For frontend-to-blockchain communication.

### Frontend
- React.js: For building the user interface.
- Vite: As the frontend build tool.
- Tailwind CSS: For styling the application.
- React Router: For handling client-side navigation.

### Backend
- Node.js: As the JavaScript runtime environment.
- Express.js: For building the backend API.
- MongoDB Atlas: As the cloud database for storing user data.
- Mongoose: For modeling the application data.
- JWT & bcrypt.js: For handling user authentication and password hashing.

---
## Project Structure

The project is organized into three main directories:

- `/blockchain`: Contains the Solidity smart contract, deployment scripts, and Hardhat configuration.
- `/backend`: Contains the Node.js/Express server for user management and API endpoints.
- `/frontend`: Contains the React application for the user interface.

---
## Prerequisites

Before you begin, ensure you have the following installed:

- Node.js (v18 or later)
- npm (usually comes with Node.js)
- MetaMask browser extension

---
## Local Development Setup

### 1. Clone the Repository
First, clone the project to your local machine.
`git clone <your-repo-url>`
`cd E-VOTING`

### 2. Install Dependencies
You need to install the dependencies for each part of the project. Open three separate terminals.

- In Terminal 1 (for the blockchain):
`cd blockchain`
`npm install`

- In Terminal 2 (for the backend):
`cd backend`
`npm install`

- In Terminal 3 (for the frontend):
`cd frontend`
`npm install`

### 3. Setup Backend Environment
- In the `/backend` directory, create a `.env` file.
- Add your MongoDB Atlas connection string to it:
`MONGO_URI="your_mongodb_connection_string"`

### 4. Running the Application

### Automated Start (Recommended)
We have created a script to run the entire development environment with a single command.

- From the root `E-VOTING` directory, run:
`npm run dev`

This command will automatically:
1. Start the local Hardhat blockchain node.
2. Start your backend server.
3. Deploy your smart contract to the local node.
4. Start your frontend React application.

### Manual Start (For Understanding)
If you want to run each service manually:
1. Terminal 1 (Blockchain Node):
   `cd blockchain`
   `npx hardhat node`
2. Terminal 2 (Backend Server):
   `cd backend`
   `node server.js`
3. Terminal 3 (Deployment):
   `cd blockchain`
   `npx hardhat run scripts/deploy.js --network localhost`
4. Terminal 4 (Frontend):
   `cd frontend`
   `npm run dev`

