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
