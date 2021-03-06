**What I learned so far:**

Terminal:
    show current directory: pwd

    List files and folders: ls
    List files and folders in a directory: ls [directory]
    List all files and folders, including hidden files and folders: ls -a
    List files and folders in a directory, including hidden files and folders: ls [directory] -a
    List all files and folders, including hidden files and folders, including the size of each file: ls -al
    List all files and folders, including hidden files and folders, including the size of each file, including the owner of each file, including the group of each file, including the last modified time of each file, including the last accessed time of each file, including the creation time of each file: ls -alhGtAC

    Open a file: open [file]
    Open files in VS Code inside a folder: code .
    Open a file in a directory: open [directory] [file]
    Open a folder: open [folder]
    Open a folder in a directory: open [directory] [folder]

    Open current directory: cd
    Open a directory: cd [directory]

    list all directories: dir
    list all directories in a directory: dir [directory]

    list all files: file
    list all files in a directory: file [directory]

    list files and folders in a directory: dir [directory]

    list all files and folders, including hidden files and folders: dir -a

    change directory: cd [directory]

    change directory to the parent directory: cd ..

    change directory to the root directory: cd /

    change directory to the home directory: cd ~

    change directory to the home directory of the current user: cd ~user

    change directory to the home directory of the specified user: cd ~user

    create a directory: mkdir [directory]
    create a directory, with a specified line number: mkdir [directory] [line number]

    create a file: touch [file]
    create a file with a specified size: touch [file] [size]
    create a file with a specified size and a specified owner: touch [file] [size] [owner]
    create a file with a specified size and a specified owner and a specified group: touch [file] [size] [owner] [group]

    Delete a file: rm [file]

    Delete a directory: rmdir [directory]

    Delete a folder: rm -rf [folder]

    Delete a file or a directory: rm -rf [file or directory]

    Delete a file or a directory, with confirmation: rm -rf [file or directory]



Configuring git: 

    Show the username: git config user.name
    Show the email: git config user.email

    username: git config --global user.email "email"
    email: git config --global user.name "full name/username"


Initialize git: git init

Status: git status


Log: git log
    Log with file name: git log --name-only
    Log with line number: git log --numstat
    Log in short format: git log --pretty=oneline
    Log in short format with file name: git log --pretty=oneline --name-only
    Log with file name and line number: git log --name-only --oneline
    Log with file name and line number and commit message: git log --name-only --oneline --pretty=format:"%h %s"
    Log with file name and line number and commit message and author: git log --name-only --oneline --pretty=format:"%h %s %an"
    Log with file name and line number and commit message and author and date: git log --name-only --oneline --pretty=format:"%h %s %an %ad"
    Log with file name and line number and commit message and author and date and time: git log --name-only --oneline --pretty=format:"%h %s %an %ad %at"
    Log with file name and line number and commit message and author and date and time and email: git log --name-only --oneline --pretty=format:"%h %s %an %ad %at %ae"
    Log with file name and line number and commit message and author and date and time and email and committer: git log --name-only --oneline --pretty=format:"%h %s %an %ad %at %ae %cn"
    Log with file name and line number and commit message and author and date and time and email and committer and committer date: git log --name-only --oneline --pretty=format:"%h %s %an %ad %at %ae %cn %cd"
    Log with file name and line number and commit message and author and date and time and email and committer and committer date and committer time: git log --name-only --oneline --pretty=format:"%h %s %an %ad %at %ae %cn %cd %ct"
    Log with file name and line number and commit message and author and date and time and email and committer and committer date and committer time and committer email: git log --name-only --oneline --pretty=format:"%h %s %an %ad %at %ae %cn %cd %ct %ce"
    Log with file name and line number and commit message and author and date and time and email and committer and committer date and committer time and committer email and committer name: git log --name-only --oneline --pretty=format:"%h %s %an %ad %at %ae %cn %cd %ct %ce %cn"


Add gitignore in the root of a repository: git add .gitignore

    Inside the file, add the following:
    .DS_Store # for files
    foldername/ # for folders
    *.log # will ignore all files with the .log extension
    Use gitignore.io for templates: python, windows, mac, linux, vscode, etc https://www.gitignore.io/


Stage and Commit:
    Stage all files: git add .

    Stage a file: git add file.txt file2.txt

    Undo a stage: git reset HEAD file.txt
    

    Commit: git commit -m "Commit message"

    Stage and commit in one step:
        git commit -am "Commit message"
        git commit -a -m "Commit message"

    Amend the last commit(Stage/add the changes and do this): git commit --amend -m "Commit message"


