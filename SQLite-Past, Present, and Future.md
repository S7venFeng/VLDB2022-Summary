



1. SQLite was initially released in Aug.2020 as a small library. SQLite is embedded in other process, not started alone as a process. SQLite popular over the world, can be found in every IOS and Android device. It has 3 core advantages: 
   + **Cross-Platform.** SQLite can be run on any platform with an 8-bit byte, 32-bit and 64-bit integers, and a C-compiler. 
   + **Compact and self-contained.** A single C file, has 150 thousand lines source code and only 750KB after compiled. Same as DuckDB, no external dependencies, don't need install or config.
   + **Reliable.** Over 600 lines of test code for every line of code. Tests over 100% of branches

2. Designers. 
   + SQL Compiler. SQLite's tokenizer, parser and code generator act like a compiler, translating SQL into bytecode(has several virtual functions)
   + VDBE(Virtual database engine). heart of the SQLite. Execute the instructions in bytecode program one by one
   + Backend-Modules. B-tree Module. Page cache.
3.  Optimzation
   + LIP(Lookahead Information Passing). Using bloomfiter early in the join pipeline reduces the number of tuples flow through the join pipeline. 4.2X faster in SSB

