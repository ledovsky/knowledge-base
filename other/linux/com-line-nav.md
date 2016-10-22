# Работа в терминале Unix
Date: 2016-02-23

## Навигация

    ~                                   home folder
    /                                   root folder
    ..                                  upper level folder
    ls                                  list files and directories
    ls -a                               list all (including hidden files)
    ls -l                               list with details
    cd <folderName>                     change directory
    pwd                                 current working directory

## Работа с файлами

Наиболее необходимые

    cp <file> <path>                    copy
    rm <file>                           remove file
    rm -r <folder>                      remove folder
    ls -a | grep expr | xargs rm        search and remove
    mv <file/folder> <path/folder>      move file/folder to folder
    mv file.txt file2.txt               rename file
    mkdir <folder>                      make new folder
    touch <file>                        create file
    less <file>                         view file content

    cp image.jpg newimage.jpg           copy and rename a file
    cp image.jpg <folderName>/          copy to folder
    cp image.jpg folder/newName.jpg     
    cp -R stuff otherStuff              copy and rename

    head (-n <n_line>) <filename>       outputs the first n lines of file
    tail (-n <n_line>) <filename>       outputs the last 10 lines of file

    cat <file>                          read file to command line
    cat > <file>                        write command-line input to file
    ln -s                               create symbolic link

    chmod +x <filename>                 set permission - executable

## Создание сокращений (alias)

    alias ls="ls -a"


## Горячие клавиши

*add more page*

    CTRL L                              Clear the terminal
    CTRL A                              Move to start of line
    CTRL E                              Move to the end of line
    CTRL U                              Delete all left of the cursor
    META F                              Move forward a word
    META B                              Move backward a word
    TAB                                 Auto completion of file or command

Meta is ALT key normally. For Mac OS X users: you must enable in yourself. Open Terminal > Preferences > Settings > Keyboard, and enable Use option as meta key.

## Полезные команды

    !!                                  repeat previous command


[Bash Cheatsheet - LeCoupa](https://gist.github.com/LeCoupa/122b12050f5fb267e75f)



