#GEM3D Standard Coding Style

##.clang-format
The style options are based on the [GEM3D standard coding style guide](https://github.com/GEM3D/basics/blob/master/coding_style/GEM3D_Coding_Standard.pdf).

    Requirements:
      Clang v.3.8.0
    
    USAGE: clang-format -style=file [<file> ...]
    
Vim Integration:

There is an integration for vim which lets you run the clang-format standalone tool on your current buffer, 
optionally selecting regions to reformat. The integration has the form of a python-file which can be found 
under clang/tools/clang-format/clang-format.py.

This can be integrated by adding the following to your .vimrc:

    map <C-K> :pyf <path-to-this-file>/clang-format.py<cr>
    imap <C-K> <c-o>:pyf <path-to-this-file>/clang-format.py<cr>

The first line enables clang-format for NORMAL and VISUAL mode, the second line adds support for INSERT mode. 
Change “C-K” to another binding if you need clang-format on a different key (C-K stands for Ctrl+k).

With this integration you can press the bound key and clang-format will format the current line in NORMAL and 
INSERT mode or the selected region in VISUAL mode. The line or region is extended to the next bigger syntactic entity.

It operates on the current, potentially unsaved buffer and does not create or save any files. To revert a formatting, 
just undo.