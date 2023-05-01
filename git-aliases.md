# Aliases

Just a list of my running aliases the i like.

These should be added to the `[alias]` section of the `~/.gitconfig` file
---
```
  st = status
  br = branch --format='%(authordate:relative)%09%09   %(refname)' --sort='-committerdate'
  ck = checkout
  cp = cherry-pick
  ckt = checkout --track
  aliases = !git config --get-regexp 'aliases.*' | colrm 1 6 | sed 's/[ ]/ = /'
  lg = log --graph --pretty = format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date = relative
  delete-squashed = "!f() { local targetBranch=${1:-master} && git checkout -q $targetBranch && git branch --merged | grep -v \"\\*\" | xargs -n 1 git branch -d && git for-each-ref refs/heads/ \"--format=%(refname:short)\" | while read branch; do mergeBase=$(git merge-base $targetBranch $branch) && [[ $(git cherry $targetBranch $(git commit-tree $(git rev-parse $branch^{tree}) -p $mergeBase -m _)) == \"-\"* ]] && git branch -D $branch; done; }; f"
  c = commit -am
  ll = log --oneline
  last = log -1 HEAD --stat
  d = diff
```
