# Tools

## GDAL
### Resources
* GDAL 中文教程 [http://headfirst-gdal.readthedocs.io/en/latest/preface.html](http://headfirst-gdal.readthedocs.io/en/latest/preface.html)
* GDAL python Cookbook [https://pcjericks.github.io/py-gdalogr-cookbook/index.html\#](https://pcjericks.github.io/py-gdalogr-cookbook/index.html#)
* GDAL official [http://www.gdal.org/index.html](http://www.gdal.org/index.html)
* GDAL python API [http://gdal.org/python/](http://gdal.org/python/)
* python source code search [http://nullege.com/codes](http://nullege.com/codes)

### Key pages
* OGR Architecture [http://gdal.org/ogr\_arch.html](http://gdal.org/ogr_arch.html)

## VIM
### my .vimrc
```
"""""""""""""""""""""""""""""""""""""""""""""""""""""""
" Vundle plugins
set nocompatible              " be iMproved, required
filetype off                  " required

set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
Plugin 'VundleVim/Vundle.vim'
Plugin 'Valloric/YouCompleteMe'
call vundle#end()            " required
filetype plugin indent on    " required
"""""""""""""""""""""""""""""""""""""""""""""""""""""""

syntax on
colorscheme elflord
set ruler
set number
set tabstop=4
set shiftwidth=4
```
install youcompleteme from vundle

## Screen
### run screen by script
```
CUDA_VISIBLE_DEVICES=0 screen -dmS test th trainLSTM.lua
```
