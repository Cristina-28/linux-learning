
# Linux Learning Notes

---

## Module 1 — Navigation & Filesystem Basics

### Commands
- pwd         → print current location
- ls          → list files in directory
- ls -l       → list with details (permissions, size, date)
- cd path     → navigate to folder
- cd ..       → go up one level
- cd ~        → go home from anywhere
- mkdir name  → create a folder
- touch file  → create an empty file
- cp a b      → copy file a to b
- mv a b      → move or rename file a to b
- rm file     → delete a file (files only)
- rm -r dir   → delete a folder and its contents
- echo "x" > file   → write to file (overwrites)
- echo "x" >> file  → append to file
- cat file    → print entire file
- head -n N file    → print first N lines
- tail -n N file    → print last N lines
- nano file   → open file in text editor

### Key concepts
- Ctrl+O saves in nano, Ctrl+X exits
- > overwrites, >> appends — don't mix them up
- rm has no undo — be careful

---

## Module 2 — The Linux Mental Model & FHS

### Key concepts
- Kernel = core OS, talks directly to hardware
- Shell = interface between you and the kernel (bash is a shell)
- Desktop Environment = the GUI layer (optional, servers often have none)
- "Everything is a file" — hardware, processes, config all appear as files

### Filesystem Hierarchy Standard (FHS)
- /          → root, top of everything
- /home      → user folders (/home/cristina)
- /etc       → system configuration files
- /var       → logs, cache, variable data
- /bin       → essential commands (ls, cp, mv live here)
- /tmp       → temporary files, wiped on reboot
- /dev       → devices (hard drives, keyboard, etc.)
- /proc      → virtual files for running processes
- /root      → home folder of the root (admin) user

### Paths
- Absolute path → starts with /, works from anywhere (e.g. /home/cristina)
- Relative path → depends on where you are (e.g. cd linux-learning)
- ~ = shortcut for /home/cristina
- .. = one level up


## Module 3 — File viewing, searching & editing

### Commands
- less file          → scroll through a file (q to quit, /word to search)
- tail -f file       → watch a file update live (Ctrl+C to stop)
- grep "word" file   → search for text inside a file
- grep -i            → case-insensitive
- grep -n            → show line numbers
- grep -r "word" .   → search recursively in all files
- find . -name "x"   → find a file by name
- find . -name "*.md"→ find all files with extension
- find . -type d     → find directories only
- find . -type f     → find files only

### Vim basics
- vim file     → open file
- i            → enter Insert mode (now you can type)
- Esc          → back to Normal mode
- :w           → save
- :q           → quit
- :wq          → save and quit
- :q!          → quit without saving

### Key concepts
- grep searches INSIDE files, find searches FOR files
- find searches subfolders by default, grep needs -r
- Vim has modes — always press Esc before issuing commands
