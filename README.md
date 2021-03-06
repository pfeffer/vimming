# To use:

1. Fork the repo to your own account.

2. On the command line:

  ```
  $ git clone git@github.com:[YOUR_USERNAME]/vimming.git ~/.vim
  $ ln -s ~/.vim/vimrc ~/.vimrc
  $ cd ~/.vim
  $ git submodule init
  $ git submodule update
  ```

3. Open `vim` and enjoy.

# Things to note

- The leader key is the spacebar.
- tabstop/shiftwidth/softtabstop is 2

## Searching

- Search is using the_silver_searcher instead of grep.
- `K` (shift + k) while on a word, will grep for the word in the code base.
  - `foo_bar` will also find `foo_bar_something`
- `KK` (shift + kk) while on a word, will grep for the tag (just the word) in the code base.
  - `foo_bar` will not find `foo_bar_something`
- `<Leader>/` will unhighlight the search terms.

## Git (Fugitive)

- `:Gstatus` will display a window buffer with the git status.
 - If you place your cursor over a file and press Enter, it will open in the
   buffer above.
 - If you place your cursor over a file and press `D`, the diff of that file
   will be displayed.
 - If you place your cursor over a file and press `-`, the file will be placed
   in staging (`git add`), or removed from staging if it was already there (`git
   reset`).
- `:Gcommit` will open a window buffer where you can enter your commit message.
  Saving the message will commit the file.
- You have access to git commands via `:Git`
  - `:Git push origin master`, for instance will push to master.
- `:Gdiff` on a file with changes will open a diff buffer.
  - In order to revert changes, select the part of the code and use `:diffget`,
    this will get the changes from the diff buffer.
  - If you're in the diff buffer and want the send the changes to your file,
    `:diffput`.