Branches:

    List all branches: git branch

    List remote branches: git branch -r

    Create branch: git branch branch_name

    Switch to branch:
        git switch branch_name
        git checkout branch_name

        When switching to a branch, if the branch does not exist, git will create it.
        Unstaged changes will be lost when using checkout.
        Unstaged changes will come with the new branch, when using switch if there is no conflict.
        
    Switch to remote branch: 
        git switch [branch name]
        git checkout --track origin/[branch name]

    Create branch and switch to it:
        git switch -c branch_name
        git checkout -b branch_name

    Rename branch(have to be in that branch): git branch -m new_branch_name

    Rename any branch: git branch -m branch_name new_branch_name

    Delete a merged branch: git branch -d branch_name

    Delete a local branch: git branch -D branch_name


Merging branches:

    Fast forward merge: 
        First switch to the branch you want to merge: git switch branch_name
        Then merge: git merge branch_name
    
    Resolving conflicts:
        Open up the file(s) with merge conflicts.
        Edit the file(s) to remove the conflicts. Decide which branch's contents you want to keep.
        Or keep the contents of both branches.
        Remove the conflict "markers" in the document.
        Add the file(s) to the staging area: git add .
        Commit the changes: git commit -m "Commit message"
        Usually the commit message will be the same as the one you used for the merge. Or "Resolve conflicts".


    Resolving conflicts in vs code:
        It can be done by opening the file in vs code and choosing the "merge conflicts" option.
        Then, you can choose which branch's contents you want to keep.
        Or keep the contents of both branches.
        Add the file(s) to the staging area: git add .
        Commit the changes: git commit -m "Commit message"
        Usually the commit message will be the same as the one you used for the merge. Or "Resolve conflicts".


