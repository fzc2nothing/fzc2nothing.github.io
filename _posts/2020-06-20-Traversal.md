---
layout:     post
title:      The order of traversal
subtitle:   
date:       2020-06-20
author:     Zichao
header-img: img/ghostdoll.jpeg
catalog: true
tags:
    - Java
---

## Inorder Traversal
1. Traverse the left subtree, i.e., call Inorder(left-subtree)
2. Visit the root.
3. Traverse the right subtree, i.e., call Inorder(right-subtree)

## Preorder Traversal
1. Visit the root
2. Traverse the left subtree, i.e., call Inorder(left-subtree)
3. Traverse the right subtree, i.e., call Inorder(right-subtree)

## Postorder Traversal
1. Traverse the left subtree, i.e., call Inorder(left-subtree)
2. Traverse the right subtree, i.e., call Inorder(right-subtree)
3. Visit the root