# Sound Alarm

## Overview

Sound Alarm is a Python project that provides functionality for creating and customizing sound alarms. It allows users to define a series of beeps with specific frequencies and durations, as well as pauses (sleeps) between the beeps. It also includes an option to make alarms cancelable by handling keyboard interrupts gracefully.

## Features

- **Customizable Beeps**: Define beeps with varying frequencies and durations.
- **Sleep Between Beeps**: Add pauses or sleeps between the beeps.
- **Cancelable Alarms**: Alarms can be gracefully canceled using keyboard interrupts.

## Installation Instructions

To install and set up the Sound Alarm project, follow these steps:

1. **Clone the Repository**: Clone the GitHub repository to your local machine.
    ```bash
    git clone https://github.com/Yuriy/sound_alarm.git
    ```

2. **Navigate to the Project Directory**:
    ```bash
    cd sound_alarm
    ```

3. **Ensure Python is Installed**: Make sure Python is installed on your system. This project is developed using Python 3.

4. **Install Dependencies**: There are no external dependencies for running the base functionality provided in `sound_alarm.py`. Just ensure you have the standard Python library available.

## Usage Examples

You can use the provided classes and functions to create and run custom alarms. Below is an example of how to use the `BaseBeeper` class:

```python
from sound_alarm import BaseBeeper

class CustomBeeper(BaseBeeper):
    def add_beep(self, frequency, duration):
        self._beeps.append((frequency, duration))

    def add_sleep(self, duration):
        self._beeps.append(('sleep', duration))

    def beep(self):
        for action in self._beeps:
            if action[0] == 'sleep':
                print(f"Sleeping for {action[1]} seconds")
                # time.sleep(action[1])
            else:
                print(f"Beeping at {action[0]} Hz for {action[1]} seconds")
                # Code to play beep sound

# Usage
beeper = CustomBeeper()
beeper.add_beep(1000, 1)  # Beep at 1000 Hz for 1 second
beeper.add_sleep(0.5)     # Sleep for 0.5 seconds
beeper.add_beep(1500, 1)  # Beep at 1500 Hz for 1 second
beeper.beep()             # Run the beep sequence
```

## Code Summary

The code structure is simple and revolves around the `BaseBeeper` class, which provides a base implementation for creating custom alarms. Key functionalities include:

- **BaseBeeper Class**: The core class where beeps and sleeps are defined.
  - `__init__`: Initializes an empty list to store beeps.
  - `add_beep`: Adds a beep with a specific frequency and duration (to be implemented in subclasses).
  - `add_sleep`: Adds a sleep interval (to be implemented in subclasses).
  - `beep`: Executes the beep sequence (to be implemented in subclasses).
- **Cancelable Decorator**: A decorator function to make alarm functions cancelable using a keyboard interrupt.

## Contributing Guidelines

Contributions to the Sound Alarm project are welcome! If you would like to contribute, please follow these guidelines:

1. **Fork the Repository**: Fork the project repository on GitHub.
2. **Clone Your Fork**: Clone your forked repository to your local machine.
   ```bash
   git clone https://github.com/YourUsername/sound_alarm.git
   ```
3. **Create a New Branch**: Create a new branch for your feature or bugfix.
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. **Make Changes**: Implement your changes and commit them with descriptive messages.
5. **Push Your Changes**: Push your changes to your forked repository.
   ```bash
   git push origin feature/your-feature-name
   ```
6. **Create a Pull Request**: Open a pull request on the original repository, describing your changes.

## License

This project is licensed under the MIT License. For more details, refer to the `LICENSE` file.

---

Feel free to explore, use, and contribute to the project. If you encounter any issues or have questions, please open an issue on GitHub. Happy coding!