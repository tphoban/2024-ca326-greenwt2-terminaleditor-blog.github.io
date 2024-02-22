## 2023-10-10 Change of Idea
We had our first meeting with our supervisor, Stephen Blott. We proposed creating an AI-based project which makes predictions based on accident data. After having discussed the advantages and disadvantages, we decided to leave this idea and instead develop a terminal-based editor which could be deployed in an educational context (CA116/CA117)

## 2023-10-13 Project Proposal
Today we submitted our proposal for the TTENS project. TTENS is a terminal text editor which is tailored towards novice programmers. It acts as a user-friendly alternative to terminal-based editors such as "Nano" and "Vim". The acronym is short for Terminal Text Editor for Novice Programmers.

The project is planned to be developed in a Linux environment, with C++ as the primary language.

## 2023-11-27 Useful Resources
As part of our research, we have found some useful resources which could be of use for both implementing and better understanding text editors in general.

The Craft of Text Editing is a book which takes you through the process of developing a text editor. Admittedly, the book uses C as the language of teaching, but since C and C++ share many similarities we can still take inspiration and gain a deeper understanding of text editors.

We have also found some external libraries/tools that we plan to incorporate into our project. All relevant references will be included in our functional specification.

## 2023-12-01 Functional Specification
During the previous week, we wrote most of the specfication, which meant that today we just had to add some minor tweaks and diagrams. We managed to upload before the 5pm deadline.

Apart from working on the functional specs, we have continued to read through our resources and conduct further research.

## 2024-01-02 Return
After a challenging semester and having rested during the winter break, we are motivated and ready to commence project work again. Today we put focus on uploading the blog to our git repo. One of the team members had already written some entries but forgotten to upload it from their local desktop.

In the coming days we plan to devlop the core functionality of the project, namely creating, editing, saving and deleting text files. Once the editor has a strong base, we can then begin working on the shortcut implementation, which is one of our main objectives.

## 2024-01-08 Foundation Editor
The development process has proceeded smoothly and we have managed to implement a foundational version of the editor. It has core features such as creating, editing and saving files. Currently, we are trying to fix some strange behaviour caused by the arrow keys. This has proven difficult to solve. We have also realised that implementing shortcuts such as copy (CTRL + C), paste (CTRL + V) and undo (CTRL + Z) is not a straightforward process, since ncurses does not directly support reading the clipboard. We believe that external libraries such as xclip and xsel could solve this problem. Moreover, both CTRL + C and CTRL + Z are special key combinations which are used to forcefully shut down programs, making development a lot more difficult.

## 2024-01-14 Syntax Highlighting
To implement syntax highlighting, we have decided to use Pygments. This is a popular syntax highlighting tool which gives colour and style to syntax, making it more readable and easy to understand. We have also implemented the paste shortcut, which now works on both WSL and other Linux systems.

## 2024-02-06 Undo Shortcut
Development is progessing well. Shortcuts such as copy, paste, cut, save and exit have been incorporated into the editor, albeit with some minor bugs in relation to the cursor position. Regarding shortcuts, we plan to implement undo, which would mean that all major shortcuts can be used within the editor. There seems to be a number of tutorials for developing undo/redo functionality such as https://www.geeksforgeeks.org/implement-undo-and-redo-features-of-a-text-editor/ and https://www.mattduck.com/undo-redo-text-editors.html. We hope that these can inspire us to create our own solution. Once we have implemented this, focus can then be placed on ironing out bugs in areas such as syntax highlighting and cursor position.

## 2024-02-13 Undo and Redo implemented
Both undo and redo functionalities have now been implemented into the project. The StateManager class handles this, which acts as a doubly linked list. Linewise selection (CTRL + A) has also been added, meaning that the user can now select multiple lines for selection. We took inspiration from Vim's selection mode. CTRL + A is probably not the most intuitive binding, but that is not high on our priorities for now. In the meantime, we plan to figure out how to handle tabs and add linting mode (CTRL + L), which notifies the user about potential code errors. Due to linters being highly language-specific, we have decided to place focus on linting in Python, since this is the language used by beginners. The decision of linter was between Pylint, Flake8 and Ruff, but we belive that Ruff suits our project needs best due to its extreme speed. Once we have completed these tasks, we can then focus on ironing out known issues and writing the associated documentation for TTENS.

## 2024-02-19 Final Touches
Since the last blog entry, we have done what we set out to do. Known issues have been handled such as linewise/text selection display issues, cursor movement after pasting and copying special characters such as '\n'. We have even written a script which compiles the TTENS executable and adds a symbolic link to the bin folder, meaning that TTENS is part of the PATH and can be run from any directory on the system. This makes running the program intuitive and follows the convention of editors such as nano, vim, etc. Linting mode has not yet been implemented, however. We plan to have the user manual, technical specifications and linting mode done by the 21st so that we can ensure that no significant bugs have been introduced and give ourselves time for recording the video walkthrough of using TTENS. If linting mode can not be implemented by the 21st, we may have to consider leaving it out.