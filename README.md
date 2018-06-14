# Tutorials
Some usefull tutorials. Feel free to contribute with all you

## Summary

## 1. GIT
### 1.1. Change git default editor
```bash
git config --global core.editor "your-editor" 
``` 

### 1.2. Show current branch on terminal

1. Open your `.bashrc`
```bash
vim ~/.bashrc 
``` 

2. Add the following lines at the end of the file
```bash
function git_branch_name() {
  git branch 2>/dev/null | grep -e '^*' | sed -E 's/^\* (.+)$/(\1) /'
}


function show_colored_git_branch_in_prompt() {
  PS1="\[\033[01;32m\]\u@\h:\[\033[01;34m\]\w\[\033[31m\]\$(git_branch_name)\[\033[m\]$ "
}

show_colored_git_branch_in_prompt 
``` 

### 1.3. Add aliases to git commands
1. Open your `.gitconfig` 
```bash
vim ~/.gitconfig 
``` 

2. Add a new session called `[alias]` and add your aliases

```bash
[user]
  email = user@email.com
  name = user
[core]
  editor = vim
[alias]
  st = status
  d = diff
  pom = push origin master
```

3. Now you can use your custom commands like this:
```bash
# Equivalent to 'git push origin master'
git pom
```
