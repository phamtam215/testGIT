# testGIT

Take careful note of the user name and email address you register with at GitHub, ideally it will be the same username and email you configure git with locally.
If you only ever used Git locally by yourself then this username and email would just be stored on your local historical logs.
However if you end up working with others and using GitHub, this information will be useful to identify who did what.
You can check the current configuration with the commands:

- git config user.name
- git config user.email
  The configuration commands will be:
- git config --global user.name “user” => user will display on github as distributor (updated 1 minute ago by "username")
- git config --global user.email “email”

# REMOTE

We can check for remote branches with the command:
git remote -v
If you run this command on a cloned repo, you will view the URL of the remote branch, like the GitHub URL.
If there is no connection to a remote branch, then you won’t see a URL.

GitHub has officially changed the naming convention of its master branch to main branch.
You’ll see this reflected in the instructions that GitHub provides:
git branch -M main

---

`Origin` is name of remote repository
Command
git remote -v
Result
origin https://github.com/thachphamblog/hoc-git.git (fetch)
origin https://github.com/thachphamblog/hoc-git.git (push)
=> push to `origin` is pushing to `https://github.com/thachphamblog/hoc-git.git`

Once you are in the correct branch, use the command git push -u origin <branch_name> to push the branch to the remote repository on GitHub. This will create a new branch with the same name on the remote repository and set the upstream to the branch you just pushed. The -u flag stands for --set-upstream which tells Git to set the upstream branch.
Setting the upstream branch when pushing a branch to a remote repository is an important step in Git that allows you to establish a connection between the local branch and its corresponding branch on the remote repository.

When you use the -u or --set-upstream option with the git push command, Git sets the remote branch as the upstream branch for the local branch. This means that Git will remember the relationship between the local branch and the remote branch, and you can use commands like git pull and git push without specifying the remote branch name and Git will know which branch to update.

---

you can add additional remote connections to your local repository using the git remote add command. This allows you to work with multiple remote repositories, such as when you need to collaborate with different teams or contribute to different open-source projects. Each remote connection represents a link between your local repository and a remote repository, and you can interact with each remote separately using Git commands such as git fetch, git pull, and git push.

---

`git pull` and `git fetch` are both Git commands that are used to update your local repository with changes from a remote repository. However, they work in slightly different ways:

- `git fetch:` The git fetch command downloads the latest changes from the remote repository, but `does not integrate` them into your local repository. This means that you can use git fetch to see what changes have been made in the remote repository without affecting your local repository.
  For example, if you run `git fetch origin`, Git will `retrieve the latest changes` from the origin remote `and` `update your local copy of the origin branch`. However, it will not automatically merge these changes into your current branch. To integrate the changes, you will need to use the git merge or git rebase command.

- `git pull:` The git pull command is used to both download and integrate changes from a remote repository into your local repository in a single command. It is essentially a combination of git fetch and git merge. When you run git pull, Git will first download the latest changes from the remote repository using git fetch, and then automatically merge them into your current branch.
  For example, if you run git pull origin master, Git will retrieve the latest changes from the origin remote's master branch and merge them into your local master branch.

It's important to note that` git pull` can sometimes lead to merge `conflicts` if you and `another contributor have both made changes to the same part of the code`. In this case, you will need to `manually resolve the conflicts` before you can commit your changes.

Overall, git fetch is useful for checking for changes in the remote repository without affecting your local repository, while git pull is useful for quickly updating your local repository with the latest changes from the remote repository.

When you run `git fetch,` Git will update your local copy of `all the remote branches`, `not just the branch that you are currently on`. So in your example, if you are on branch A and you run git fetch, Git will update your local copy of branch B with any changes that have been made in the remote repository.

In summary, running git fetch updates your local copy of all remote branches, but you will still need to manually merge the changes into your local branch if you want to incorporate them.

---

git branch -a
![image](https://user-images.githubusercontent.com/85342922/226678085-eca08597-0385-463d-954b-5166bd2a724b.png)
Overall, the `git branch -a` command is useful for seeing a list of all branches in your local repository and their corresponding remote tracking branches. It can help you keep track of which branches are available both locally and in the remote repository.

- \* main: This means that you are currently on the main branch in your local repository.
- origin: This is a reference to the remote repository that your local repository is connected to. It indicates that your local repository has a remote named origin.
- remotes/origin/HEAD -> origin/main: This line indicates the default branch of the remote repository that your local repository is tracking. In this case, it is pointing to the main branch on the origin remote.
- remotes/origin/main: This is a reference to the main branch in the origin remote repository. It indicates that your local repository has a remote tracking branch named origin/main, which tracks the main branch in the origin remote repository.
- remotes/origin/test1: This is a reference to another branch in the origin remote repository named test1. It indicates that your local repository has a remote tracking branch named origin/test1, which tracks the test1 branch in the origin remote repository
