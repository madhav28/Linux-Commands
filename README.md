# Linux-Commands
## 1. Connect to the server
```bash
ssh username@servername
```
## 2. List all the files
```bash
ls

ls -l         # Long format listing with permissions, owner, size, etc.

ls -a         # Show all files including hidden ones (starting with .)

ls -la        # Long format including hidden files

ls -lt        # Sort by modification time (newest first)

ls -ltr       # Sort by modification time (newest LAST)

ls -latr      # Include hidden files, long format, newest last  

ls -lS        # Sort by file size (largest first)

ls -lSr       # Sort by file size (smallest FIRST)

ls -lh        # Human-readable file sizes (KB, MB, GB)
```
## 3. Print working directory
```bash
pwd
```
## 4. Change directory
```bash
cd                       # Change to home directory

cd /path/to/directory    # Change to a specific directory

cd ..                    # Change to parent directory

cd -                     # Change to previous directory

cd ~                     # Change to home directory (same as just 'cd')

cd ../..                 # Move up two directory levels
```
## 5. Create a file using touch
```bash
touch afile.txt                 # Create a single file  

touch file1.txt file2.txt       # Create multiple files  

touch file{1..10}.txt           # Create files with numbered names (file1.txt to file10.txt)  

touch file{a..d}.txt            # Create files with letter ranges (filea.txt to filed.txt)  

touch "file with space.txt"     # Create a file with spaces in the name  

touch .hiddenfile               # Create a hidden file (starts with a dot)  

touch -c non_existent.txt       # Avoid creating file if it doesn't exist (-c flag)  

touch -t 202501011200 file.txt  # Create file with specific timestamp (YYYYMMDDhhmm)  

touch -r reference.txt new.txt  # Use timestamp from reference.txt for new file  
```
## 6. Add content to a file
```bash 
echo "Hello World!" > newfile.txt                     # Overwrite file (or create new) with content 
  
echo "New line" >> newfile.txt                        # Append content to file (preserves existing content)
 
echo -e "Line 1\nLine 2\nLine 3" > multiline.txt      # Multi-line echo (using quotes) 

printf "Name: %s\nAge: %d\n" "Alice" 25 > user.txt    # Using printf (better for formatting)  

ls -l >> log.txt                                      # Append command output to a file  

date > current_time.txt                               # Overwrite file with command output  

# Add multi-line content with a heredoc
cat << EOF > config.txt                                 
Host: example.com  
Port: 8080  
Timeout: 30  
EOF  

# Append multi-line content  
cat << EOF >> config.txt                              
Debug: true  
EOF
```
## 7. Create or edit a file with nano
```bash
nano file.txt            # Create/edit file.txt (opens interactive editor)
nano ~/Documents/note.md # Edit a file in a specific directory
nano /etc/config.conf    # Edit system files (requires sudo)

# Common Nano Shortcuts (interactive mode):
^O (Ctrl+O)             # Save ("Write Out")
^X (Ctrl+X)             # Exit (prompts to save if unsaved)
^K (Ctrl+K)             # Cut current line
^U (Ctrl+U)             # Paste
^W (Ctrl+W)             # Search
^\ (Ctrl+\)             # Search and replace
^G (Ctrl+G)             # Open help menu
^_ (Ctrl+_)             # Go to specific line number
```
8. Create or edit a file with vim
```bash
vim file.txt                    # Open file.txt (create if it doesn't exist)
vim +300 config.conf            # Open file and jump to line 300
vim -O file1.txt file2.txt      # Open files in vertical split view
sudo vim /etc/nginx/nginx.conf  # Edit system files (requires sudo)

# Essential Vim Commands:
i          # Enter Insert mode (start typing)
Esc        # Return to Normal mode (stop typing)
:w         # Save file ("write")
:q         # Quit (fails if unsaved changes)
:q!        # Quit WITHOUT saving (force)
:wq        # Save and quit
:x         # Save only if changes were made, then quit
:help      # Open Vim's built-in help
```
## 9. View file contents
### Basic Viewing
```bash
cat file.txt             # Display entire file contents
cat -n file.txt          # Show with line numbers
cat file1.txt file2.txt  # Concatenate multiple files
```
### Partial Viewing
```bash
head file.txt           # Show first 10 lines
head -n 5 file.txt      # Show first 5 lines
tail file.txt           # Show last 10 lines
tail -n 5 file.txt      # Show last 5 lines
tail -f logfile.log     # Follow (live tail) a growing file
```
### Advanced Viewing
```bash
less file.txt           # Interactive viewer (scroll/search with /pattern)
more file.txt           # Basic pager (spacebar to advance)
nl file.txt             # Show with line numbers (alternative to cat -n)
tac file.txt            # Display in reverse order (cat backwards)
```
### Filtered Viewing
```bash
grep "pattern" file.txt      # Show only lines containing pattern
grep -v "exclude" file.txt   # Exclude lines with pattern
grep -i "hello" file.txt     # Case-insensitive search
grep -A 3 "match" file.txt   # Show 3 lines after match
grep -B 2 "match" file.txt   # Show 2 lines before match
```
## 10. Securely delete files
```bash
shred file.txt          # Overwrite file to hide contents (default 3 passes)
shred -u file.txt       # Overwrite AND delete file after shredding
shred -v file.txt       # Verbose mode (show progress)
```
## 11. Make a new directory
```bash
mkdir newdirectory
```
## 12. Copy and paste a file
```bash
cp /path/to/sourcefile /path/to/destination
```
## 13. Move a file
```bash
mv '/path/to/sourcefile.txt /path/to/destinationfile.txt
```
## 14. Remove a file
```bash
rm '/path/to/file'
```
## 15. Remove a directory
```bash
rm -r directory/            # Delete directory and ALL contents inside
rm -rf directory/           # Delete WITHOUT confirmation prompts
```
## 16. Create a soft link to a file
```bash
ln -s file.txt link.txt     # Create link to file in current directory
```
## 17. Clear the terminal
```bash
clear
```
## 17. Display username
```bash
whoami
```
## 18. Add a new user
```bash
useradd madhav

sudo useradd madhav   # Add user as a admin (low-level utility)

sudo adduser madhav   # Add user as a admin (high-level utility) 
```
## 19. Switch user
```bash
su madhav
```
## 20. Change back to my original user
```bash
exit
```
## 21. Change password of a user
```bash
sudo passwd madhav     # Different user

passwd                 # Change my password
```
## 22. Update packages repository
```bash
sudo apt update
```
## 23. Inspect another user
```bash
# Install finger
sudo apt update
sudo apt install finger

# Inspect user
finger username
```
## 24. Help/Manual for a package
```bash
man package
```
## 25. Short help/Manual for a package
```bash
whatis package
```
## 26. Get location of a executable
```bash
which package       # Get one location

whereis package     # Get all location
```
## 27. Download from internet
```bash
wget https://example.com/file.zip

curl -o myfile.zip https://example.com/file.zip
```
## 28. Compress a file
```bash
zip archive_name.zip file1 file2 file3
```
## 29. Unzip a file
```bash
unzip archive_name.zip
```
## 30. Compare two files
```bash
cmp file1.txt file2.txt
```
## 31. Difference in two files
```bash
diff file1.txt file2.txt
```
## 32. Sort contents of a file
```bash
cat file.txt | sort     # sorts the lines in ascending order
```
## 33. Find files
```bash
sudo find / -name "file*"         # Find files named "file*" system-wide

sudo find . -type f -name ".*"    # Find hidden files in current dir

sudo find . -type f -empty        # Find empty files in current dir

sudo find . -perm /a=x            # Find executable files in current dir
```
## 34. Make a file executable
```bash
chmod +x file.sh
```
## 35. Change ownership of a file
```bash
chown username file.txt
```
## 36. Get ip address
```bash
ifconfig

ip address
```
## 37. Search for a string pattern
```bash
ip address | grep "eth0"

ip address | grep "eth0" | awk "{print $2}"
```
## 38. DNS server
```bash
resolvectl status
```
## 39. Check if internet is up
```bash
ping google.com                 # Ping Google continuously

ping -c 5 google.com            # Ping Google 5 times

ping -c 5 -s 500 google.com     # Ping Google 5 times with 500-byte packets

traceroute google.com           # Trace route to Google
```
## 40. Check the open ports
```bash
netstat          # Show all active network connections and listening ports  

netstat -tulpn   # Show listening TCP/UDP ports with process info (numeric)  

ss -tulpn        # Show listening TCP/UDP ports with process info (modern netstat alternative)
```
53. Allow incoming TCP connections on port 80 (HTTP)
sudo iptables -I INPUT -p tcp -m tcp --dport 80 -j ACCEPT
54. Allow incoming traffic on port 80
sudo ufw allow 80
55. Status of ufw
sudo ufw enable
sudo ufw status
56. Info about the system
uname
uname -a
57. neofetch
sudo apt install neofetch
neofetch
58. View Calendar
cal
calculate math
echo "4+5+6+7" | bc
59. Check memory in the system
free
60. Disk Space
df
df -H
61. Size of a directory
du -sh path/to/directory
61. Check running processes
ps
ps -aux
62. check top process
top
htop
63. Kill a specific process
ps -aus | grep thisisbash.sh
kill -9 process_id
64. Kill a process using name
pkill -f thisisbash
65. systemctl
sudo systemctl start apache2
sudo systemctl stop apache2
sudo systemctl restart apache2
sudo systemctl status apache2
66. Get history of all the commands
history
67. Reboot the system
sudo reboot
68. shutdown the system
sudo shutdown
sudo shutdown -h now