---
title : "File, Directory Manager, Permissions, Networking, and SSH"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

#### Advanced File and Directory Management

1. Create a mkdr for Symblic

```
sudo mkdir -p /path/to
```

2. Symbolic and Hard Links:
- Create a symbolic link (shortcut)

```
sudo ln -s /path/to/original /path/to/symlink
```

3. Create a hard link (another name for the same file)

```
sudo ln /path/to/original /path/to/hardlink
```

4. Find Command:
- Find files by name

```
find /path/to/search -name "filename"
```

- Find files modified in the last 7 days

```
find /path/to/search -type f -mtime -7
```

- Execute a command on found files

```
find /path/to/search -name "*.log" -exec rm {} \;
```

5. rsync for Efficient File Transfer
- Synchronize directories locally or remotely

```
rsync -avz /source/directory /destination/directory
```

- Example for remote sync

```
rsync -avz /source/directory user@remote_host:/destination/directory
```



#### Permissions

6. Access Control Lists (ACLs) 
- Set an ACL on a file

```
setfacl -m u:fcj:rwx myfile.txt
```

- View ACLs

```
getfacl myfile.txt
```

7. Sticky Bit
- Set the sticky bit on a directory to restrict deletion to the owner

```
sudo mkdir /path/to/directory
sudo chmod +t /path/to/directory
```

8. Special Permissions (SUID, SGID)
- Set SUID (Set User ID)

```
chmod u+s myfile.txt
```

- Set SGID (Set Group ID)

```
chmod g+s directoryname
```

#### Advanced Networking

9. Network Configuration
- Configure network interfaces using `ip` command:

```
sudo ip addr add 192.168.1.100/24 dev eth0
sudo ip link set eth0 up
```

10. Network Troubleshooting

- Use `netstat` to view network connections and listening ports

```
netstat -tuln
```

- Use `traceroute` to trace the route packets take to a network host

```
traceroute example.com
```

11. Network Services
- Use nmap to scan for open ports on a host

```
nmap -sT -p- example.com
```

12. Firewall Configuration
- Configure firewall rules with `iptables`

```
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
sudo iptables -A INPUT -j DROP
```

#### Advanced SSH Usage

1. SSH Config File
- Configure SSH client options in `cd ~/.ssh/config`

```
Host myserver
    HostName example.com
    User myuser
    Port 2222
    IdentityFile ~/.ssh/id_rsa
```

- Connect using the configured alias

```
ssh myserver
```

2. SSH Key Management
- Generate and use different key types

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

3. Add SSH keys to the agent

```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

4. SSH Port Forwarding
- Local port forwarding

```
ssh -L local_port:remote_host:remote_port user@ssh_server
```
- Example:

```
ssh -L 8080:localhost:80 user@example.com
```

5. SSH ProxyJump

```
ssh -J user@jump_host user@target_host
```

6. Other SSH Commands
- With every one of them having its page, other than the customer ssh, there are other SSH orders.
    - sshd – OpenSSH server
    - sftp – file transfer with FTP-related command interface
    - scp – file transfer with RCP-related command interface
    - ssh-add – a tool to add a key to the agent
    - ssh –agent – agent to hold private key for single sign-on
    - ssh-copy-id – configures a public key as authorized on a server
    - ssh-keygen – creates a key pair for public-key authentication

#### Advanced Terminals

7. tmux
- Terminal multiplexer allowing multiple sessions within a single terminal window.
- Start a tmux session

```
tmux
```

- Detach from a session

```
Ctrl + b, then d
```

- Reattach to a session

```
tmux attach-session -t 0
```

8. Terminator
- Split terminal windows for multi-tasking.
- Split terminal horizontally

```
Ctrl + Shift + O
```

- Split terminal vertically

```
Ctrl + Shift + E
```

#### Advanced Text Editors and IDEs
9. GNU Emacs
- Emacs Lisp: Extend Emacs functionality with scripting.

```
(global-set-key (kbd "C-x C-b") 'ibuffer)
```

- Org Mode: Advanced project planning and note-taking.

```
emacs -nw

* TODO Write report
DEADLINE: <2024-06-15>
```

10. VIM
- Plugins: Extend VIM functionality using plugins managed by vim-plug. Install `vim-plug`

```
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

- Add plugins to `.vimrc`

```
call plug#begin('~/.vim/plugged')
Plug 'preservim/nerdtree'
Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }
call plug#end()
```

- Install plugins

```
vim +PlugInstall +qall
```

11. Advanced Editing
- Split window vertically

```
:vsplit filename
```

- Navigate between splits

```
Ctrl + w, then arrow keys
```

12. Nano
- Custom Configuration: Edit ~/.nanorc for syntax highlighting and shortcuts.
- Enable syntax highlighting for Python

```
include "/usr/share/nano/python.nanorc"
```

- Execute external commands within Nano

```
^R ^X (Read output from a command)
```

13. Kate
- Sessions: Save and load sessions to maintain your workspace.
- Save session

```
kate --start session_name
```

14. Gedit
- Plugins: Extend functionality with plugins like code snippets and embedded terminal.
- Enable plugins

```
gedit > Preferences > Plugins
```

15. Geany
- Integrated Build System: Compile and run code directly from the editor.
- Set build commands

```
Geany > Build > Set Build Commands
```

16. Sublime Text
- Package Control: Manage plugins and themes.
- Install Package Control

```
https://packagecontrol.io/installation
```

- Install a package

```
Ctrl + Shift + P > Package Control: Install Package
```

17. Advanced Editing
- Multi-caret editing

```
Ctrl + Click to place multiple cursors
```

18.  Visual Studio Code
- Extensions: Extend functionality with a wide range of extensions.
- Install extensions

```
Ctrl + Shift + X > Search and install
```

- Integrated Terminal

```
Ctrl + `
```

- Advanced Code Navigation

```
F12
```

#### Summary

Thank you for making it through to the end of LINUX Command-Line for Beginners: A Comprehensive Advanced Starting Guide to Learn Linux
from Scratch to Bash Scripting and Shell Programming, let’s hope it was informative and able to provide you with all of the tools you need to achieve your goals whatever they may be.

Chances are if you’ve made it to this point, it is because you want to know khow you can navigate through the Linux operating system as well as having a clear grasp of the several command lines and also the best ways of using them. You have made it to this point because you want to know all about many different pieces that the Linux operating system comprises and also how you can install different distributions of Linux.



