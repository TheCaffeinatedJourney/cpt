# cpt (copy file text)

This script copies the contents of a specified file to the clipboard, with options to exclude commented lines (`-c`) and/or blank lines (`-b`).

## Description

The script reads and copies the content of a file to the clipboard using `xclip`. It provides optional flags to exclude commented lines (lines starting with `#`) and blank lines from the copied output. The first line of the file (shebang line if present) will always be included.

## Installation

 1. **Clone the Repository**:
```bash
git clone --depth=1 https://github.com/TheCaffeinatedJourney/cpt.git
cd cpt
```

 2. **Make the Script Executable**:
```bash
chmod +x cpt
```

### Additional Optional Installation Steps
 3. **Add the file to your $PATH**:
Move the file to your $PATH to run the script from anywhere by simply typing `cpt`.
- Create `$HOME/bin` if it does not exist (or use another directory in your path)
```bash
mkdir -p "$HOME/bin"
```
- Add `$HOME/bin` to your path if it is not already by adding the following line to your shell's configuration file (`~/.bashrc`):
```bash
export PATH="$HOME/bin:$PATH"
```
- Then source the configuration file:
```bash
source ~/.bashrc
```

- Copy or symlink the script to $HOME/bin
```bash
# soft link
ln -s /path/to/repo/cpt "$HOME/bin/cpt"
# copy file
cp /path/to/repo/cpt "$HOME/bin/cpt"
```

4. **Bash Completion**
To enable parameter and file tab completions
- Copy the `cpt_completion` file to the your bash completion directory (usually `~/.bash_completion.d/`, create the directory if it doesn’t exist):
```bash
mkdir -p ~/.bash_completion.d
cp cpt_completion ~/.bash_completion.d/
```
- Then add this line to the your ~/.bashrc file to source the completions:
```bash
source ~/.bash_completion.d/cpt_completion
```
- Then source the configuration file
```bash
source ~/.bashrc
```

## Usage

```bash
cpt [options] <file>
```

### Options

- `-c` : Exclude comment lines (lines starting with `#`).
- `-b` : Exclude blank lines.
- `-h` : Show the help message.

### Example

To copy the contents of a file, excluding comments and blank lines:

```bash
./copy_file.sh -cb example.txt
```

## Dependencies
- `xclip`: Required for copying content to the clipboard. 

## Error Handling
- The script will display an error if no file is specified or if the specified file is not found.
- An invalid option will result in an error message and display the help message.

## Contributions
Feel free to submit issues or pull requests to enhance the script.  Contributions are welcome!

## License
This script is released under the MIT License.