Comparing changes with git diff:

    Compare staging area and working directory(Compares unstaged changes and last commit): git diff

    Compare changes in working directory since your last commit (includes staged and unstaged changes): git diff HEAD

    Compare changes within a file (compares unstaged and last commit): git diff file.txt

    Compare changes within a file since your last commit(shows changes in staged and working tree): git diff HEAD file.txt

    Compare changes between last commit and staging area (shows only staged changes):
        git diff --staged file.txt
        git diff --cached file.txt

    
    Compare changes within a file between two commits: git diff commit_id1 commit_id2 file.txt


    Compare changes in staging area since your last commit, excluding untracked files: 
    
        git diff --staged
        git diff --cached

        Compare changes in working directory since your last commit, excluding untracked files and ignored files: git diff --cached --ignore-submodules

        Compare changes in working directory since your last commit, excluding untracked files and ignored files, and show the output in a pager, and show the diff in a pager, and show the diff in a pager with color, and show the diff in a pager with color and word diff: git diff --cached --ignore-submodules --stat --patch-with-stat --color-words --word-diff


    Comparing branches (compares changes from branch_name1 to branch_name2):
        git diff branch_name1 branch_name2
        git diff branch_name1..branch_name2


    Compare two commits :

        [commit] is the commit hash
        Previous commit can be accessed with HEAD^, HEAD^^, HEAD^^^, etc.
        Also:
        HEAD~1 is the previous commit
        HEAD~2 is the previous commit of the previous commit


        Show the changes between two commits: git diff [commit] [commit]

        Compare parent commit with current commit: git diff [commit]^ [commit]

        Compare parent commit with current commit and show the output in a pager: git diff [commit]^ [commit] --stat


        Show the changes between two commits, excluding untracked files: git diff [commit] [commit] --cached

        Show the changes between two commits, excluding untracked files and ignored files, and show the output in a pager, and show the diff in a pager, and show the diff in a pager with color, and show the diff in a pager with color and word diff: git diff [commit] [commit] --cached --ignore-submodules --stat --patch-with-stat --color-words --word-diff



    
        Show the changes between two commits, with a specified file name: git diff [commit] [commit] [file name]
    
        Show the changes between two commits, with a specified file name and line number, with a specified number of lines, with a specified number of characters, with a specified number of words, with a specified number of bytes, with a specified number of lines of context, with a specified number of characters of context: git diff [commit


Stashing:
    Stash changes:
        git stash
        git stash save
            
        Stash changes and keep working directory clean: 
            git stash --keep-index
            git stash --keep-index save

        Stash changes with a message: 
            git stash -m "Stash message"
            git stash -m "Stash message" save
        
        git stash save "Stash message"
        git stash save --keep-index
        git stash save --keep-index "Stash message"

    Show the stashed changes:
        git stash list
        git stash show

        Show the stashed changes in a pager: git stash show --patch

        Show the stashed changes in a pager with color: git stash show --patch --color-words

        Show the stashed changes in a pager with color and word diff: git stash show --patch --color-words --word-diff

        Show the stashed changes in a pager with stat: git stash show --patch --stat

    Apply the stashed changes:
        (Leaves it in the stash list for possible later reuse (or you can then 'git stash drop' it))
        git stash apply
        
        Apply a specific stash:
            git stash apply stash@{0}
            git stash apply stash@{1}

        Apply the stashed changes and keep working directory clean: git stash apply --keep-index

        Apply the stashed changes and keep working directory clean, with a specified index file: git stash apply --keep-index --index-file=.git/stash

    Apply the stashed changes, and remove the stashed changes:
        (Throws away the (topmost, by default) stash after applying it)
        git stash pop

        Apply a specific stash, and remove the stashed changes:
            git stash pop [stash id]
            git stash pop stash@{0}
            git stash pop stash@{1}

    Remove/delete the stashed changes:
        git stash drop

        Remove/delete a specific stash:
            git stash drop [stash id]
            git stash drop stash@{0}
            git stash drop stash@{1}


Check changes:

    Checkout a commit:
        git checkout [commit]
        
        Checkout a commit, with a specified file name: git checkout [commit] [file name]
        
        Checkout a commit, with a specified file name and line number, with a specified number of lines, with a specified number of characters: git checkout [commit] [file name] [line number] [number of lines] [number of characters]

    Switch back from detached HEAD state to master/branch:
        git switch master
        git switch master -- [file name]

        git switch [branch_name]

        Go back to the head of the branch you're on:
            git switch -

    Checkout previous commits:
        (HEAD~1 points to the last commit before where HEAD points at)
        git checkout HEAD~1
        git checkout HEAD~2
        git checkout HEAD~3


    Checkout origin/main: git checkout origin/main

Undo Changes: 

    Undo unstaged local changes:
        Confirm that the file is unstaged: 
            git status
            git diff --cached
            git diff HEAD

        To overwrite local changes after the last commit:: 
            git checkout -- [file name] 
            git checkout HEAD [file name]

        Restores using HEAD as the default source: git restore [file name]
        Restores using HEAD~1 as the default source: 
            git restore --source HEAD~1 [file name]
            (This will restores the contents of the file to the state of HEAD~1)

            git restore --source [commit hash] [file name]

        
        To save local changes so that they can be restored later: 
            git stash
            git stash save
        
        To discard local changes to all files permanently after last commit: git reset --hard

        To discard local changes to a specific file permanently after last commit: git reset --hard [file name]

        Undo changes after particular commit:
        
            Removes all the commits and discard all changes after the specified commit:
                git reset --hard [commit]

            Removes all the commits after the specified commit, changes are shown as modified in the working directory:
                git reset [commit]

            Go back to a previous commit(Changes since that commit changes are shown as modified in the working directory):
                git reset [commit]
                
                Go back to a previous commit, with a specified file name: git reset [commit] [file name]
                
                Go back to a previous commit, with a specified file name and line number, with a specified number of lines, with a specified number of characters: git reset [commit] [file name] [line number] [number of lines] [number of characters]    

            Using revert, revert creates a new commit with the changes from the specified commit, and the new commit is made the new HEAD:
                git revert [commit]


    Undo staged changes:
        Confirm that the file is staged: 
            git status
            git diff

        To unstage the file but keep your changes: git restore --staged [file name]

        To unstage everything but keep your changes: git reset

        To unstage the file to current commit HEAD: git reset HEAD [file name]

        To discard all local changes but save them for later: git stash

        To discard everything permanently: git reset --hard


Cloning: 
    git clone [repository]
    git clone [repository URL] [directory name]


Setting up SSH Keys:
    Open terminal(bash)
    Enter the following command to see if existing SSH keys are set up:
        ls -al ~/.ssh

    If not Generate a new key by following the instructions from this link:
        https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent


Connect local repo to remote repo:
    * Create a new repo on Github.
    * Connect your local repo (add a remote)
    * Push up your changes to Github


    View existing remotes for your repository:
        gir remote
        git remote -v
        (-v verbose, shows the URL of the remote)

    Add a remote: git remote add [name] [remote URL]
        git remote add origin [remote URL]
    
    Rename a remote: git remote rename [old name] [new name]
        git remote rename origin origin_new
    
    Remove a remote: git remote remove [name]
        git remote remove origin

    Rename master branch to main:
        git branch -M main
        (-M: shortcut for --move --force)

        git branch -m master master_new
        (-m: shortcut for --move)
    
    Push up your changes to Github: git push <remote> <branch>
        git push origin main
        git push origin master --force
        (-f: force push)

    Push a branch up to Github: git push <remote> <branch>
        git push origin main
        git push origin master --force
        (-f: force push)p-  1

        git push -u origin master
        (-u: update remote)

        Push only th specified file: git push -u origin master -- [file name]
        (-u: update remote)

        git push origin master --force: 
            (-f: force push)

        git push origin master --tags: 
            (-t: push tags)


        git push origin master --delete: 
            (-d: delete remote branch)

<remote>/<branch>: origin/main refers to the state of main branch on the remote repo named origin.
upstream/<branch>: upstream/main refers to the state of main branch on the upstream repo named upstream.
(upstream is a common remote name)


Fetching: 
    View existing remotes for your repository: git remote -v

    Fetch the latest changes from the remote repo: git fetch [remote]
    (This will fetch the latest changes from the remote repo, and merge them with your local repo)

    Fetch the latest changes from the remote repo on a branch: git fetch [remote] <branch>


    git fetch [remote] <branch> --tags: 
        (-t: fetch tags)

    git fetch --all: 
        (-a: fetch all remotes)
        
    git fetch --tags: 
        (-t: fetch tags)

    git fetch --prune: 
        (-p: prune remote branches)

    git fetch --prune --all --tags --prune-tags --prune-unreachable: 
        (-u: prune unreachable branches)
    
    git fetch --prune --all --tags --prune-tags --prune-unreachable --prune-refs --prune-shallow --prune-refs-with-glob=refs/remotes/*/* --prune-shallow-exclude=refs/remotes/origin/


Pulling: 
    git pull [remote] [branch]
    (This will pull the latest changes from the remote repo, and merge them with your local repo)
    (Pulls can result into merge conflicts)

    git pull origin/main: 
        (This will pull the latest changes from the remote repo, and merge them with your local repo)
        (Pulls can result into merge conflicts)

    git pull:
        If we run git pull without any arguments, it assumes that remote will default to origin and branch will default to whatever tracking connection is configured for your current branch.
        Note: This behavior can be configured, and tracking connections can be changed manually. Most people do not mess with that stuff.

    git pull [remote] [branch] --tags: 
        (-t: pull tags)

    git pull --all: 
        (-a: pull all remotes)
        
    git pull --tags: 
        (-t: pull tags)

    git pull --prune: 
        (-p: prune remote branches)

    git pull --prune --all --tags --prune-tags --prune-unreachable: 
        (-u: prune unreachable branches)
    
    git pull --prune --all --tags --prune-tags --prune-unreachable --prune-refs --prune-shallow --prune-refs-with-glob=refs/remotes/*/* --prune-shallow-exclude=refs/remotes/origin/



Rebase: 
Why rebase?: We get a much cleaner Project history. No unnecessary merge conflicts(like Resolve merge conflicts on feature branches). We end up with a linear project history.
We can also rewrite, delete, rename or even reorder commits (before sharing them) with interactive rebase.

Warning: Never rebase commits that have been shared with others. If you have already pushed commits up to Github, do not rebase them unless you're positive no one on the team is using these commits.

We can also wait until we are done with a feature and then rebase the feature branch on the master branch.

    Merging using rebase:
        (First switch to the branch you want to merge with: 
            git switch [branch name]
            git switch feature)

        git rebase [branch name]
        git rebase main
        (This will merge the branch with the current branch)
        (Merging can result in conflicts)
        When there's conflicts, resolve them, add and then "run git rebase --continue" to continue the rebase.
        To abort rebase when there's conflicts, run "git rebase --abort".

    Editing comments with interactive rebase:
        Running git rebase -i HEAD~4
        (HEAD~4 is the how far back you want to go)
        This will open up the interactive rebase editor. Here we'll see a list of commits alongside a list of commands that we can choose from. Here are a couple of the more commonly used commands:
            - pick: use the commit
            - reword: use the commit, but edit the commit message
            - edit: use the commit, but stop for amending
            - fixup: use commit contents but meld it into previous commit and discard the commit message
            - drop: remove commit

    git rebase [remote] [branch]
    (This will rebase your current branch on top of the specified branch)

    git rebase [remote] [branch] --onto [new branch name]
    (This will rebase your current branch on top of the specified branch, and create a new branch named [new branch name])

    git rebase --continue: 
        (This will continue the rebase)

    git rebase --skip: 
        (This will skip the current commit)

    git rebase --abort: 
        (This will abort the rebase)

    git rebase --edit-todo: 
        (This will edit the todo file)

    git rebase --show-current-patch: 
        (This will show the current patch)

    git rebase --show-current-patch --stat: 
        (This will show the current patch and the diffstat)

    git rebase --show-current-patch --stat --summary: 
        (This will show the current patch, the diffstat, and the summary)

    git rebase --show-current-patch --stat --summary --graph: 
        (This will show the current patch, the diffstat, the summary, and the graph)

    git rebase --show-current-patch --stat --summary --graph --color --no-color --no-graph --no-stat: 
        (This will show the current patch, the diffstat, the summary, the graph, the color, the no-color, the no-graph, and the no-stat)