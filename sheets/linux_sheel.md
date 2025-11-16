# Linux Terminal Cheat Sheet — Ready to copy/paste

Commands shown one per block for easy copy/paste. A one-line description follows each command.

## Navigation & listing
```sh
pwd
```
Print the current working directory.

```sh
ls -la
```
List all files (including hidden) with details.

```sh
cd /path/to/dir
```
Change current directory to /path/to/dir.

```sh
cd -
```
Switch to the previous directory.

## File & directory operations
```sh
mkdir -p path/to/newdir
```
Create a directory and parent directories if needed.

```sh
touch file.txt
```
Create an empty file or update file timestamps.

```sh
cp src dest
```
Copy a file or directory (use -r for directories).

```sh
mv oldname newname
```
Move or rename a file or directory.

```sh
rm file.txt
```
Remove a file (use rm -r for directories; be careful).

```sh
rm -rf dir/
```
Force-remove a directory and its contents (dangerous — use carefully).

## Viewing & editing files
```sh
cat file.txt
```
Print the file to stdout.

```sh
less file.txt
```
Paginate through a file (q to quit).

```sh
head -n 50 file.log
```
Show the first 50 lines of a file.

```sh
tail -n 100 -f file.log
```
Show last 100 lines and follow file as it grows.

```sh
nano file.txt
```
Edit a file with nano (simple terminal editor).

```sh
vim file.txt
```
Edit a file with vim (powerful terminal editor).

## Searching & finding
```sh
grep -n "pattern" file.txt
```
Search for "pattern" in file and show line numbers.

```sh
grep -R "pattern" .
```
Recursively search current directory for "pattern".

```sh
find . -name "*.py"
```
Find files matching pattern starting from current directory.

```sh
locate filename
```
Quickly find files by name (update db with sudo updatedb).

## Permissions & ownership
```sh
chmod +x script.sh
```
Make a script executable.

```sh
chmod -R 755 dir/
```
Recursively set directory and file permissions.

```sh
chown user:group file
```
Change file owner and group.

## Processes & system info
```sh
ps aux | grep process_name
```
List processes and filter by name.

```sh
top
```
Interactive process viewer (press q to quit).

```sh
htop
```
Improved interactive process viewer (if installed).

```sh
kill <pid>
```
Send SIGTERM to process with pid.

```sh
pkill -f process_name
```
Kill processes matching a pattern.

## Networking & transfer
```sh
ssh user@host
```
Connect to a remote host via SSH.

```sh
scp file user@host:/remote/path
```
Copy a file to a remote host over SSH.

```sh
curl -O https://example.com/file.tar.gz
```
Download a file with curl and save with remote name.

```sh
wget https://example.com/file.tar.gz
```
Download a file with wget.

## Compression & archives
```sh
tar -czvf archive.tar.gz dir/
```
Create a gzipped tarball of dir/.

```sh
tar -xzvf archive.tar.gz
```
Extract a gzipped tarball.

```sh
zip -r archive.zip dir/
```
Create a zip archive of dir/.

## Disk & usage
```sh
df -h
```
Show filesystem disk usage in human-readable form.

```sh
du -sh .
```
Show total size of current directory.

```sh
du -h --max-depth=1
```
Show sizes of subdirectories one level deep.

## Package management (Debian/Ubuntu examples)
```sh
sudo apt update && sudo apt upgrade -y
```
Update package lists and upgrade installed packages.

```sh
sudo apt install package-name -y
```
Install a package via apt.

## Shell helpers
```sh
history | grep git
```
Search your shell history for git commands.

```sh
alias gs="git status"
```
Create a temporary alias in the current shell session.

```sh
export PATH="$HOME/.local/bin:$PATH"
```
Prepend a directory to PATH for the current session.

```sh
chmod +x ./script.sh && ./script.sh
```
Make a script executable and run it.

## Quick tips
- Use tab completion to speed navigation and reduce typos.
- Pipe commands to combine tools (e.g., ps aux | grep name | awk ...).
- Always dry-run destructive commands when possible (e.g., inspect with ls/find before rm).
- Use sudo only when necessary and understand the command being run.
- Keep a small set of trusted dotfiles (aliases, functions) for common workflows.