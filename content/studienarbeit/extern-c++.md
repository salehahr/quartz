---
title: extern c++
date: "2021-01-11"
external_url: "http://en.cppreference.com/w/cpp/language/storage_duration"
tags:
  - -sa/processed
  - software/cpp
---

[http://en.cppreference.com/w/cpp/language/storage\_duration](http://en.cppreference.com/w/cpp/language/storage_duration)

is a storage class specifier that controls storage duration and its linkage.

extern - static or thread storage duration and external linkage

**Storage duration**

*   static:
    *   storage for the object is allocated when the program begins and deallocated when the program ends.
    *   only one instance of the object exists
*   thread
    *   storage for the object is allocated when the thread begins and deallocated when the thread ends
    *   each thread has its own instance of the object
        

**Linkage**

*   If a name has **linkage**, it refers to the **same entity** as the same name introduced by a declaration in another scope
*   If a variable, function, or another entity with the same name is declared in several scopes, but does not have sufficient linkage, then several instances of the entity are generated.
    

external linkage:
variables and functions with external linkage also have [language linkage](http://en.cppreference.com/w/cpp/language/language_linkage), which makes it possible to link translation units written in different programming languages.

