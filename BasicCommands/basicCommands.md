# Open <filename> in vim
        vim <filename>

# Open up built-in help docs about <topic> if any exists   
        :help <topic>    

# Quit vim    
        :q               
    
# Save current file    
        :w

# Save file and quit vim               
        :wq             
    
# Save file and quit vim   
        ZZ               
    
# Quit vim without saving file
# ! *forces* :q to execute, hence quiting vim without saving   
        :q!              

# Quit vim without saving file                     
        ZQ               
    
# Save file and quit vim, shorter version of :wq    
        :x               

# Undo
        u  

# Redo              
        CTRL+R           

# Move left one character
        h 

# Move down one line               
        j                   
    
# Move up one line   
        k                

# Move right one character
        l                

# Move back one full screen
        Ctrl+B 	         
    
# Move forward one full screen
        Ctrl+F 	         

# Move forward 1/2 a screen
        Ctrl+D 	         
    
# Move back 1/2 a screen
        Ctrl+U
    
    
# Moving within the line

        0                # Move to beginning of line
        $                # Move to end of line
        ^                # Move to first non-blank character in line

# Searching in the text

        /word            # Highlights all occurrences of word after cursor
        ?word            # Highlights all occurrences of word before cursor
        n                # Moves cursor to next occurrence of word after search
        N                # Moves cursor to previous occurrence of word

        :%s/foo/bar/g    # Change 'foo' to 'bar' on every line in the file
        :s/foo/bar/g     # Change 'foo' to 'bar' on the current line
        :%s/\n/\r/g      # Replace new line characters with new line characters

# Jumping to characters

        f<character>     # Jump forward and land on <character>
        t<character>     # Jump forward and land right before <character>

        # For example,
        f<               # Jump forward and land on <
        t<               # Jump forward and land right before <

# Moving by word

        w                # Move forward by one word
        b                # Move back by one word
        e                # Move to end of current word

# Other characters for moving around

        gg               # Go to the top of the file
        G                # Go to the bottom of the file
        :NUM             # Go to line number NUM (NUM is any number)
        H                # Move to the top of the screen
        M                # Move to the middle of the screen
        L                # Move to the bottom of the screen

        i                # Puts vim into insert mode, before the cursor position
        a                # Puts vim into insert mode, after the cursor position
        v                # Puts vim into visual mode
        :                # Puts vim into ex mode
        <esc>            # 'Escapes' from whichever mode you're in, into Command mode

# Copying and pasting text
        # Operations use the vim register by default
        # Think of it as vim's private clipboard

        # Yank ~ copy text into vim register
        y                # Yank whatever is selected
        yy               # Yank the current line

                        # Delete ~ yank text and delete from file
        d                # Delete whatever is selected
        dd               # Delete the current line

        p                # Paste text in vim register after the current cursor position
        P                # Paste text in vim register before the current cursor position

        x                # Delete character under current cursor position

        # 'Verbs'

        d                # Delete
        c                # Change
        y                # Yank (copy)
        v                # Visually select

# 'Modifiers'

        i                # Inside
        a                # Around
        NUM              # Number (NUM is any number)
        f                # Searches for something and lands on it
        t                # Searches for something and stops before it
        /                # Finds a string from cursor onwards
        ?                # Finds a string before cursor

# 'Nouns'

        w                # Word
        s                # Sentence
        p                # Paragraph
        b                # Block

# Sample 'sentences' or commands

        d2w              # Delete 2 words
        cis              # Change inside sentence
        yip              # Yank inside paragraph (copy the para you're in)
        ct<              # Change to open bracket
                        # Change the text from where you are to the next open bracket
        d$               # Delete till end of line

        >                # Indent selection by one block
        <                # Dedent selection by one block
        :earlier 15m     # Reverts the document back to how it was 15 minutes ago
        :later 15m       # Reverse above command
        ddp              # Swap position of consecutive lines, dd then p
        .                # Repeat previous action
        :w !sudo tee %   # Save the current file as root
        :set syntax=c    # Set syntax highlighting to 'c'
        :sort            # Sort all lines
        :sort!           # Sort all lines in reverse
        :sort u          # Sort all lines and remove duplicates
        ~                # Toggle letter case of selected text
        u                # Selected text to lower case
        U                # Selected text to upper case
        J                # Join the current line with the next line
    
# Fold text
        zf               # Create fold from selected text
        zo               # Open current fold
        zc               # Close current fold
        zR               # Open all folds
        zM               # Close all folds

        qa               # Start recording a macro named 'a'
        q                # Stop recording
        @a               # Play back the macro


# Other Commands


        " Example ~/.vimrc
        " 2015.10

        " Required for vim to be iMproved
        set nocompatible

        " Determines filetype from name to allow intelligent auto-indenting, etc.
        filetype indent plugin on

        " Enable syntax highlighting
        syntax on

        " Better command-line completion
        set wildmenu

        " Use case insensitive search except when using capital letters
        set ignorecase
        set smartcase

        " When opening a new line and no file-specific indenting is enabled,
        " keep same indent as the line you're currently on
        set autoindent

        " Display line numbers on the left
        set number

        " Indentation options, change according to personal preference

        " Number of visual spaces per TAB
        set tabstop=4

        " Number of spaces in TAB when editing
        set softtabstop=4

        " Number of spaces indented when reindent operations (>> and <<) are used
        set shiftwidth=4

        " Convert TABs to spaces
        set expandtab

        " Enable intelligent tabbing and spacing for indentation and alignment
        set smarttab
