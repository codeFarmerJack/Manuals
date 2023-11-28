1. How to check out a specific commit in Git?
   You can either use the 'git checkout' or 'git switch' command.
    (1) Using 'git checkout':
        'git checkout <commit_hash>'
        Replace '<commit_hash>' with the actual commit hash you want to checkout. This will put your repository in a "detached HEAD" state, meaning you're not on any branch
    (2) Using 'git switch' (Git version 2.23 and later)
        'git switch <commit_hash>'
        This is similar to 'git checkout' but with a more straightforward syntax. Again, replace '<commit_hash>' with the actual commit hash.
    (3) Creating a New Branch from a Specific Commit:
        If you want to work on the commit without being in a detached HEAD state, you can create a new branch from the commit:
        'git checkout -b new_branch_name <commit_hash>'
        or 
        'git switch -c new_branch_name <commit_hash>'
        Replace 'new_branch_name' with the name you want for your new branch and '<commit_hash>' with the actual commit hash.
    (4) Returning to the Previous Branch
        After you've finished working with the specific commit, you might want to return to your previous branch. You can do this using:
        'git checkout -'
        This will switch back to the branch you were on before checking out the specific commit.
    Note:
        If you want to explore the commit history and don't need to make changes, you can also use 'git log' to view the commit hisotry and find the commit hash:
        'git log'
        Find the commit hash of the specific commit you're interested in and then use one of the above commands to check it out.

        Remember that if you make changes in a detached HEAD state, those changes won't be associated with any branch. Creating a new branch is a good practice if you plan to make modifications.

2. How to switch to a different branch in Git?
    You can use the 'git checkout' or 'git switch' command. Here's how you can do it:
    (1) Using 'git checkout':
        'git checkout branch_name'
        Replace 'branch_name' with the name of the branch you want to switch to.
    (2) Using 'git switch':
        'git switch branch_name'
        Again, replacee 'branch_name' with the name of the branch you want to switch to.
    (3) Creating a New Branch and Switching to It:
        If the branch you want to switch to doesn't exist, you can create a new branch and switch to it one step:
        'git checkout -b new_branch_name'
        or 
        'git switch -c new_branch_name'
        Replace 'new_branch-name' with the name you want for your new branch.
    Note: 
    If you have changes in your working directory that haven't been commited, Git may prevent you from switching branches to avoid conflicts. You can either commit your changes or stash them before switching branches.
    If you want to switch back to the branch you were on before switching to another branch, you can use the 'git switch -' or 'git checkout -' command.

3.  When you're trying to switch to a specific commit without creating a branch, an error happens. If you want to work with that specific commit, you can follow the suggestions in the hint and use the '--detach' option. Here's how:
    'git checkout --detach <commit_hash>'
    or with 'git switch':
    'git switch --detach <commit_hash>'
    Replace '<commit_hash>' with the actual commit hash you want to work with.

    Using '--detach' puts your repository in a "detached HEAD" state, meaning you're not on any branch. Any changes you make in this state won't be associated with a branch, so it's a good practice to create a new branch if you plan to make modifications:
    'git checkout -b new_branch_name <commit_hash>'
    or with 'git switch':
    'git switch -c new_branch_name <commit_hash>'
    Replace 'new_branch_name' with the name you want for your new branch and '<commit_has>' with the actual commit hash.

    After creating the branch, you can switch to it and continue your work:
    'git checkout new_branch_name'
    or with 'git switch':
    git switch new_branch_name'
    This approach allows you to work with the specific commit within the context of a new branch.

