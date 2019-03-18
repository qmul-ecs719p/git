# Version Control with Git

**Requirements**: 

- install [git](http://git-scm.com/) 

- sign up an account at [Github](https://github.com/).

In any software development, one of the most important tools is version control software such as Git (`git`) and Mercurial (`hg`). We will look at `git`, although `hg` is just as good and works in almost exactly the same way.

The source code or digital content is stored in a **repository**. The repository does not only contain the latest version of all files, but the complete history of all changes to the files since they were added to the repository.

A user can **checkout** the repository, and obtain a local working copy of the files. All changes are made to the files in the local working directory, where files can be added, removed and updated.

When a task has been completed, the changes to the local files are **commited** (saved to the repository).

If someone else has been making changes to the same files, a **conflict** can occur. In many cases conflicts can be resolved automatically by the system, but in some cases we might manually have to **merge** different changes together.

It is often useful to create a new **branch** in a repository, or a **fork** or **clone** of an entire repository, when we doing larger experimental development. The main branch in a repository is called **master**. When a branch or a fork is completed, it can be merged in to the master branch.

With Git or Mercurial, we can **pull** and **push** changesets between different repositories. For example, between a local copy of there repository to a central online reposistory (for example on a community repository host site like github.com).

We cover the basics in [workflow](./workflow.md). For more information, you could check [official github guides](https://guides.github.com/) or the courses at [Github Learning Lab](https://lab.github.com/courses?tag=Git). 