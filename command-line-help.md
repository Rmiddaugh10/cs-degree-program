# Linux Command Line and Development Environment Guide

## Terminal Navigation and Interaction

### Text Viewers and Pagers (less, more, man)
- Press `q` to exit text viewers and manual pages
- Use `Space` to scroll down one page
- Use `b` to scroll up one page
- Use arrow keys for line-by-line navigation
- Press `/` followed by a term to search forward
- Press `n` to find the next occurrence of your search term
- Press `N` to find the previous occurrence

### Bash Shell Shortcuts
- `Ctrl+A`: Move cursor to beginning of line
- `Ctrl+E`: Move cursor to end of line
- `Ctrl+K`: Cut text from cursor to end of line
- `Ctrl+U`: Cut text from beginning of line to cursor
- `Ctrl+Y`: Paste (yank) text that was cut
- `Ctrl+R`: Search command history (reverse search)
- `Ctrl+L`: Clear screen
- `Ctrl+C`: Terminate current process
- `Ctrl+Z`: Suspend current process
- `Ctrl+D`: Exit current shell session (similar to typing "exit")

### Command History
- `Up/Down` arrows navigate through command history
- `!!` repeats the last command
- `!$` refers to the last argument of the previous command
- `history` shows your command history
- `!123` runs command number 123 from history

## Package Management

### APT (Debian/Ubuntu)
- `sudo apt update`: Update package list
- `sudo apt upgrade`: Upgrade all packages
- `sudo apt install <package>`: Install a package
- `apt search <term>`: Search for packages
- `apt show <package>`: Show package details
- `sudo apt remove <package>`: Remove a package (keeps configuration)
- `sudo apt purge <package>`: Remove a package and its configuration
- `sudo apt autoremove`: Remove automatically installed packages no longer needed

### Pip (Python)
- `pip list`: List installed packages
- `pip install --user <package>`: Install a package for current user only
- `pip install -r requirements.txt`: Install packages from a requirements file
- `pip freeze > requirements.txt`: Create a requirements file from installed packages
- `pip show <package>`: Show information about a package
- `pip install --upgrade <package>`: Upgrade a package

### Conda (Anaconda)
- `conda create -n <env-name> python=3.10`: Create a new environment
- `conda activate <env-name>`: Activate an environment
- `conda deactivate`: Exit current environment
- `conda list`: List packages in current environment
- `conda install <package>`: Install a package
- `conda update <package>`: Update a package
- `conda remove <package>`: Remove a package
- `conda env list`: List all environments
- `conda env export > environment.yml`: Export environment to a file
- `conda env create -f environment.yml`: Create environment from a file

## File Operations

### Basic File Commands
- `ls -la`: List all files with details
- `cp -r source destination`: Copy directories recursively
- `mv source destination`: Move/rename files or directories
- `rm -rf directory`: Remove directory and contents (use with caution!)
- `find . -name "*.py"`: Find all Python files in current directory and subdirectories
- `grep -r "text" .`: Search recursively for text in files

### File Permissions
- `chmod +x file.sh`: Make a script executable
- `chmod 755 file`: Set common permissions for executables (rwx for owner, rx for others)
- `chmod 644 file`: Set common permissions for regular files (rw for owner, r for others)
- `chown user:group file`: Change file ownership

## Development Tools

### Git Commands
- `git init`: Initialize a repository
- `git clone url`: Clone a repository
- `git status`: Check status of working directory
- `git add .`: Stage all changes
- `git commit -m "message"`: Commit staged changes
- `git pull`: Fetch and merge changes from remote
- `git push`: Push changes to remote
- `git branch`: List branches
- `git checkout -b branch-name`: Create and switch to a new branch
- `git log --oneline`: View commit history in compact format
- `git diff`: Show changes between working directory and staging area
- `git stash`: Temporarily store changes to work on something else
- `git stash pop`: Apply stashed changes

### VSCode Tips
- `Ctrl+P`: Quick file navigation
- `Ctrl+Shift+P`: Command palette
- `Ctrl+\`: Split editor
- `Ctrl+``: Open/close integrated terminal
- `Ctrl+K Ctrl+O`: Open folder
- `Alt+Up/Down`: Move line up/down
- `Shift+Alt+Up/Down`: Copy line up/down
- `Ctrl+/`: Toggle line comment
- `Ctrl+Space`: Trigger suggestions

### Python Virtual Environments
- `python -m venv env`: Create a virtual environment
- `source env/bin/activate`: Activate virtual environment (Linux/Mac)
- `env\Scripts\activate`: Activate virtual environment (Windows)
- `deactivate`: Exit virtual environment

## System Information and Monitoring

### System Status
- `htop`: Interactive process viewer (may need to install)
- `top`: Display running processes
- `free -h`: Display memory usage in human-readable format
- `df -h`: Show disk space usage
- `du -sh directory`: Show directory size
- `uname -a`: Display system information
- `lsb_release -a`: Display Linux distribution information
- `ps aux | grep program`: Find specific running processes

### Network Commands
- `ifconfig` or `ip a`: Display network interfaces
- `ping hostname`: Test connectivity
- `netstat -tuln`: List open ports
- `ssh user@host`: Connect to remote server via SSH
- `scp file user@host:/path`: Copy file to remote server
- `wget url`: Download file from web
- `curl url`: Make HTTP request to URL

## Text Processing

### Text Manipulation
- `cat file`: Display file content
- `head -n 10 file`: Show first 10 lines
- `tail -n 10 file`: Show last 10 lines
- `tail -f file`: Monitor file for changes
- `wc -l file`: Count lines in file
- `sort file`: Sort lines in file
- `uniq`: Filter out repeated lines (use after sort)
- `cut -d',' -f1 file.csv`: Extract first column from a CSV file
- `sed 's/old/new/g' file`: Replace text in file
- `awk '{print $1}' file`: Print first column of each line

## Installation Troubleshooting

### Common Issues
- If a package installation fails, try `sudo apt update` first
- For "permission denied" errors, use `sudo` for system packages
- For Python package errors, consider using a virtual environment
- If you see "command not found" after installation, you may need to add the installation path to your PATH environment variable
- Check logs in `/var/log` for system-wide installations
- For space issues, use `df -h` to check available disk space
- Use `ldd /path/to/executable` to check for missing libraries

### Log Files and Debugging
- Most application logs are in `/var/log`
- Python crash logs may be in your user directory
- Use `journalctl -xe` to view system journal for recent errors
- Add verbose flags (`-v`, `--verbose`) to see more details during installation
- For Python debugging, use `import pdb; pdb.set_trace()` in your code

## Jupyter Notebooks

### Jupyter Commands
- `jupyter notebook`: Start Jupyter notebook server
- `jupyter lab`: Start JupyterLab server
- Shift+Enter: Run cell and move to next
- Ctrl+Enter: Run cell and stay
- Esc then a: Insert cell above
- Esc then b: Insert cell below
- Esc then dd: Delete cell
- Esc then m: Change cell to markdown
- Esc then y: Change cell to code

This guide covers essential commands and shortcuts that will help you throughout your computer science studies. As you gain experience, you'll develop your own workflow and discover additional tips and tricks tailored to your specific needs.
