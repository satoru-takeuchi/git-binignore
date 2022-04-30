# git-binignore
`git-binignore` adds any binary executables and shared objects under a git repository to ".gitignore."

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

All source files have already been registered in this repository.

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

In most cases, we want to ignore them. However, it's annoying to add them to ".gitignore" one-by-one. We often encounter this situation when writing sample programs written in books and articles. We are freed from this bothersome work by "git-binignore."

```console
$ git binignore
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
