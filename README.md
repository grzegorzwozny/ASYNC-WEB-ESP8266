# Micropython Async Non-blocking WebServer for ESP8266

This project is a non-blocking web server written in MicroPython for the ESP8266. Using the `select()` module for non-blocking I/O and an asynchronous task scheduler, it enables efficient, multitasking server operation. The project includes additional features such as:

- Real-Time Clock (DS1307)
- External I/O Port Expander (MCP23017)
- JSON-based pseudo-database
- Custom command parser
- Independent tasks

## Architecture
The application consists of three main threads:
1. **Server Thread**: Manages the web server in non-blocking mode.
2. **I/O Management Thread**: Handles input/output port operations.
3. **Monitoring Thread**: Supervises application state and performance.

The application is designed to manage a hardware controller with six output channels (for relay control), and an input for monitoring a limit switch (e.g., for door status). A real-time clock (RTC) provides date and time, enabling two distinct operating modes.

## Operating Modes
1. **Continuous Mode**: Activates a timer for a defined period (e.g., 60 seconds) to control relay outputs. When the timer starts, the relay is set to "on," and after the period ends, it automatically turns "off."
   
2. **Scheduler Mode**: Allows configuration to activate specific channels based on day and time (e.g., from hour to hour on specific days). Up to seven schedules can be programmed, one for each day of the week.

## Demo
Check out the demo here: [Demo Video](https://youtu.be/OatHs5Z4SgE)

## Note
The hardware layer for this device is proprietary and cannot be shared.
