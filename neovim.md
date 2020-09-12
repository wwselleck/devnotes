# Neovim

## Terminal
- Enter the terminal and input keys
  - `exe 'term' | exe 'star' | call feedkeys('abc\<CR>')`
    - `exe term` runs :term
    - `exe star` enters insert mode
    - `feedkeys` sends the keys to the terminal
