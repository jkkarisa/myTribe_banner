
# CloudmyTribe Terminal Banner

This guide provides step-by-step instructions to set up a CloudmyTribe banner that displays every time you open your terminal in Gitpod and ensures the banner remains visible even after clearing the screen.

## Prerequisites

- Python 3
- `pip` (Python package installer)

## Step 1: Install `colorama` Library

Open your terminal and run the following command to install the `colorama` library:

```sh
pip install colorama
```

## Step 2: Create the Python Script

Create a directory for the script (optional):

```sh
mkdir ~/scripts
```

Open the `vim` editor to create the Python script:

```sh
vim ~/scripts/cloudmytribe_banner.py
```

Press `i` to enter insert mode and paste the following code:

```python
from colorama import init, Fore, Style

def display_banner():
    init(autoreset=True)
    banner = r"""
     ____ _                 _                _____     _ _          
    / ___| | ___  _   _  __| |_ __ ___  _   |_   _| __(_) |__   ___ 
   | |   | |/ _ \| | | |/ _` | '_ ` _ \| | | || || '__| | '_ \ / _ \
   | |___| | (_) | |_| | (_| | | | | | | |_| || || |  | | |_) |  __/
    \____|_|\___/ \__,_|\__,_|\__,_|_| |_| |_|\__, ||_||_|  |_|_.__/ \___|
                                      |___/                        
    Welcome to CloudmyTribe!
    """
    print(Fore.MAGENTA + banner)

if __name__ == "__main__":
    display_banner()
```

Press `Esc`, type `:wq`, and press `Enter` to save and exit `vim`.

## Step 3: Make the Script Executable

Run the following command to make the script executable:

```sh
chmod +x ~/scripts/cloudmytribe_banner.py
```

## Step 4: Add the Script to Your Shell Configuration File

### For Bash Shell

Open your `.bashrc` file:

```sh
vim ~/.bashrc
```

Press `i` to enter insert mode, scroll to the bottom using the arrow keys, and add the following lines:

```sh
# Display CloudmyTribe banner on terminal start and clear screen
python3 ~/scripts/cloudmytribe_banner.py

# Alias clear command to keep the banner visible
alias clear='clear && python3 ~/scripts/cloudmytribe_banner.py'
```

Press `Esc`, type `:wq`, and press `Enter` to save and exit `vim`.

### For Zsh Shell

Open your `.zshrc` file:

```sh
vim ~/.zshrc
```

Press `i` to enter insert mode, scroll to the bottom using the arrow keys, and add the following lines:

```sh
# Display CloudmyTribe banner on terminal start and clear screen
python3 ~/scripts/cloudmytribe_banner.py

# Alias clear command to keep the banner visible
alias clear='clear && python3 ~/scripts/cloudmytribe_banner.py'
```

Press `Esc`, type `:wq`, and press `Enter` to save and exit `vim`.

## Step 5: Reload the Shell Configuration

After updating your shell configuration file, reload it to apply the changes.

For Bash, run:

```sh
source ~/.bashrc
```

For Zsh, run:

```sh
source ~/.zshrc
```

## Verification

Close your terminal and open it again. You should see the CloudmyTribe banner displayed. When you clear the screen using the `clear` command, the banner should reappear.

## Troubleshooting

If you encounter any issues or need further assistance, feel free to ask the dev team or any member of your unit!

## License

This project is licensed under the MIT License.
```

This file provides clear, step-by-step instructions for setting up the CloudmyTribe banner in the terminal using Gitpod, including installing dependencies, creating and editing the script, and configuring the terminal to run the script on startup and after clearing the screen.
