# How-to-copy-a-branch-of-one-repository-to-a-branch-of-another-repository
[Written in a hurry.]

Refer: https://stackoverflow.com/a/49095833

1. Create a remote new-repo on github.
1. Import og-repo-1 into this new-repo.
1. Create new branch in new-repo, from the require commit in new-repo-branch-1. Let's call it new-repo-branch-2.
1. Open gitkraken.
1. Checkout to new-repo-branch-2
1. Perform the following command using GUI:
git add remote <og-repo-2-name> <repo-2-ssh-url>

Do not actually write the command. Just add og-repo-2 to the list of 'REMOTE' using GUI.

7. Write the following command on the working directory using Terminal:
git merge --allow-unrelated-histories <repo-2-name>/<repo-2-branchName>

This would give an error.

8. Commit new-repo-branch-2 with a commit message. Right now, merge has NOT taken place.

9. Run the above command again:
git merge --allow-unrelated-histories <og-repo-2-name>/<og-repo-2-branchName>

It'd say that we have merge conflicts.

10. Resolve the conflicts. I did it within GitKraken. Accept the changes from og-repo-2. (For me, these were on the left side.) Do it for all the conflicting files.

11. Commit. THIS commit merges og-repo-2-branch to new-repo-branch-2. Release tags are also merged.

1. Remove og-repo-2 from GitKraken GUI.

1. Push the changes of new-repo-branch-2 to remote.
