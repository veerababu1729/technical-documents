# Linux Commands Cheat Sheet

## Working with Text Files using Pipes

### Download Harry Potter book from the internet
```bash
curl -s -L "https://raw.githubusercontent.com/bobdeng/owlreader/master/ERead/assets/books/Harry%20Potter%20and%20the%20Goblet%20of%20Fire.txt" -o book.txt
```

- `curl` downloads stuff from the web
- `-s` keeps it quiet (no loading bars)
- `-L` follows redirects
- `-o book.txt` saves it as book.txt

### Show first 3 lines
```bash
head -n 3 book.txt
```

- `head` shows the top of a file
- `-n 3` means show only 3 lines

### Show last 10 lines
```bash
tail -n 10 book.txt
```

- `tail` shows the end of a file
- `-n 10` means show last 10 lines

### Count how many times characters appear in the book
```bash
grep -o "Harry" book.txt | wc -l
grep -o "Ron" book.txt | wc -l
grep -o "Hermione" book.txt | wc -l
grep -o "Dumbledore" book.txt | wc -l
```

- `grep` finds text
- `-o` puts each match on new line
- `wc -l` counts the lines

### Show lines 100 to 200
```bash
sed -n "100,200p" book.txt
```

- `sed` can grab specific lines from a file

### Count unique words in the book
```bash
cat book.txt | tr 'A-Z' 'a-z' | tr -c 'a-z' '\n' | sort | uniq | wc -l
```

- `cat` reads the file
- `tr 'A-Z' 'a-z'` makes everything lowercase
- `tr -c 'a-z' '\n'` puts each word on new line
- `sort` arranges alphabetically
- `uniq` removes duplicates
- `wc -l` counts them

## Working with Processes

### Find Chrome's process IDs
```bash
ps -o pid,ppid -C chrome
```

- `ps` shows running processes
- `pid` = process ID, `ppid` = parent process ID
- `-C chrome` filters only Chrome processes

### Close Chrome from terminal
```bash
pkill chrome
```

- `pkill` kills a process by its name

### Show top 3 CPU-hungry processes
```bash
ps -eo %cpu,cmd --sort=-%cpu | head -n 4
```

- `-eo` shows all processes
- `%cpu` shows CPU usage
- `--sort=-%cpu` sorts by CPU (highest first)
- `head -n 4` shows top 3 (plus header)

### Show top 3 memory-hungry processes
```bash
ps -eo %mem,cmd --sort=-%mem | head -n 4
```

- Same as above but for memory usage

## Working with Ports

### Start a simple web server on port 8000
```bash
python3 -m http.server 8000
```

- Starts Python's built-in web server
- Access it at `localhost:8000`

### Stop that server (in another terminal)
```bash
lsof -i :8000
```

- Shows what's running on port 8000
- Note the PID, then:
```bash
kill <PID>
```

Or just kill all Python processes:
```bash
pkill python3
```

### Try starting server on port 90 (will probably fail - needs sudo)
```bash
python3 -m http.server 90
```

- Ports below 1024 need admin rights

### Show all network connections
```bash
netstat -a
```

- Lists all active network connections (TCP/UDP)

### Find what's using port 5432
```bash
lsof -i :5432
```

- Shows process using that specific port

## Installing Software

### Install some useful programs
```bash
sudo apt update
```

- Updates the list of available software
```bash
sudo apt install htop vim nginx
```

- `htop` - better task manager
- `vim` - text editor
- `nginx` - web server

### Remove nginx
```bash
sudo apt remove nginx
```

- Uninstalls nginx but keeps config files

## Network Stuff

### What's my computer's IP address?
```bash
ip -4 addr
```

- Shows your IPv4 address

### What's Google's IP address?
```bash
nslookup google.com
```

- Looks up the IP for a website

### Check if internet is working
```bash
ping google.com
```

Or use:
```bash
nslookup google.com
```

- If you get an IP back, internet works!

### Find where programs are installed
```bash
which node
which code
```

- Shows the full path to these programs
- Usually something like `/usr/bin/node`
