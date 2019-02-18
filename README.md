CStyle-vim-config
==========================


### Introduction ###
Install and configure the YouCompleteMe and some other plugins to build the vim environment for C/C++ project.<br>
It allows you to search words, comment and uncomment codes easily.<br>
It allows you to jump to header files, to declaration and to definition recusively.


### Installation ###
Execute `sudo ./install.sh`.<br>


### General Usage ###
Execute `source ~/.bashrc` after the installation to make `vimc` work.<br>
To start a C/C++ project, execute `vimc` at the root of the project.<br>
Why "at the root of project"? To ensure that searching or jumping in the project works as expected with the help of `.ycm_extra_conf.py` and `.tags` generated by executing `vimc`.<br>



`:Q`:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; quit vim and all plugins, delete `.ycm_extra_conf.py` and `.tags` in the root of project<br>

`\tg`:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; open or close the window of taglist<br>

`\cc`:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; comment one line<br>
`\cm`:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; comment multi lines<br>
`\cu`:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; uncomment<br>

`<C-p>`:&nbsp;&nbsp;&nbsp; search file in project<br>
`\vv`:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; search the word under cursor in project<br>
`\vr`:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; replace the word under cursor in project (`:ReplaceUndo` to undo the replace)<br>

`F12`:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; jump to header file<br>
`<C-]>`:&nbsp;&nbsp;&nbsp; jump to declaration or to definition<br>
`g<C-]>`:&nbsp; jump to the only match or list multi matches<br>
`<C-o>`:&nbsp;&nbsp; go backword<br>
`<C-i>`:&nbsp;&nbsp; go forward<br>

### Tips ###
0) Edit the line 59 to 61 of `ycm_extra_conf.py` to change the searching path of YCM.<br>
1) `<C-]>` is set as `2<C-]>` in `.vim` files, because the second option is normally what you need. If not, type `g<C-]>` then a number to do your choice.<br>
2) For huge/distributed projects, use `F12` before `<C-]>` is recommended if possible.<br>
3) If `tags file not ready` is printed while typing `<C-]>` or `g<C-]>`, it means that the file `.tags` hasn't been generated yet by `ctags`. It is probably because that the project is so huge that `ctags` needs some time to generate the `.tags`.
4) `:help syntastic_quiet_messages` to avoid unexpected error messages from syntastic.


### Some bugs ###
a) Downloading clang may fail while installing YCM. In this case, you need to download clang (`libclang-7.0.0-x86_64-unknown-linux-gnu.tar.bz2` for x86_64) manually from https://dl.bintray.com/micbou/libclang/ and put it into `~/.vim/bundle/YouCompleteMe/third_party/ycmd/clang_archives/`.<br>
b) On Mac OS, you need to install `ctags` with `brew` with the command: `brew install ctags`, and then add ``alias ctags="`brew --prefix`/bin/ctags"`` into the `~/.bashrc`.

### What's more ###
This vim config doesn't offer you a way to format your code. Because code formatter is heavey but not necessary, also, it doesn't support the newest C/C++ very well. You can install and config by yourself a code formatter, such as `astyle`.


### References ###
https://github.com/VundleVim/Vundle.vim (vim plugin manager)<br>
https://github.com/Valloric/YouCompleteMe<br>
https://github.com/rdnetto/YCM-Generator<br>
https://github.com/tpope/vim-pathogen (start YCM automatically while executing vim)<br>
https://github.com/scrooloose/nerdtree<br>
https://github.com/vim-syntastic/syntastic<br>
https://github.com/dkprice/vim-easygrep<br>
https://github.com/ctrlpvim/ctrlp.vim<br>
https://github.com/scrooloose/nerdcommenter<br>
https://github.com/vim-scripts/taglist.vim<br>
https://github.com/vim-scripts/Conque-GDB<br>
https://github.com/rstacruz/sparkup<br>
https://github.com/tpope/vim-fugitive<br>
https://github.com/tomasiser/vim-code-dark<br>
