# vscode-merge-preview-rebase
sets up a scenario where you can rebase a branch to show a potential 'visual/context' bug (non-breaking/non-functional) in the new vscode merge preview when doing a rebase.  Its totally possible this is intended but at first glance when I saw it it seemed backwards
# vscode-merge-preview-rebase
sets up a scenario where you can rebase a branch to show a potential 'visual/context' bug (non-breaking/non-functional) in the new vscode merge preview when doing a rebase. 

Its totally possible this is intended but at first glance when I saw it it seemed backwards


To replicate the bug within VSCode first clone this repository and run the following commands:
```
git checkout branch1
git rebase main
```

This should cause a simple merge conflict
The issue, is the wording of 'Yours' vs 'Theirs'

When I first saw this, it sliglthy confused me because the 'Yours' section was actaully coming from `main` not `branch1`. 

During a rebase this kinda makes sense though that VScode thinks this because the 'source branch' (`main`) is applied first, then your changes.  Hence VScode thinks its a bit opposite.

This 'bug' might be a phisopical isssue, but it confused me enough in my more complicated merge conflict that I thought I would bring it up.