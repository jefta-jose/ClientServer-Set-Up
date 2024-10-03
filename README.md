# ClientServer-Set-Up

# Client
--- pnpm create vite

--- pnpm install

--- pnpm add -D vite

--- pnpm run dev

# Server

--- pnpm init

--- pnpm add express

--- pnpm add dotenv cors

--- pnpm add -D nodemon

=======================================================================

Create the server.js File

const express = require('express');
const cors = require('cors');
const dotenv = require('dotenv');

// Initialize environment variables
dotenv.config();

const app = express();
const PORT = process.env.PORT || 5000;

// Middleware
app.use(cors());
app.use(express.json());

// Basic route
app.get('/', (req, res) => {
  res.send('Hello from the backend!');
});

// Start the server
app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});


Update your package.json scripts to include the start and dev commands:

"scripts": {
  "start": "node server.js",
  "dev": "nodemon server.js"
}

=======================================================================

--- pnpm run dev