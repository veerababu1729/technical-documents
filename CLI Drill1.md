# Linux File System Practice

## Setting up the folder structure
```bash
mkdir hello  # Create main folder
cd hello  # Go into it

# Create two folders inside hello
mkdir five
mkdir one

cd one  # Go into 'one' folder

# Create two text files
touch a.txt
touch b.txt

mkdir two  # Create 'two' folder inside 'one'
cd two  # Go into 'two'
touch d.txt  # Create d.txt file

mkdir three  # Create 'three' folder
cd three  # Go deeper
touch e.txt  # Create e.txt

mkdir four  # Another folder
cd four  # Go into it
touch access.log  # Create a log file

# Go back to the main hello folder
cd ~/hello

ls  # Check what's inside
cd five  # Go into 'five' folder

mkdir six  # Create 'six' folder
cd six  # Enter it
touch c.txt  # Create c.txt

mkdir seven  # Last folder
cd seven  # Go inside
touch error.log  # Create another log file
```

## Tasks

### Task 1: Delete all .log files
```bash
find ~/hello -type f -name "*.log" -delete
```

- `find` searches for files
- `~/hello` is where to search
- `-type f` means only files (not folders)
- `-name "*.log"` finds anything ending with .log
- `-delete` removes them

### Task 2: Add content to a.txt
```bash
filepath=$(find ~/hello -type f -name "a.txt")
nano "$filepath"
```

- First, find where a.txt is and save its location
- Then open it in nano editor to add text
- You could also use: `echo "your text" >> "$filepath"`

### Task 3: Delete the 'five' directory
```bash
filepath=$(find ~/hello -type d -name "five")
rm -r "$filepath"
```

- Find the 'five' folder (`-type d` means directory)
- `rm -r` removes folder and everything inside it
- `-r` means "recursive" (delete contents too)

### Task 4: Rename 'one' folder to 'uno'
```bash
cd hello
mv one uno
```

- `mv` (move) command also renames things
- Just do: `mv oldname newname`

### Task 5: Move a.txt into the 'two' directory
```bash
cd ~/hello
mv uno/a.txt uno/two/
```

- Move a.txt from uno folder into uno/two folder
- Format: `mv source destination`
