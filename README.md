# learnablegit
Version control is a system that records changes to a file or set of files over time, allowing you to recall specific versions later. It is particularly valuable in collaborative software development, where multiple people may be working on the same codebase simultaneously. Version control helps manage changes, track history, and collaborate efficiently.
Git is the version control system that handles the tracking of changes and collaboration locally, while GitHub is a web-based platform that provides hosting and collaboration tools for Git repositories. Git can be used without GitHub, but GitHub relies on Git for its version control capabilities. Other similar services exist, but GitHub is one of the most popular and widely used platforms.
Three other alternatives to github are : Bitbucket,sourceforge and gitlab
Both git fetch and git pull are Git commands that are used to update your local repository with changes from a remote repository. However, they have different behaviors:

git fetch:
Purpose:

git fetch is used to retrieve the latest changes from the remote repository without automatically merging them into your working branch.
Operation:

It fetches all branches and tags from the remote repository, updating your local references (like origin/master, origin/develop, etc.) but does not modify your working directory or merge any changes.
Usage:

Use git fetch when you want to see what changes are present on the remote without integrating them into your local working copy immediately.
Example:

git pull:
Purpose:

git pull is used to fetch the latest changes from the remote repository and automatically merge them into your current working branch.
Operation:

It combines git fetch and git merge into a single command. It fetches changes from the remote and then merges them into the current local branch.
Usage:

Use git pull when you want to bring the remote changes into your local working copy and automatically merge them.

Key Differences:
Automatic Merge:

git fetch only updates the remote tracking branches without merging, leaving your working directory unchanged. You need to explicitly merge the changes using a separate command.
git pull automatically fetches changes and merges them into your current branch.
Control over Merging:

git fetch provides more control over when and how you merge changes, allowing you to review the changes before merging.
git pull performs the fetch and merge in a single step, which can be convenient but may result in automatic merges that you may want to review first.
In summary, if you want to see what changes exist on the remote without merging them immediately, use git fetch. If you want to fetch and merge changes in one step, use git pull. The choice depends on your workflow and whether you prefer more manual control over the merging process.
In simple terms, git rebase is a Git command used to change the way your commit history looks. It helps in cleaning up and organizing your commits. Instead of merging changes, as with git merge, git rebase integrates changes by moving or combining commits.

Here's a simple explanation:

git rebase essentially takes a series of commits and places them on top of another commit.
Let's say you have a branch with some commits, and in the meantime, someone else made changes in the remote repository. If you want to bring those changes into your branch while keeping your commits on top, you can use git rebase.

Basic git rebase Command:
git pull origin main
git rebase origin/main

This sequence of commands fetches the changes from the remote (git pull origin main) and then reorganizes your commits on top of the changes from the remote branch (git rebase origin/main).

In simple terms:

git pull origin main: Fetch the changes from the remote branch (main in this case) into your local branch.

git rebase origin/main: Rearrange your commits on top of the latest changes from the remote branch. This makes your commit history look cleaner and more linear.

Remember that using git rebase rewrites commit history, so it's generally recommended to avoid it on commits that you've already pushed to a shared repository. Use it mainly for local branches or branches that haven't been shared with others.

In simple terms, git cherry-pick is a Git command that allows you to pick and apply specific commits from one branch and apply them onto another branch. It's like selecting individual changes (commits) and copying them to another branch.

Here's a basic explanation:

git cherry-pick lets you take specific changes from one branch and apply them to another branch, as if you made those changes directly on the target branch.

Basic git cherry-pick Command:
git checkout target_branch
git cherry-pick commit_hash

This sequence of commands checks out the target branch where you want to apply the changes and then cherry-picks a specific commit onto that branch.

In simple terms:

git checkout target_branch: Switch to the branch where you want to apply the changes.

git cherry-pick commit_hash: Apply the changes from the specified commit onto the current branch.

Here, commit_hash is the unique identifier of the commit you want to cherry-pick. You can find the commit hash by looking at the commit history using git log.

Remember that using git cherry-pick copies individual commits, so it's a handy tool when you only need specific changes from one branch to another. Also, be aware that conflicts might occur during the cherry-pick process, and you may need to resolve them manually