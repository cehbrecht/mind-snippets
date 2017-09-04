# GitSnippet
Created Monday 08 June 2015

##### Hello Git
	$ cd hello-git
	$ git init
	$ ls -al


##### git status
	$ vim readme.md
	$ git status
	$ git status -s # short


##### git add
	$ git add readme.md
	$ git status -s
	$ vim readme.md
	$ git status -s
	$ git status


##### git commit
	$ git commit
	$ git status
	$ git commit -a  # add and commit
	
##### enable color
``$ git config --global color.ui auto``

##### git log
	$ git log
	$ git log --oneline
	$ git log -p
	$ git log --graph


##### define git log alias
<https://gist.github.com/ralfebert/515937>

	$ git config --global alias.lg "log --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr %an)%Creset' --abbrev-commit --date=relative"
	$ git lg


##### gitignore  ... ignore files

	$ cat .gitignore
	*~


##### revert unstaged changes
	$ vim readme.md
	$ git status -s
	$ git checkout readme.txt


##### revert staged changes
	$ vim readme.md
	$ git add readme.md
	$ git status
	$ git reset HEAD readme.md
	$ git checkout readme.md


##### revert commited changes
	$ vim readme.md
	$ git commit -a
	$ git log
	$ git revert 832... # commit id
	$ git log


##### git branch
	$ git branch
	$ git branch -v
	$ git branch newfeature
	$ git checkout newfeature
	$ git branch -v


##### git merge
	$ vim changes.md
	$ git commit -a
	$ git branch -v
	$ git checkout master
	$ git merge newfeature
	$ git branch -v


##### git merge ... conflict
	$ vim readme.md
	$ git commit -a
	$ git branch -v
	$ git checkout newfeature
	$ vim readme.md
	$ git commit -a
	$ git merge master # confilct
	$ vim readme.md # resolve manually
	$ git add readme.md
	$ git commit -a
	$ git checkout master
	$ git merge newfeature


##### git merge ... keep ours or theirs
	$ git merge
	$ git checkout --ours # or --theirs
	$ git status
	$ git commit -a


##### git stash ... move local changes to stash

	$ touch isnix
	$ git add isnix
	$ git stash
	$ git stash list
	$ git stash pop


##### git tag  ... tag specific commit

	$ git tag v0.1
	$ git tag


##### git new repo... remotes

	$ git remote -v
	# create new bare repo
	$ cd  ~/sandbox 
	$ git init --bare central-repo
	$ cd -    # back to my hello-git repo
	$ git remote add origin ~/sandbox/central-repo
	$ git remote -v
	$ git checkout master
	$ git push origin master


##### git push/pull  ... update changes with remotes

	$ cd ~/sandbox
	$ git clone central-repo my-hello-git
	$ cd my-hello-git
	$ git remote -v
	$ vim readme.txt
	$ git commit -a
	$ git push
	
	$ cd ../hello-git
	$ git checkout master
	$ git pull


##### git cherrypic ... pick only specific commit

	$ git checkout newfeature
	$ vim readme.txt
	$ vim newfile.txt
	$ git add .
	$ git commit
	$ git push
	$ git lg
	
	$ git checkout master
	$ git cherry-pick fbba208
	$ git lg


##### git rebase ... keep your history clean

<http://git-scm.com/book/en/v2/Git-Branching-Rebasing>

   	# apply your local changes on top of remote branch changes
	# clean up local history
	# "... never rebase anything you’ve pushed somewhere."

	$ git checkout master
	$ git branch experiment
	$ git checkout experiment
	$ vim readme.txt
	$ git commit -a
	
	$ git checkout master
	$ vim changes.txt
	$ git commit -a
	
	$ git checkout experiment
	$ git rebase master


##### git workflow ... distributed
<http://git-scm.com/book/en/v2/Distributed-Git-Distributed-Workflows>

##### github
<http://git-scm.com/book/en/v2/GitHub-Contributing-to-a-Project>

##### using branches
<http://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows>

##### git repo internals

<http://git-scm.com/book/en/v2/Git-Internals-Plumbing-and-Porcelain>
<http://git-scm.com/book/en/v2/Git-Internals-Git-References>

objectstore, blob, tree, commit, gc, packed

	$ git cat-file -p master^{tree}
	$ git cat-file -p d60809eab92d7c7adb6bee023e4857c24df5a1dd
	$ git log   # choose commit
	$ git cat-file -p 27ba98c


##### git alternatives (distributed)

* mercurial: <https://mercurial.selenic.com/>
* bzr: <http://bazaar.canonical.com/en/>


##### binary files

* mercurial largefiles: <https://mercurial.selenic.com/wiki/LargefilesExtension>
* git annex: <http://git-annex.branchable.com/>
* git annex assistant: <http://git-annex.branchable.com/assistant/>


##### git links

* <http://git-scm.com/>
* <http://sixrevisions.com/resources/git-tutorials-beginners/>
* <https://gist.github.com/ralfebert/515937>































