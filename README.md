Random tips, tricks and notes

Git
===
Show list of dangling commits with short description:

    git fsck --lost-found | grep "^dangling commit" | sed "s/^dangling commit //g" | xargs git show -s --oneline
