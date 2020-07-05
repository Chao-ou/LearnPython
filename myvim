"Call Vundle{
" Before Use Vundle need to do this{
" be iMproved
" required!
set nocompatible
filetype off
"}
set rtp+=~/.vim/bundle/vundle/
call vundle#rc()
" let Vundle manage Vundle
" required!
Bundle 'gmarik/vundle'
"}


Bundle 'airblade/vim-gitgutter'
Bundle 'surround.vim'
Bundle 'stegtmeyer/find-complete'

"LeaderF{
"Bundle 'Yggdroot/LeaderF'
"let g:Lf_ShortcutF = '<C-P>'
"}

"status line{
Bundle 'scrooloose/syntastic'
set statusline+=%#warningmsg#
set statusline+=%{SyntasticStatuslineFlag()}
set statusline+=%*
"let g:syntastic_always_populate_loc_list = 0
"let g:syntastic_auto_loc_list = 1
"let g:syntastic_check_on_open = 1
let g:syntastic_check_on_w = 1
let g:syntastic_check_on_wq = 1
"let g:syntastic_cpp_check_header = 0
"let g:syntastic_cpp_no_include_search = 1
"}


"Taglist{
Bundle 'taglist.vim'

let Tlist_Show_One_File=1     "不同时显示多个文件的tag，只显示当前文件的
let Tlist_Exit_OnlyWindow=1   "如果taglist窗口是最后一个窗口，则退出vim
let Tlist_Ctags_Cmd="/usr/bin/ctags" "将taglist与ctags关联
let Tlist_Use_SingleClick=1
let Tlist_Auto_Open=1
let Tlist_Auto_Start=1

let tags_file=findfile("tags", ".;")
if !empty(tags_file) && filereadable(tags_file)
    exe 'set tags+='.tags_file
endif
"}


"cscope-gatgs{
Bundle 'gtags.vim'
"set cscopequickfix=s-,c-,d-,i-,t-,e-,g-
nmap <C-R>a :cs find a <C-R>=expand("<cword>")<CR><CR> "查找该符号被修改的地方
nmap <C-R>s :cs find s <C-R>=expand("<cword>")<CR><CR> "查找C语言符号，即查找函数名、宏、枚举值等出现的地方（包括头文件）
nmap <C-R>g :cs find g <C-R>=expand("<cword>")<CR><CR> "查找函数、宏、枚举等定义的位置，类似ctags所提供的功能（比如有可能只在头文件处）
nmap <C-R>d :cs find d <C-R>=expand("<cword>")<CR><CR> "查找本函数调用的函数
nmap <C-R>c :cs find c <C-R>=expand("<cword>")<CR><CR> "查找调用本函数的函数
nmap <C-R>t :cs find t <C-R>=expand("<cword>")<CR><CR> "查找本字符串
nmap <C-R>e :cs find e <C-R>=expand("<cword>")<CR><CR> "查找egrep模式，相当于egrep功能，但查找速度快多了
nmap <C-R>f :cs find f <C-R>=expand("<cword>")<CR><CR> "查找并打开文件，类似vim的find功能
nmap <C-R>i :cs find i ^<C-R>=expand("<cword>")<CR>$<CR> "查找包含本文件的文件

if has("cscope")
	set csprg=$HOME/local/bin/gtags-cscope
	set cscopetag "是否启用 cscope 的数据库给 tag 用 (like Ctrl+],Ctrl+t)
	set csto=1    "cscope 数据库的优先级(0:cscope 优先，1:tag 文件优先)
    set cspc=3 "显示文件路径的深度
	let csdb_name="GTAGS"
	set nocsverb
	" add any database in current directory
	let csdb_name="GTAGS"
	if filereadable(csdb_name)
		exe "cs add" csdb_name
	else
        let cscope_file=findfile(csdb_name, ".;")  "findfile $1==>filename,$2==>path,end by ;
		if !empty(cscope_file) && filereadable(cscope_file)
			exe "cs add" cscope_file
		endif
	endif
"	set csverb
endif
"}

