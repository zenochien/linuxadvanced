---
title : "Linux Advanced"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 1.4 </b> "
---

#### 1. Bash Shortcuts Commands

| Navigation    | Description                         | Editing       | Description                                                        | History       | Description                                 |
|---------------|-------------------------------------|---------------|--------------------------------------------------------------------|---------------|---------------------------------------------|
| **Ctrl \+ A** | Move to the beginning of the line\. | **Ctrl \+ U** | Cut/delete from the cursor position to the beginning of the line\. | **Ctrl \+ R** | Search command history \(reverse search\)\. |
| **Ctrl \+ E** | Move to the end of the line\.       | **Ctrl \+ K** | Cut/delete from the cursor position to the end of the line\.       | **Ctrl \+ G** | Escape from history search mode\.           |
| **Ctrl \+ B** | Move back one character\.           | **Ctrl \+ W** | Cut/delete the word before the cursor\.                            | **Ctrl \+ P** | Go to the previous command in history\.     |
| **Ctrl \+ F** | Move forward one character\.        | **Ctrl \+ Y** | Paste the last cut text\.                                          | **Ctrl \+ N** | Go to the next command in history\.         |
| **Alt \+ B**  | Move back one word                  | **Ctrl \+ L** | Clear the screen\.                                                 | **Ctrl \+ C** | Terminate the current command\.             |
| **Alt \+ F**  | Move forward one word\.             |               |                                                                    |               |                                             |

#### 2. Basic Terminal

![Basic Commands](/images/1-Introduce/basic-commands.jpg)

#### 3. Vim (Vi) Shortcuts Commands:

| Normal Mode  | Description                                                       | Command Mode                   | Description                                              | Visual Mode | Description                       |
|--------------|-------------------------------------------------------------------|--------------------------------|----------------------------------------------------------|-------------|-----------------------------------|
| **i**        | Enter insert mode at the current cursor position.                 | **:w**                         | Save the file.                                           | **v**       | Enter visual mode to select text. |
| **x**        | Delete the character under the cursor.                            | **:q**                         | Quit Vim.                                                | **y**       | Copy the selected text.           |
| **dd**       | Delete the current line.                                          | **:q!**                        | Quit Vim without saving changes.                         | **d**       | Delete the selected text.         |
| **yy**       | Copy the current line.                                            | **:wq**                        | Save and quit Vim.                                       | **p**       | Paste the copied or deleted text. |
| **p**        | Paste the copied or deleted text below the current line.          | **:s/old/new/g**               | Replace all occurrences of “old” with “new” in the file. |             |                                   |
| **u**        | Undo the last change.                                             | **:set nu** or **:set number** | Display line numbers.                                    |             |                                   |
| **Ctrl + R** | Redo the last undo.                                               |                                |                                                          |             |                                   |
| **ESC**      | Exit from insert or command-line mode and return to command mode. |                                |                                                          |             |                                   |
