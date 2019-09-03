Pomme-c-vim
==========================


### Introduction ###
Pomme-c-vim can build a vim-plugin-based environment for c/c++. It will install and configure the YouCompleteMe and some other plugins.<br>
It allows you to search and replace words, comment and uncomment codes.<br>
It allows you to jump to header file, to declaration and to definition recusively.<br>
It allows you to create files with templates.<br>
It allows you to format codes with K&R style.


### Installation ###
Execute `./install.sh`.<br>


### General Usage ###
Execute `source ~/.bashrc` after the installation to make `vimc` work.<br>
To start a C/C++ project, execute `vimc` at the root of the project.<br>
Why "at the root of project"? To ensure that searching or jumping in the project works as expected with the help of `.ycm_extra_conf.py`, `.tags` and `.clang-format` generated by executing `vimc`.<br>



`:Q<CR>`: quit vim and all plugins, delete `.ycm_extra_conf.py`, `.clang-format` and `.tags` in the root of project<br>

`\tg`: open or close the window of taglist<br>

`<F6>`: format the current file<br>

`\cc`: comment one line<br>
`\cv`: comment one line with next delimiter.<br>
`\cm`: comment multi lines<br>
`\c$`: comment to end of line<br>
`\cu`: uncomment<br>

`<C-p>`: search file in project<br>

`\vv`: search the word under cursor in project<br>
`\vr`: replace the word under cursor in project (`:ReplaceUndo` to undo the replace)<br>
`cgt`: save changes and close all tabs except the first, then close the bottom-right window (`\vr`+`cgt` is recommanded)<br>

`<F12>`:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; jump to header file<br>
`<C-]>`:&nbsp;&nbsp;&nbsp; jump to declaration or to definition<br>
`g<C-]>`:&nbsp; jump to the only match or list multi matches<br>
`<C-o>`:&nbsp;&nbsp; go backword<br>
`<C-i>`:&nbsp;&nbsp; go forward<br>



To get more information about usage, click on the links at the References below.


### Tips ###
0) Edit the line 59 to 61 of `ycm_extra_conf.py` to change the searching path of YCM.<br>
1) Edit the template files at `~/.vim/templates/` to customize the templates for `.h`, `.hpp`, `.c` and `.cpp`.<br>
2) `<C-]>` is set as `2<C-]>` in `.vim` files, because the second option is normally what you need. If not, type `g<C-]>` then a number to do your choice.<br>
3) For huge/distributed projects, use `<F12>` before `<C-]>` is recommended if possible.<br>
4) If `tags file not ready` is printed while typing `<C-]>` or `g<C-]>`, it means that the file `.tags` hasn't been generated yet by `ctags`. It is probably because that the project is so huge that `ctags` needs some time to generate the `.tags`.<br>
5) After typing `C-p` and selecting a file, type `F12` is recommanded to refresh the Nerdtree.<br>
6) `:help syntastic_quiet_messages` to avoid unexpected error messages from syntastic.


### Some bugs ###
a) Downloading clang may fail while installing YCM. In this case, you need to download clang (`libclang-7.0.0-x86_64-unknown-linux-gnu.tar.bz2` for x86_64) manually from https://dl.bintray.com/micbou/libclang/ and put it into `~/.vim/bundle/YouCompleteMe/third_party/ycmd/clang_archives/`.<br>
b) Omnisharp for c# may fail on downloading for some reason. This error can be ignored if you don't use c#. Otherwise, you can manually download it from https://github.com/OmniSharp/omnisharp-roslyn/releases/download/v1.32.19/omnisharp.http-linux-x64.tar.gz and move it into `~/.vim/bundle/YouCompleteMe/third_party/ycmd/third_party/omnisharp-roslyn/v1.32.19/`.<br>
c) On Mac OS, you need to install `ctags` with `brew` with the command: `brew install ctags`, and then add ``alias ctags="`brew --prefix`/bin/ctags"`` into the `~/.bashrc`.



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
https://github.com/rstacruz/sparkup<br>
https://github.com/tpope/vim-fugitive<br>
https://github.com/Yggdroot/indentLine<br>
https://github.com/tomasiser/vim-code-dark<br>
