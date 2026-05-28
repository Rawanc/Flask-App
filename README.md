# Flask Message Board

A simple and lightweight Flask web application that allows users to submit and view messages. The messages are persistently stored in a local text file (`message_log.txt`).

## Features

* Submit new messages via a web form.
* View a running list of all previously submitted messages.
* File-based storage for easy setup and logging.
* Configurable via environment variables.

## Prerequisites

* Python 3.x
* Flask

## Setup and Installation

1. Clone this repository or download the source code.
2. Navigate to the project directory:
   ```bash
   cd "Flask App"
   ```
3. (Optional) Create and activate a virtual environment:
   ```bash
   python -m venv venv
   # On Windows:
   venv\Scripts\activate
   # On macOS/Linux:
   source venv/bin/activate
   ```
4. Install the required dependencies:
   ```bash
   pip install flask
   ```

## Running the Application

Start the application by running the `app.py` script:

```bash
python app.py
```

The application will be accessible in your web browser at `http://localhost:5000`.

### Configuration Options

The application supports the following environment variables:

* `PORT`: Specifies the port to run the server on (default: `5000`).
* `DEBUG`: Set to `True` to enable Flask's debug mode for development (default: `False`).