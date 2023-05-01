# Aliases

Just a list of my running aliases the i like

---
```
alias.st=status
alias.br=branch --format='%(authordate:relative)%09%09   %(refname)' --sort='-committerdate'
alias.ck=checkout
alias.cp=cherry-pick
alias.ckt=checkout --track
alias.aliases=!git config --get-regexp 'alias.*' | colrm 1 6 | sed 's/[ ]/ = /'
alias.lg=log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative
alias.delete-squashed=!f() { local targetBranch=${1:-master} && git checkout -q $targetBranch && git branch --merged | grep -v "\*" | xargs -n 1 git branch -d && git for-each-ref refs/heads/ "--format=%(refname:short)" | while read branch; do mergeBase=$(git merge-base $targetBranch $branch) && [[ $(git cherry $targetBranch $(git commit-tree $(git rev-parse $branch^{tree}) -p $mergeBase -m _)) == "-"* ]] && git branch -D $branch; done; }; f
alias.c=commit -am
help.autocorrect=20
```
