Text Editor in C

A simple terminal-based text editor written in C that allows users to create, edit, navigate, and manage text files directly from the command line.

The project uses a Doubly Linked List to store the text and Stacks to implement Undo and Redo functionality.

📌 Features
✏️ Text Editing
Insert text at the current cursor position
Delete a specified number of characters
Delete the contents of the current line
Display the current contents of the file
↩️ Undo / Redo
Undo – Reverts the most recent editing operation
Redo – Reapplies the last undone operation
🖱️ Cursor Navigation

The editor supports:

Move Up
Move Down
Move Left
Move Right
Go to Start of File
Go to End of File
Go to Start of Line
Go to End of Line
📁 File Handling
Load an existing text file when a filename is provided
Perform editing operations on the loaded file
Prompt the user to save changes before exiting
Save the modified content to a file
🆕 Empty File Handling

If the program is started without a filename:

./text_editor

the editor creates an empty internal buffer.

The user can perform editing operations normally. Before exiting, the program asks for a filename and saves the content to that file.

🧠 Data Structures Used
1. Doubly Linked List

The text is stored using a Doubly Linked List.

Each node represents a portion/character of text and contains links to the previous and next nodes.

NULL <- Node <-> Node <-> Node <-> Node -> NULL

Advantages:

Easy insertion and deletion
Supports movement in both directions
Suitable for cursor navigation
2. Stack

Stacks are used for implementing Undo and Redo operations.

        +---------+
        |  Action |
        +---------+
        |  Action |
        +---------+
        |  Action |
        +---------+
            TOP

When an operation is performed, it can be stored in the Undo stack.

When Undo is performed, the operation is moved to the Redo stack.

🔄 Undo / Redo Flow
             Editing Operation
                    |
                    v
              Undo Stack
                    |
                  Undo
                    |
                    v
              Redo Stack
                    |
                  Redo
                    |
                    v
              Undo Stack

This allows the user to move backward and forward between editing states.

🏗️ Project Structure
Text-Editor/
│
├── text_editor.c
├── README.md
└── text files
⚙️ Technologies Used
C Programming
Doubly Linked List
Stack
Dynamic Memory Allocation
File Handling
Pointers
Structures
Command Line Arguments
🔧 Compilation

Compile the program using GCC:

gcc text_editor.c -o text_editor
▶️ How to Run
Run with an existing file
./text_editor filename.txt

The editor loads the contents of filename.txt and allows the user to modify it.

Run without a file
./text_editor

The editor starts with an empty buffer.

The user can enter text and provide a filename when saving.

📂 File Loading Flow
             Program Start
                   |
          Is filename given?
             /           \
           Yes            No
            |              |
            v              v
      Open the file    Create empty
            |             buffer
            v              |
       Load content        |
            |              |
            +-------+------+
                    |
                    v
              Start Editor
💾 Saving Flow

When the user exits the editor:

             Exit Editor
                  |
                  v
          Save changes?
             /     \
           Yes      No
            |        |
            v        v
       Save File    Exit
            |
            v
           Exit

If the editor was started without a filename, the user is asked to enter a filename before saving.

🧩 Main Operations
Operation	Description
Insert	Inserts text at the current cursor position
Delete Characters	Deletes the specified number of characters
Delete Line	Deletes the contents of the current line
Undo	Reverts the last operation
Redo	Reapplies the last undone operation
Display	Displays the current text
Move Up	Moves cursor to the previous line
Move Down	Moves cursor to the next line
Move Left	Moves cursor one position left
Move Right	Moves cursor one position right
Start of File	Moves cursor to the beginning
End of File	Moves cursor to the end
Start of Line	Moves cursor to the beginning of current line
End of Line	Moves cursor to the end of current line
🔑 Key Concepts Demonstrated

This project demonstrates practical usage of:

Structures
Pointers
Doubly linked lists
Stack implementation
Dynamic memory allocation
File I/O
Command-line arguments
Cursor management
Data manipulation
Undo/Redo mechanisms
🚀 Future Improvements

The project can be enhanced with:

Dynamic buffer resizing
Search functionality
Search and replace
Copy, Cut and Paste
Multiple file support
Syntax highlighting
Improved cursor handling
Keyboard shortcuts
Auto-save functionality
GUI-based text editor
🎯 Learning Outcome

This project provides practical experience in designing a text editor using C data structures and file handling.

It demonstrates how a Doubly Linked List can be used for efficient text manipulation and how Stacks can be used to implement Undo and Redo functionality.

👩‍💻 Author

Harshada Wani

Built using C Programming and Data Structures.
