# SPTK with waf

-----------------

# Description 

Waf integration to build [Speech Signal Processing Toolkit (SPTK) library ](http://sp-tk.sourceforge.net/)　with C and C++ Compliers. 

**SPTKを自分のコードから呼びたい人向けです。**

* SPTKを共有ライブラリとしてインストールできます。
* C、C++の好きな方でコンパイルできます。
* wafが使えます（速い、出力がキレイ）
* 自分のC、C++コードからSPTKのメソッドを呼べます。
* コマンドラインツールはインストールされません。
   

コマンドラインツールを使いたい人は、元のconfigure scriptを使えばOKです。

# Branches

- master : c++ 向け
- gcc: c向け
- g++: c++向け（master にマージされる）

# About the SPTK
    
see README.org

# Platform

* Unix系
* Ubuntu 12.04 LTS 64bit, Mac OS X 10.9 で最低限確認済

# Getting started

## Build

     ./waf configure && ./waf

## Build with clang++

     CXX=clang++ ./waf configure && ./waf

## Build with gcc

     git checkout gcc
     ./waf configure && ./waf

## Build with clang

     git checkout gcc
     CC=clang ./waf configure && ./waf

## Install 

     sudo ./waf install

* Include files: `/usr/local/include/SPTK`
* Library: `/usr/local/lib/SPTK`
* Pkg-config: `/usr/local/lib/pkgconfig`

オリジナルのSPTKとはインストール場所が異なります（オリジナルは、`/usr/local/SPTK`）

# How to use

`<SPTK/SPTK.h>` をインクルードして、好きな関数を呼ぶ

コンパイルは、例えば以下のようにする

     g++ test.cpp `pkg-config SPTK --cflags --libs`

面倒なので、example/ 内のコードを修正して使う（wafを使おう）のがおすすめです。