4. How to delete a branch in Git?
    You can use the 'git branch' command. Here are the steps:
    (1) Deleting a Local Branch:
        'git branch -d branch_name'
        Replace 'branch_name' with the name of the branch you want to delete. If the branch has unmerged changes (commits that haven't been merged into another branch), Git will prevent you from deleting it with '-d'. To force deletion, you can use '-D':
        'git branch -D branch_name'
    (2) Deleting a Remote Branch:
        Deleting a remote branch involves pushing an empty reference to the remote repository. Here's one way to do it:
        'git push origin --delete branch_name'
        Replace 'branch_name' with the name of the remote branch you want to delete.
    Note:
        Be cautious when deleting branches, especially if they contain unmerged changes. Once a branch is deleted, the changes associated with it may be difficult to recover.
        Deleting a branch only removes the branch reference; it doesn't delete the commits. Commits are retained in the Git history, even if the branch is deleted.
        Ensure that you're not on the branch you are trying to delete. If you are, switch to a different branch using 'git checkout' or 'git switch'.

5. How to check the branch I'm currently working on in Git?
    You can use the following command:
    'git branch'
    The branch you are working on will be highlighted with an asterisk (*). 

6. How to push to a specific branch in Git?
    You can use the following command:
    'git push origin branch_name'
    Replace "branch_name" with the name of the branch you want to push to. This assumes that you have already committed your changes to the branch.
    (1) If the branch doesn't exist on the remote repository yet, you might need to create the branch on the remote repository. You can do this by adding the '-u' option to set up trakcing:
    'git push -u origin branch_name'
    This estabishes a tracking relationship between your local branch and the remote branch. After the initial setup, you can simply use 'git push' to push changes to the tracked remote branch.

    (2) If you are working in a branch and want to push changes to the remote repository with the same name, you can use a shrotcut:
    'git push origin HEAD'
    This pushes the changes from your current local branch (HEAD) to the remote branch with the same name.

7. 'git push origin HEAD' Failed. fatal: 'origin' does not appear to be a git repository. 
    The error indicates that Git is unable to find a remote repository named 'origin.' This typically means taht the remote repository is not configured for your Git repository. To resolve this, you need to set up a remote repository and associate it with the name 'origin'.
    Here are the steps to set up a remote repository:
    (1) Check Existing Remotes:
        First, check if you have any existing remotes configured for your repository:
        'git remote -v'
        This will list the names and URLs of the remotes associated with your repository.
    (2) Add 'origin' Remote:
        If 'origin' is not listed, or if you need to update the remote URL, you can add it using the following command:
        'git remote add origin <repository_url>'
        Replace '<repository_url>' with the actual URL of your remote repository. For example, if you are using HTTPS:
        'git remote add origin https://github.com/username/repo.git'
        Or if you are using SSH:
        'git remote add origin git@github.com:username/repo.git'
    (3) Verify Remote Configuration:
        After adding the remote: you can verify the remote configuration:
        'git remote -v'
        Ensure that 'origin' is listed with the correct URL.
    (4) Push to 'origin'
        Now, you can push your changes to the 'origin' remote:
        'git push origin HEAD'
        This command pushes the changes in your current branch to the remote branch with the same name.

8. Meaning of 'origin'
    In Git, "origin" is the default name given to the remote repository from which your local reopsitory was cloned. It's a conventionally used alias for the URL of the remote repository.
    Here's a breakdown of the term:
    * Remote Repository: A remote repository is a version of your project hoseted on a server or another location. This allows multiple developers to work on the same project. The remote repository is usually hosted on platforms like GitHub, GitLab, Bitbucket, or a private server.
    * Origin: "Origin" is just a conventionally used name for the default remote repository. When you clone a repository, Git automatically sets up a remote named "origin" that points to the repository from which you cloned.

    When you run commands like 'git pull' or 'git push origin', you are interacting with the remote repository named "origin". For example:
    * 'git pull origin master': Pulls changes from the remote repository's master branch into your local repository.
    * 'git push origin branch_name': Pushes changes from your local branch to the remote repository's branch with the specified name.

    You can view the list of remotes for your repository using the command:
    'git remote -v' 
    This will show the names and URLs of all the remotes associated with your local repository.

9. '**HEAD**' Introduction 
    In Git, '**HEAD**' is a symbolic reference that poitns to the last commit in the branch you are currently working on. It represents the tip of the current branch and serves as a convenient way to refer to the most recent commit in your working directory.
    Here are some key points about 'HEAD'"
    (1) Current Commit: 'HEAD' points to the commit that your working directory reflects. If you make a new commit, 'HEAD' will be updated to point to that new commit.
    (2) Branch Pointer: 'HEAD' is indirectly associated with the branch you are currently on. It usually points to the branch itself, and the branch, in turn, points to the latest commit in that branch.
    (3) Detached HEAD: In Git, you can also have a "detached HEAD" state. This occurs when 'HEAD' directly points to a specific commit instead of a branch. In this state, any new commits you make won't be associated with a branch, and you might lose them if you switch branches.

    Here are some common uses of 'HEAD'
    * View Current Commit:              'git log -n 1 HEAD'
    * Switch Branches:                  'git checkout branch_name'
    * Create a New Branch from HEAD:    'git checkout -b new_branch_name'
    * Detach HEAD (for viewing specific commit):    'git checkout commit_hash'
    * Push Changes to Remote Branch:    'git push origin HEAD'
        This pushes changes from the local branch (pointed by 'HEAD') to the remote branch.

    In summary, 'HEAD' is a dynamic pointer that always points to the latest commit in the branch you are currently working on. Understanding 'HEAD' is crucial for navigating through your Git history and managing branches.

10. Switch between SSH and HTTP(S） protocols
    To switch between SSH and HTTP(S) protocols when cloning a Git repository, you need to update teh repository URL. Git supports both SSH and HTTP(S) as transport protocols, and you can switch between them based on your preference or the available access method.
    (1) Switching from HTTPS to SSH:
       If you initially cloned the repository using HTTPS and want to switch to SSH, you can update the remote URL using the following steps:
       (i) View the current remote URL:
            'git remote -v'
       (ii) Change the remote URL from HTTPS to SSH:
			'git remote set-url origin git@github.com:user/repo.git'
			Replace 'git@github.com:user/repo.git' with the SSH URL of your repository.
	(2) Switching from SSH to HTTPS:
		If you initially cloned the repository using SSH and want to switch to HTTPS, you can update the remote URL with the following steps:
		(i)	View the current remote URL:
    		'git remote -v'
    	(ii) Change the remote URL from SSH to HTTPS
    		'git remote set-url origin https://github.com/user/repo.git'
    		Replace 'https://github.com/user/repo.git' with the HTTPS URL of your repository

	After making these changes, future Git operations like '**git pull**' or '**git push**' will use the specified protocol.
	Remember to replace '**origin**' with the actual name of your remote if you have a different remote name.

11. Git stash explanation:
    The '**git stash**' command is used in Git to temporarily save changes that you have not committed, allowing you to switch branches or perform other operations without committing your work. The stashed change can later be reapplied to your working directory.
    **Stash Local Changes**:
    'git stash'
    **Stash with a Message**:
    You can include a message to describe the changes being stashed.
    'git stash save "Your stash message here"'
    **List Stashes**:
    To see a list of stashes:
    'git stash list'
    **Apply the Most Recent Stash**:
    To apply the most recent stash and remove it from the stash list:
    'git stash apply'
    **Apply a Specific Stash**
    If you have multiple stashes and want to apply a specific one (replace 'stash@{n}' with the stash reference you want):
    'git stash apply stash@{n}'
    **Apply and Drop the Stash**:
    To apply the most recent stash and remove it from the stash list:
    'git stash pop'
    **Drop a Specific Stash**:
    To remove a specific stash without applying its changes:
    'git stash drop stash@{n}'
    **Clear All Stashes**:
    To remove all stashes:
    'git stash clear'
    Using '**git stash**' is particularly useful when you need to switch branches or perform other operations that might conflict with your current changes. Stashing allows you to save your changes temporarily and reapply them later.
