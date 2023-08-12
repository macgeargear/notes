[[Cheat Sheet]]
- to archive and restore files, we use `gzip`, `bzip2`, `tar`, `zip/unzip` and `xz/unxz`
- These commands are designed to either merge multiple files into a single file or compress a large file into a smaller one. 

<span class="purple"><u>The task of archiving data is important for several reasons</u></span>
1. Large files may be difficult to transfer. Making these files smaller helps make transfere quicker.
2. Transferring multiple files from one system to another can become tedious when there are many files. Merging them into a single file for transport makes this process easier.
3. Files can quickly take up a lot of space, especially on smaller removeable media like thumb drives. Archiving reduce this problem.

`tar` command is used to merge multiple files into a single file. Bydefault, it does not compress the data.
`-c` options tells the `tar` command to create a `tar` file.
`-v` option stands for <u>"verbose"</u> , which instructs the `tar` command to demostrate what is doing. 
`-f` option is used to specify the name of the `tar` file.

---
 Note : **tar =  **T**ap **AR**chive.**
- To display the contents of a `tar` file by using the avilable options 
	 - `t`  = list the contents
	 - `v` = verbose 
	 - `f` = filename

- Te create `tar` file that is compressed use `-z` option: The `-z` option makes use of the `gzip` utility to perform compression.
- To extract the contents of an archive. Data is restored to the current directory by default. use `tar -xvf tarfile.tar.gz`


