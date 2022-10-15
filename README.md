# vscode-merge-preview-rebase
sets up a scenario where you can rebase a branch to show a potential 'visual/context' bug (non-breaking/non-functional) in the new vscode merge preview when doing a rebase.  Its totally possible this is intended but at first glance when I saw it it seemed backwards

Its totally possible this is intended but at first glance when I saw it it seemed backwards

# How to replicate
To replicate the bug within VSCode, first clone this repository and run the following commands:
```
git checkout branch1
git rebase main
```

This should cause a simple merge conflict

The issue, is the wording of 'Yours' vs 'Theirs'
<img width="969" alt="Screen Shot 2022-10-15 at 12 22 29 AM" src="https://user-images.githubusercontent.com/479738/195970325-5a5934c8-2fc6-428b-9e53-ea28fb6fcb9d.png">


When I first saw this, it sliglthy confused me because the 'Yours' section was actually coming from `main` not `branch1`. 

During a rebase this kinda makes sense though that VScode thinks this, since the 'source branch' (`main`) is applied first, then the changes from the branch (`branch1`).  Hence, to the users perspective, its seems the wrong way around.

When doing a merge instead of a rebase, the Yours/Theirs wording is as expected.
<img width="1004" alt="Screen Shot 2022-10-15 at 12 22 58 AM" src="https://user-images.githubusercontent.com/479738/195970341-c898fd70-9131-491e-a60d-239a353f8455.png">


This 'bug' might be a philosophical isssue, but it confused me enough in my more complicated merge conflict that I thought I would bring it up.
