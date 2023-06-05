# Chatbot Application (LangChain)

This is a Python Flask application that implements a chatbot using OpenAI's GPT-3.5 turbo model and LangChain. The chatbot application is designed to process user inputs, generate responses using the GPT-3.5 model, and manage user data and conversation history with LangChain. Notably, user conversation history and other relevant data are persisted in a MongoDB database, ensuring that interactions are not lost between sessions.

## License

This project is licensed under the terms of the MIT license.

## Installation

To install the application, you need to have Python installed on your machine. You also need to install the required Python packages. 

First, you may want to create a virtual environment to isolate the dependencies for this project. You can do this using `virtualenv`:

```bash
# Install virtualenv
pip install virtualenv

# Create a virtual environment
virtualenv --python=python3 venv

# Activate the virtual environment
source venv/bin/activate
```

Then, you can install the required packages using the `requirements.txt` file:

```bash
pip install -r requirements.txt
```

Next, you need to set up your environment variables. Copy the `.env.sample` file to a new file named `.env` and replace the placeholders with your actual values:

```bash
cp .env.sample .env
# Open .env and replace the placeholders with your actual values
```

## Structure

The application is structured into five main Python files:

1. `app.py`: This is the main Flask application file. It sets up the Flask application and defines the routes for the application.

2. `Chatbot.py`: This file defines the Chatbot class. The Chatbot class connects to a MongoDB database and provides methods for managing users and persisting conversation history.

3. `User.py`: This file defines the User class. The User class represents a user of the chatbot and provides methods for generating responses to user's questions.

4. `memory.py`: This file provides functions for managing a user's conversation history in MongoDB, ensuring that past interactions are not lost.

5. `config.py`: This file provides functions for setting up logging and retrieving environment variables.

## Usage

To run the application, execute the `app.py` file:

```bash
python app.py
```

The application runs a web server that listens for HTTP POST requests on the `/process` endpoint. The POST request should contain a JSON object with the following properties:

- `username`: The username of the user.
- `message_input`: The message input from the user.
- `input_type`: The type of the input. Currently, only 'text' input type is supported.

The application responds with a JSON object that contains the chatbot's response to the user's input.

## Contributing

Contributions are welcome. Please submit a pull request if you want to propose changes.

## Support

If you encounter any issues or have any questions, please open an issue on GitHub.

## Authors and Acknowledgement

This project was created by Marcus Adebayo.

## License

This project is licensed under the terms of the MIT license.