# Starvision WebGL Deployment

## Capstone Project at Holberton School

### Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Team](#team)
- [Technologies](#technologies)
- [Setup](#setup)
- [Usage](#usage)


### Overview
Starvision is an immersive simulation of the solar system developed using the Unity Game Engine. This project serves as a capstone for our Software Engineer program at Holberton School. The simulation provides detailed information about the planets and the sun, including rotation, speed, and distance, sourced from NASA databases.

### Features
- Realistic simulation of the solar system
- Detailed information about each planet and the sun
- Interactive user interface
- JSON file integration for dynamic data updates
- Educational content based on NASA data
- WebGL deployment for browser access

### Team
- **Raphael Santos**: Backend, Database Manager https://github.com/GoldenHatchet15
- **Abdiel**: Dev Lead https://github.com/Abdiel-88
- **Ladie**: Frontend, Backend https://github.com/Eidal559

### Technologies
- Unity Game Engine
- C#
- HTML
- CSS
- JavaScript
- JSON
- Bootstrap

### Setup
To get a local copy of the WebGL deployment up and running, follow these simple steps:

#### Prerequisites
- Unity Game Engine installed
- Visual Studio or another C# IDE
- Git
- Python 3
- Flask
- Flask-CORS

#### Installation
1. Clone the repository:
    ```sh
    git clone git@github.com:GoldenHatchet15/StarVision-full_-project.git
    ```
2. Set up the data:
    - Ensure your JSON data file is in place.
    - Place the JSON file in the `WebGL/StreamingAssets` folder of the Unity project.
3. Configure data loading(if necessary):
    - Update the data loading scripts in the Unity project to read from the JSON file.


### Running the WebGL Build Locally
1. Ensure you have Python 3, Flask, and Flask-CORS installed. You can install Flask and Flask-CORS using pip:
    ```sh
    pip install Flask Flask-CORS
    ```
2. Create a Python script (`server.py`) with the following content:
    ```python
    #!/usr/bin/env python3
    from flask import Flask, send_from_directory
    from flask_cors import CORS

    app = Flask(__name__, static_folder='StarVision-full_-project')
    CORS(app)

    @app.route('/')
    def serve_index():
        return send_from_directory(app.static_folder, 'index.html')

    @app.route('/<path:path>')
    def serve_file(path):
        return send_from_directory(app.static_folder, path)

    if __name__ == '__main__':
        app.run(port=8000)
    ```
3. Ensure your WebGL build is located in the `StarVision-full_-project` directory.
4. Run the Flask server:
    ```sh
    python server.py
    ```
5. Open a browser and navigate to `http://localhost:8000` to see the simulation.

### Usage
Interact with the planets through the browser to view detailed information and explore the solar system.

