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
7. Create a file:
nano file.txt
8. Create a file:
vim file.txt
save by clicking esc and :wq enter
9. See what is in the file.
cat file.txt
10. Don't want anyone to see what is in the file.
shred file.txt
11. Make a new directory
mkdir newdirectory
12. Copy and paste a file
cp '/path/to/sourcefile.txt' '/path/to/destinationfile.txt'
Move a file
mv '/path/to/sourcefile.txt' '/path/to/destinationfile.txt'
13. Remove a file
rm '/path/to/file.txt'
14. Remove a directory
rmdir '/path/to/directory'
Fails if the directory is not empty then
rm -r '/path/to/directory'
15. Create a soft link to a file.
ln -s 'file.txt' 'link.txt'
16. Clear the terminal
clear
17. Display the username
whoami
18. Add a new user
useradd madhav
19. Add user as a admin (low-level utility)
sudo useradd madhav
20. Add user as a admin (high-level utility)
sudo adduser madhav
21. Switch user
su austin
22. Change back to my original user
exit
23. Change password of a user
sudo passwd madhav
24. Change my password
passwd
25. Update repository
sudo apt update
26. Install finger
sudo apt install finger
27. Inspect another user
finger user
28. Manual of a particular package
man package
29. Quick info a about a package
whatis package
30. Get one location of a package
which package
31. Get all locations of a package
whereis package
32. Download from internet
wget link
33. get content to a file
curl link > file.txt
34. Compress a file
zip file.zip file.txt
35. unzip a file
unzip file.zip
36. Pager utility for viewing a file
less file.txt
37. See the beginning of a file
head file.txt
38. See the end of a file
tail file.txt
39. Compare two files
cmp file1.txt file2.txt
40. Difference in two files
diff file1.txt file2.txt
41. Sort contents of a file
cat file.txt | sort
42. Find files
sudo find / -name "file*"
sudo find . -type f -name ".*"
sudo find . -type f -empty
sudo find . perm /a=x
43. Make a file executable
chmod +x file.sh
44. Change ownership of a file
chown username file.txt
45. Get ip address
ifconfig
46. Get ip address
ip address
47. Search for a string pattern
ip address | grep "eth0"
48. Print using regular expressions
ip address | grep "eth0" | awk "{print $2}"
49. DNS server
resolvectl status
50. Check if internet is up
ping networkchunks.com
ping -c 5 networkchunks.com
ping -c 5 -s 500 networkchunks.com
Path to a website
traceroute networkchunk.com
51. Check the open ports
netstat
netstat -tulpn
52. Check the ports
ss -tulpn
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