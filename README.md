# VFD Display

A Python module to interface with VFD (Vacuum Fluorescent Display) displays via serial communication.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Installation

You can install the `vfd-display` module using `pip`. Ensure you have Python 3.6 or higher installed.

```bash
pip install vfd-display
```

## Usage
Here’s a simple example of how to use the VfdDisplay class to write messages to a VFD display:

```bash
import configparser
from vfd_display import VfdDisplay

# Load configuration
config = configparser.ConfigParser()
config.read('config.ini')

# Initialize the VFD display
vfd = VfdDisplay(port=config["Settings"]["Port"], enabled=config["Settings"].getboolean("Status_VFD"))

# Clear the screen
vfd.clear_screen()

# Write messages to the display
vfd.write_line("MACHINE ARRETEE", line=1, column=1)
vfd.write_line("ESSAYEZ + TARD", line=2, column=1)

# Close the connection when done
vfd.close()

```
## Configuration
You can use a configuration file (e.g., config.ini) to specify parameters such as the serial port and status of the VFD. Here’s an example of what the configuration file could look like:
ini
```bash
[Settings]
Port = /dev/ttyUSB0
Status_VFD = True
```
## Contributing
Contributions are welcome! Please open an issue or submit a pull request for any enhancements, bug fixes, or feature requests.

## License

This project is licensed under the MIT License. See the #LICENSE file for details.

### Key Sections Explained

- **Installation**: Provides users with instructions on how to install the module using `pip`.
- **Usage**: Shows a basic example of how to use the `VfdDisplay` class and read configuration settings from a file.
- **Configuration**: Suggests how to manage settings using a configuration file, improving usability.
- **Contributing**: Encourages collaboration and provides a pathway for users to contribute to the project.
- **License**: Clarifies the licensing terms for the project.

### Next Steps

- Add any additional sections relevant to your project, such as "Features," "Limitations," or "Support."
- Update the configuration file example to reflect any specific options your module requires.
- Ensure the license section reflects your chosen license by providing a link to the actual license file in your repository.

Feel free to customize this template to better suit your project's specifics or personal preferences!


