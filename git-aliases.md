Copy-paste to `.gitconfig` under `[alias]` section.
```bash
# Merge commit
mer="!git merge \"$1\" --no-ff -m \"Merge branch '$1' into '$(git rev-parse --abbrev-ref HEAD)'\" --commit #"
# Add and commit changes
co="!git add . && git commit -m \"$1\" #"
sta=status
creb=checkout -b
delb=branch -d
ma=checkout master
# Push current branch to origin
pub=!git push origin $(git rev-parse --abbrev-ref HEAD)
# Files changed in the current branch
cha=diff --name-status master...HEAD
alias="!git config --global --list | grep \"alias\\.\""
# All commits made in the current branch
branch-commits="!git show-branch --current  | grep \"$(git rev-parse --abbrev-ref HEAD)\""
# First commit of the current branch
branch-start="!git rev-parse --short=7 $(git show-branch --current | grep \"$(git rev-parse --abbrev-ref HEAD)\" | grep -E \"^\\s.{1,10}\\*\" | tail -n 1 | grep -Eo \"\\[.*\\]\" | sed 's/\\[//' | sed 's/\\]//') "
```