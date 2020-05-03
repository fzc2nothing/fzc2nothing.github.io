---
layout:     post
title:      计划一下这个暑假
subtitle:   第一次计划
date:       2020-04-11
author:     Zichao
header-img: img/ghostdoll.jpeg
catalog: true
tags:
    - iOS
    - 轮子
---


>**Summer Schedule** 以每一周为分割

# 自五月二号开始的第一周

这一周打算以补基础为主

周六周日看看cs61b，记笔记

每天刷题三道 + 复习老题三道，重看一遍算法视频

## CS 61B 第一节课：

* Polymorphism: The ability to have one method call work on several different classes of objects, even if those classes need different implementations of the method call. For example, one line of code might be able to call the "addItem" method on every kind of List, even though adding an item to a ShoppingList is complelely different from adding an item to a ShoppingCart.

* Inheritance: A class may inherit properties from a more general class. For example, the ShoppingList class inherits from the List class the property of storing a sequence of items.

* ```
    int x;
    x = 1;
 ```

    This Java declaration does two things:
    1. It allocates a chunk of memory big enough to store an integer, which Java calls type "int".
    2. It names the variable (chunk of memory) "x".


* Java programs must be compiled before you can run them. Compilation converts your wirtten code to a machine-readable bytecode.

* A complicated input program:
``` 
    import java.io.*;

    class SimpleIO {
        public static void main (String[] arg) throws Exception {
            BufferedReader keybd = 
                new BufferedReader(new InputStreamReader(System.in));
            System.out.println(keybd.readLine());
        }
    }


