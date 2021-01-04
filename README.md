# git-branch-name-on-terminal
Present git branch name on terminal prompt

* Place the following code on `~/.bash_profile` of your machine
```sh
get_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

# configure prompt with colours and branch name
export PS1="\[\033[1;35m\]\u\[\033[0;35m\]@\[\033[0;35m\]\H: \[\033[4;36m\]\w\[\033[32m\]\$(get_git_branch)\[\033[00m\] $ "

# autocompletion
[[ -r "/usr/local/etc/profile.d/bash_completion.sh" ]] && . "/usr/local/etc/profile.d/bash_completion.sh"
```
* The result will be like:
![Alt text](https://github.com/sandyGanoti/git-branch-name-on-terminal/blob/main/Screenshot%202021-01-04%20at%2011.03.36.png?raw=true)



reference: https://www.mfitzp.com/article/add-git-branch-name-to-terminal-prompt-mac/