"powerline{
Bundle 'Lokaltog/vim-powerline'
"set guifont=PowerlineSymbols for Powerline
set nocompatible
set t_Co=8
set t_Sb=^[[4%dm
set t_Sf=^[[3%dm
let g:Powerline_symbols='unicode'
"}

"rainbow{
Bundle 'rainbow_parentheses.vim'
let g:rbpt_colorpairs = [
	\ ['brown',       'RoyalBlue3'],
	\ ['red',         'firebrick3'],
	\ ['Darkblue',    'SeaGreen3'],
	\ ['darkgray',    'DarkOrchid3'],
	\ ['darkgreen',   'firebrick3'],
	\ ['darkcyan',    'RoyalBlue3'],
	\ ['white',     'SeaGreen3'],
	\ ['darkmagenta', 'DarkOrchid3'],
	\ ['brown',       'firebrick3'],
	\ ['gray',        'RoyalBlue3'],
	\ ['darkmagenta', 'DarkOrchid3'],
	\ ['Darkblue',    'firebrick3'],
	\ ['darkred',     'DarkOrchid3'],
	\ ['darkgreen',   'RoyalBlue3'],
	\ ['darkcyan',    'SeaGreen3'],
	\ ['yellow',       'SeaGreen3'],
	\ ]

let g:rbpt_max = 16
au VimEnter * RainbowParenthesesToggle
au Syntax * RainbowParenthesesLoadRound
au Syntax * RainbowParenthesesLoadSquare
au Syntax * RainbowParenthesesLoadBraces
"}

"显示行数
set nu

"使能鼠标
set mouse=a

"语法高亮
syntax on

"递增搜索
set incsearch

"检测文件的类型
filetype plugin indent on

"记录历史的行数
set history=1000

"自动对齐
set autoindent
set cindent

"智能选择对齐方式
set smartindent

"展开TAB键为空格
set expandtab
"tab为4个空格
set tabstop=4

"当前行之间交错时使用4个空格
set shiftwidth=4

"设置匹配模式，输入做括号会出现右括号
set showmatch

"编辑时显示光标状态
set ruler

"高亮查找
set hlsearch

" 命令行显示输入的命令
set showcmd
" 命令行显示vim当前模式
set showmode
"显示tab补全扩展栏
set wildmenu

"Invert copy with mouse status{
let copy_status=0
let has_taglist=0
function! Invert_copy_status()
	if g:copy_status == 1
        GitGutterEnable
		let g:copy_status = 0
		set mouse=a
	    if g:has_taglist == 1
			TlistOpen
            wincmd p  "恢复当前窗口位置的Patch
		endif
        if exists('+colorcolumn')
            set colorcolumn=80
        endif
		set nu
        set nopaste
	else
        GitGutterDisable
		let g:copy_status = 1
		set mouse=v
		let g:has_taglist = bufwinnr(g:TagList_title)
	    if g:has_taglist != -1
			TlistClose
		endif
        if exists('+colorcolumn')
            set colorcolumn=0
        endif
		set nonumber
        set paste
	endif
endfunction

if exists('+colorcolumn')
 set colorcolumn=80
endif

map <C-c> :call Invert_copy_status()<CR>
map <C-k> :q!<CR>
map <C-x> :set noexpandtab
"}

map ZZ :qa<CR>

"remember last view line{
au BufReadPost * if line("'\"") > 0|if line("'\"") <= line("$")|exe("norm '\"")|else|exe "norm $"|endif|endif
"}

"remove all trailing whitespace{
"autocmd BufWritePre * %s/\s\+$//e
"}

"set mvim fonts&theme{
set guifont=Monaco:h16
colorscheme desert
"}

let mapleader = ","
nnoremap <leader>j :tjump /
set path=.,**

"default encoding as utf-8
set encoding=utf-8

"Set backspace type{
set backspace=2
"  set backspace=[012]
"  " 0:same as ":set backspace=" (Vi compatible)
"  " 1:same as ":set backspace=indent,eol"
"  " 2:same as ":set backspace=indent,eol,start"

"{
Bundle 'easymotion/vim-easymotion'
let g:EasyMotion_smartcase = 1
let g:EasyMotion_startofline = 0 " keep cursor colum when JK motion
map <Leader><leader>h <Plug>(easymotion-linebackward)
map <Leader><Leader>j <Plug>(easymotion-j)
map <Leader><Leader>k <Plug>(easymotion-k)
map <Leader><leader>l <Plug>(easymotion-lineforward)
" 重复上一次操作, 类似repeat插件, 很强大
map <Leader><leader>. <Plug>(easymotion-repeat)
"}
