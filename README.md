# Git Lab 2

## Generate SSH Key and Connect it to our Github Account
![IMG-20231127-WA0009](https://github.com/Nada-Khater/gitlab2/assets/75952748/e8e97f15-e60a-4ded-b0f0-c02c14f2845b)
![2](https://github.com/Nada-Khater/gitlab2/assets/75952748/32fd4474-a50a-44b0-a994-8d0264076c37)
![IMG-20231127-WA0011](https://github.com/Nada-Khater/gitlab2/assets/75952748/a7873b3d-6f7e-403f-8647-d5cc8a6bfceb)

## Creating 2 branches **dev** and **test** and adding 2 files to dev and 1 file to test
```
git checkout -b dev
echo "dev1" >> devfile1.txt
echo "dev2" >> devfile2.txt
git checkout -b test
echo "test" >> testfile.txt
git push origin dev
git push origin test
```

```
git checkout main
git merge dev
git merge test
git push origin main
```

## After merging 2 branches on main
![IMG-20231127-WA0012](https://github.com/Nada-Khater/gitlab2/assets/75952748/50de4ce3-d18d-49d5-ad11-37df8283911d)

## Remove branches locally and remotly.
- Locally:
```
git branch -d test
```
- Remotely:
```
git push origin :dev
```

## Create an annoted tag with tagname v1.4.
```
git tag -a v1.4 -m "version 1.4"
```

## Push tag to remote server.
```
git push --tags
```

## List tags locally
```
git tags
```

## Delete tag locally and remotely.
- Locally:
```
git tag -d v1.4 
```
- Remotely:
```
git push origin --delete v1.4
git push origin :refs/tags/v1.4
```

## What is git rebase? Give me an example.
Git rebase is a command in Git that allows you to integrate changes from one branch into another by taking all the changes that were committed on one branch and replaying them on a different branch. This is done by taking the patch of the change that was introduced in the source branch and reapplying it on top of the destination branch.

Rebasing is useful when you want to maintain a linear project history, avoid merge conflicts, and keep your commits organized and easy to understand.
Here's a simple example of how git rebase works:

Let's say you have a feature branch and there have been some changes in the master branch that you want to incorporate into your feature branch.

1- Starting with the following commit history:
```
      A---B---C  (master)
           \
            D---E---F  (feature)
```
- You realize that changes in the master branch are essential for your feature. You switch to the feature branch and rebase:
```
git checkout feature
git rebase master
```

- If there are no conflicts, Git will smoothly apply the changes from master onto your feature branch. If conflicts occur, you'll need to resolve them as prompted by Git.

2- After resolving conflicts, continue the rebase:
```
git rebase --continue
```

- Once the rebase is complete, the commit history will look like this:
```
      A---B---C  (master)
               \
                D'---E'---F'  (feature)
```
Now, your feature branch includes the latest changes from master. This can make your branch more up-to-date and reduce the likelihood of conflicts when you eventually merge your changes back into the master branch.

Remember, use git rebase judiciously, especially on branches that you've already shared with others, as it modifies the commit history. Rebasing is often more suitable for local branches or private branches where you have more control over the commit history.

## Day1 Report:
## What is the Pull Request?
A pull request (PR) is a method of submitting contributions to an open-source project or making changes to a codebase that uses a version control system, such as Git. It is a way for developers to propose changes to a repository and request that someone review and merge those changes into the main codebase.

Here's a general workflow for a pull request:
- **Fork the Repository:** If you want to contribute to a project, you typically start by forking the repository. This creates a copy of the repository under your GitHub account.
- **Create a Branch:** Once you have your fork, you create a new branch. This branch is where you make your changes without affecting the main codebase.
- **Make Changes:** Make the necessary changes to the code, add new features, fix bugs, etc., within your branch.
- **Commit Changes:** As you make changes, you commit them to your branch. A commit is a snapshot of your changes at a particular point in time.
- **Push Changes to Your Fork:** After committing your changes, you push the changes to your fork on GitHub.
- **Open a Pull Request:** On GitHub, you can open a pull request to the original repository. This is a request to merge your changes from your branch into the main branch of the original repository.
- **Describe Changes:** In the pull request, you provide information about the changes you made, why you made them, and any other relevant details.
- **Code Review:** Other contributors or maintainers of the project can review your changes. They may provide feedback, ask for clarification, or suggest improvements.
- **Address Feedback:** If there are changes requested during the review, you make the necessary adjustments in your branch.
- **Merge:** Once the changes are reviewed and approved, a project maintainer can merge your changes into the main branch of the repository.

Pull requests are commonly used in collaborative development environments, and they facilitate a controlled and organized way of integrating code contributions from multiple developers. They provide transparency, allow for discussion about the proposed changes, and help maintain the quality and stability of the codebase.
