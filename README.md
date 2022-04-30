# git-binignore
add binary executables and shared objects to .gitignore

You can run this script any directories under a git repository. If this script finds binary executables and shared objects under the repository, add these files to ".gitignore" in each directory.

Let assume a git repository which has three so-called "hello world" programs written in C, Go, and Python3.

```conosle
$ find
.
./python
./python/hello.py
./.git
<...snip>
./c
./c/hello
./c/hello.c
./go
./go/hello
./go/hello.go
```

All source files are in this repository.

```console
$ git ls-files
c/hello.c
go/hello.go
python/hello.py
```

However, two binaries are not.

```consle
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        c/hello
        go/hello
...
```

In most cases, we want to ignore them but it's annoying to add them in ".gitignore" one-by-one. We often encounter this situation, especially when writing sample programs written in books and articles. We are freed from this bothersome work by "git-binignore."

```console
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        c/.gitignore
        go/.gitignore
...
$ cat c/.gitignore 
hello
$ cat go/.gitignore 
hello
```

# install

Copy "git-binignore" into anywhere you like (e.g. "/usr/local/bin").

# usage

```console
git-binignore
```

or run this as a git subcommand.

```console
git gitignore
```
..
