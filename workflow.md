# Basic Workflow

### 1. Creat a repository

To create a brand new empty repository, we can use the command `git init`, let's say we name the repository as `gitdemo`:

```
$ git init gitdemo
```

Now let's navigate to `gitdemo` by `cd gitdemo`. Using the command `git status`, we get a summary of the current status of the working directory. It shows if we have modified, added or removed files.


### 2. Add files

To add a new file to the repository, we first create the file and then use the `git add` command.

There are a couple of ways to write the sentence "A file with information about the gitdemo repository." into a file named `README.md`.

- in terminal, run the command `nano README.md`, then type the sentence, and use `CTRL`+`O` to write out, finally use `CTRL`+`X` to exit;

- or run the command `echo "A file with information about the gitdemo repository." > README.md` to print the sentence into the file.

Now we add the file by:

```
$ git add README.md
```

If we check `git status` now, the file is listed as a new file that has not yet been commited to the repository. 

### 3. Commit 

The initial commit is done by:

```
$ git commit README.md -m "Added a README file"
```

Let's modify `README.md` by adding a new line, then commit it again:

```
$ git commit README.md -m "added one more line in README"
```

`-m` can indicate what changes you have made for this commit. 


### 4. Remove files

To remove file that has been added to the repository, use `git rm filename`, which works similar to `git add filename`.

Let's create a new file by `touch tempfile.txt` then add and commit it:

```
$ git add tmpfile.txt
$ git commit tmpfile.txt -m "adding file tmpfile"
```

Now the file can be removed from the repository by:

```
$ git rm tmpfile
```

Removing a file is committed by:

```
$ git commit tmpfile.txt -m "remove file tmpfile" 
```

### 5. Commit Logs

The messages that are added to the commit command are supposed to give a short (often one-line) description of the changes/additions/deletions in the commit. If the `-m "message"` is omitted when invoking the git commit message an editor will be opened for you to type a commit message (for example useful when a longer commit message is requried).

We can look at the revision log by using the command `git log` and it should return somthing like:

```
    commit b810ca89e9896166310ba3ad2d29bd46b9f9e9ff
    Author: beiciliang <liangbeici@gmail.com>
    Date:   Tue Mar 13 00:30:58 2018 +0000
    
        remove file tmpfile
    
    commit 6608496f16fbcc9f90a1953bc70df1382b120fb4
    Author: beiciliang <liangbeici@gmail.com>
    Date:   Tue Mar 13 00:30:32 2018 +0000
    
        adding file tmpfile
    
    commit e85e7917bdd47e73e1c5288484c4b6288b39d692
    Author: beiciliang <liangbeici@gmail.com>
    Date:   Tue Mar 13 00:28:34 2018 +0000
    
        added one more line in README
    
    commit 42fafb866758b1924224aa95dafd667dc848eb1a
    Author: beiciliang <liangbeici@gmail.com>
    Date:   Tue Mar 13 00:23:10 2018 +0000
    
        Added a README file
```

### 6. Diffs

All commits results in a changeset, which has a "diff" describing the changes to the file associated with it. We can use `git diff` so see what has changed in a file.

### 7. Pull and Push

If the respository has been cloned from another repository, for example on github.com, it automatically remembers the address of the parant repository (called origin). We can show the origin by:

```
$ git remote show origin
```

Here we didn't specify the remote repository before, so it could not be read. 

Now let's creat a new repository called `gitdemo` at Github as our remote repository.

Github is a git repository hosting site that is very popular with both open source projects. With a hosted repository it easy to collaborate with colleagues on the same code base, and you get a graphical user interface where you can browse the code and look at commit logs, track issues etc.

Now add the URL for the remote repository where the local repository will be pushed

```
$ git remote add origin https://github.com/YOUR-GITHUB-USERNAME/gitdemo.git
```

To push our existing local repository to the remote repository:

```
$ git push -u origin master
```

We can retrieve updates from the origin repository by "pulling" changesets from "origin" to our repository:

```
$ git pull origin
```

We can register addresses to many different repositories, and pull in different changesets from different sources, but the default source is the origin from where the repository was first cloned (and the word `origin` could have been omitted from the command line above).
