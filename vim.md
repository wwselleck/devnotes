# Vim

## Workflows
- 🎥 [A Vid in which Vim Saves Me Hours & Hundreds of Clicks](https://www.youtube.com/watch?v=hraHAZ1-RaM)
- 📝 [A modern terminal workflow](https://wrotenwrites.com/a_modern_terminal_workflow_2/)

## Search & Replace
-  https://vim.fandom.com/wiki/Search_and_replace
- :s[ubstitute]
  - :s/foo/bar/g - Replace all on line
  - :%s/foo/bar/g - Replace all in file
  - :%s/foo/bar/gc - Change w/ confirmation
  - Save typing by use \zs and \ze
    - Wrong: :s/Copyright 2007 All Rights Reserved/Copyright 2008 All Rights Reserved/
    - Right: :s/Copyright \zs2007\ze All Rights Reserved/2008/
    
## Q&A 
- 💭 [What is the difference between the remap, noremap, nnoremap and vnoremap mapping commands in Vim?](https://stackoverflow.com/questions/3776117/what-is-the-difference-between-the-remap-noremap-nnoremap-and-vnoremap-mapping)
