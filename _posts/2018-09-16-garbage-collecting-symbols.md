---
layout: post
title:  "Garbage Collecting Symbols"
date:  2018-09-16
categories: ruby gc
---
Ruby 2.2 introduced symbol GC.

Prior to symbol GC, if a ruby application took in user input and transformed it into a symbol, it could be DOSed through the creation of many unique symbols.

Symbol GC introduced the concept of immortal vs mortal symbols:
- Immortal symbols aren't garbage collected. They are created through `def foo`  and `:bar`.
- Mortal symbols are garbage collected. They are symbols are created through `baz.to_sym`.

Different behavior can be observed in these three LOC between ruby 2.1 & 2.2.
```ruby
arr = ['foo'.to_sym.hash]
GC.start
arr.include?('foo'.to_sym.hash) # Value is true in 2.1 but false in 2.2
```

Ruby 2.2  can be made to return true if we make foo an immortal symbol
```ruby
:foo
arr = ['foo'.to_sym.hash]
GC.start
arr.include?('foo'.to_sym.hash) # Value is true in 2.2 because :foo is immortal
```

