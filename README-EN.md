
# Discord Rich Presence Script

This Python script enables the integration of Discord Rich Presence.
It uses the `pypresence` library to display user details on Discord,
including status, description, timestamp, and icons. Additionally, it
is equipped with a tray icon to facilitate control.

## Functions

- **Discord Rich Presence**: Displays a custom status and additional information on Discord.
- **Configurable Setup**: Customization of display options such as status, details, large and small icons, and their labels.
- **Tray Icon**: Integration of a tray icon for easy control (e.g., start/stop).
- **Timestamp**: Optional display of the start time in the status.

## Features

- Configurable `config.ini` file for easy customization.
- Support for custom icons and links in the Discord status.
- Autonomous operation in the background using `threading`.

## Requirements

Install the following modules before running the script:

```bash
pip install pypresence pillow pystray
```

## Setup
1. **Configuration File**: When the script is first run, a `config.ini` file will be created in the directory.
	Edit this file to adjust your preferred settings, set the `client_id`, and customize details.

	Example for `config.ini`:
	
	```ini
	[RichPresence]
	# Create a client ID for your application: https://discord.com/developers/applications
	client_id = YOUR_CLIENT_ID
	state = Your Status
	details = Additional Details
	# Set to 1 to show the start time
	start = 1
	large_image = your_large_image
	large_text = Text for large image
	small_image = your_small_image
	small_text = Text for small image
	button1_label = Button 1
	button1_url = https://example.com
	button2_label = Button 2
	button2_url = https://example.com
	# Base64 code for the tray icon
	tray_icon_base64 = ICON_BASE64_CODE
	```
	
2. **Discord Developer Portal**: Create an application in the 
	[Discord Developer Portal](https://discord.com/developers/applications) and get a `client_id`,
	which you will enter in the `config.ini` file.

## Running the Script

Start the script with:

```bash
python py-presence.py
```

The tray icon will appear in the taskbar, allowing easy control of the Rich Presence status.

## Customizing the Tray Icon

The tray icon uses a Base64-encoded image, which is inserted directly in the `config.ini` file.
Any icon image can be converted to Base64 and stored in the `tray_icon_base64` value.

## Note

This script runs in the background and updates the Discord status based on the settings in the `config.ini`.
The script must be restarted for reconfiguration.

## License

This project is licensed under the MIT License.

## Libraries Used

This project uses the following open-source libraries:

- [pypresence](https://github.com/qwertyquerty/pypresence - for interacting with Discord Rich Presence.
- [Pillow](https://python-pillow.org/) - for image processing and creating the tray icon.
- [pystray](https://github.com/moses-palmer/pystray) - for displaying and controlling a tray icon.
