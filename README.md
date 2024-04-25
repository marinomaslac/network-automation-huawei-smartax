# Network Automation - Huawei MAC Filter Configuration Tool

## Description
This tool is designed to automate the process of managing MAC address filtering on Huawei SmartAX Multi-Service Access Nodes (MSANs). It allows users to easily update MAC filter entries by reading data from an Excel file and applying changes to the device via SSH.

## Features
- Read MAC address data from an Excel file.
- Connect to Huawei SmartAX MSAN devices via SSH.
- Update MAC filter entries on multiple devices simultaneously.

## Requirements
- Python 3.x
- scrapli library
- openpyxl library

## Installation
1. Clone this repository to your local machine.
2. Navigate to the project directory.

## Usage
1. Ensure that Python 3.x is installed on your system.
2. Install the required Python libraries using pip:
    ```python
    pip install -r requirements.txt
    ```
3. Update the configuration file `config.json` with the appropriate credentials and device information.
4. Prepare your MAC filter data in an Excel file named `macfilter_py.xlsx`. The most important aspect is that the Excel file should contain the management IP   address of the MSAN device and the corresponding MAC addresses that should be in its MAC filter, all in the same row. The columns are not important because the script will automatically recognize whether it's dealing with MAC addresses, IP addresses, or other non-essential data such as the MSAN alias.
5. Run the script `huawei_macfilter_from_table.py` to execute the MAC filter update process:
    ```python
    python huawei_macfilter_from_table.py
    ```
This script performs the following actions:
    - Reads and deletes all MAC addresses from the MAC filter table on the Huawei SmartAX device.
    - Reads MAC addresses from the macfilter_py.xlsx Excel file and adds them to the MAC filter table on the device. 

## Important Note
Please note that due to limitations in the scrapli library, this script is not officially supported on Windows platforms. It has been tested on Linux, specifically on an Ubuntu virtual machine.

## Configuration

1. Create a new file named `config.json` in the root directory of the project.
2. Copy the following template into `config.json`:
```json
{
"username": "your_username",
"password": "your_password"
}
```
Replace `"your_username"` and `"your_password"` with your actual credentials for accessing the Huawei SmartAX device.
3. Save the `config.json` file.
4. Ensure that `config.json` is added to the `.gitignore` file to prevent it from being tracked by Git and uploaded to the repository.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License
MIT



