# ESP32-Remote-Gate-Control-System
The Gate Control System is a simple solution for remotely controlling and monitoring a gate or entry point. It consists of an ESP32-based receiver unit that interfaces with a relay to physically open and close the gate, and a web-based control interface that allows users to trigger the gate remotely.

## Project Overview

The main components of the Gate Control System are:

1. **ESP32 Receiver Unit**: The ESP32 board is responsible for receiving wireless signals from the control interface and triggering the gate's relay. It is connected to the gate's relay and configured to listen for incoming commands over the ESP-NOW protocol.

2. **Web-based Control Interface**: The web-based control interface is built using HTML, CSS, and JavaScript. It allows users to view a live video feed from a camera monitoring the gate and trigger the gate's opening and closing with the click of a button.

3. **Server Application**: The server application, written in Python using the Flask framework, serves the web-based control interface and handles the communication between the client-side interface and the ESP32 receiver unit. It receives trigger requests from the client, forwards them to the ESP32, and provides a live video feed from the gate camera.

4. **Configuration File**: The `config.json` file stores the IP address of the ESP32 receiver unit, which is used by the server application to communicate with the ESP32.

The system works as follows:

1. The user accesses the web-based control interface, which displays a live video feed from the gate camera.
2. When the user clicks the "Trigger Gate" button, the client-side JavaScript sends a request to the server application.
3. The server application receives the request, forwards it to the ESP32 receiver unit, and the ESP32 triggers the gate's relay to open or close the gate.
4. The server application sends a response back to the client-side interface, indicating the success or failure of the gate trigger operation.

This system allows for remote control and monitoring of the gate, providing convenience and security for the user.

## Installation

To set up the Gate Control System, follow these steps:

### Dependencies

The project requires the following dependencies:

- `flask`
- `flask-cors`
- `opencv-python`
- `requests`

1. Clone the repository to your local machine.
2. Install the required dependencies for the server application.
3. Configure the `config.json` file with the IP address of the ESP32 receiver unit.
4. Upload the `receiver.cpp` code to the ESP32 board.
5. Run the server application using the command `python gate_control_server.py`.
6. Access the web-based control interface in your web browser.

## Usage

1. Open the web-based control interface in your web browser.
2. Click the "Trigger Gate" button to open or close the gate.
3. The server application will forward the request to the ESP32 receiver unit, which will trigger the gate's relay.
4. The server application will send a response back to the client-side interface, indicating the success or failure of the gate trigger operation.

## Contributing

If you would like to contribute to the Gate Control System project, please follow these guidelines:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and test them thoroughly.
4. Submit a pull request with a detailed description of your changes.

## License

This project is licensed under the [MIT License](LICENSE).
