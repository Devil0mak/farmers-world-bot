# Farmers World Bot

Farmers World Bot is a JavaScript project designed to automate interactions with the Farmers World game. This project includes a CI/CD pipeline to ensure code quality and facilitate automated testing.

## CI/CD Pipeline

The CI/CD pipeline is configured using GitHub Actions and includes the following stages:

```yaml

1. Checkout Code
This step checks out the code from the repository to the GitHub Actions runner. It uses the `actions/checkout@v2` action.

2. Set up Node.js
This step sets up the Node.js environment using version 14. It uses the `actions/setup-node@v2` action.

- name: Checkout code
  uses: actions/checkout@v2

3. Install Dependencies
This step installs the necessary dependencies for the project using npm install.

  - name: Set up Node.js
  uses: actions/setup-node@v2
  with:
    node-version: '14'


4. Lint with ESLint
This step runs ESLint to ensure the code follows the JavaScript style guide. It installs ESLint and runs it on the project files.

- name: Install dependencies
  run: |
    npm install

5. Run Tests
This step runs the tests using the npm test command to ensure the code works as expected.


- name: Run tests
  run: |
    npm test


Docker Containerization
The project is also containerized using Docker. The Dockerfile sets up a container for the Farmers World Bot application. Here is the content of the Dockerfile:

FROM node:14-slim

WORKDIR /app

COPY . /app

RUN npm install

CMD ["node", "index.js"]

This Dockerfile does the following:

This Dockerfile does the following:

1.Uses the node:14-slim image as the base image.
2.Sets the working directory to /app.
3.Copies the project files into the container.
4.Installs the project dependencies.
5.Sets the command to run the bot using node index.js.


Continuous Deployment (CD)
The CD part of the workflow is not functional and deployed to an endpoint in this example.

How to Run Locally
To run the project locally, follow these steps:

Clone the repository:

git clone https://github.com/<your-username>/farmers-world-bot.git
cd farmers-world-bot

Install dependencies:

npm install

Run the bot:

node index.js

```


## References
[farmers-world-bot](https://github.com/SmartBotBlack/farmers-world-bot)