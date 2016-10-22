# Полезные инструменты в Unix

## Удаление папок пользователя Pictures, Videos и пр.

Изменить файлы  ~/.config/user-dirs.dirs, and ~/.gtk-bookmarks.

## Работа с буфером обмена

Linux

    cat file.txt | xclip -selection c
    xclip -selection clipboard -o > test.txt

Mac

    cat file.txt | pbcopy
    pbpaste > test.txt


