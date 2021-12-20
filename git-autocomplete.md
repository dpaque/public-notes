# Autocompletion for git bash aliases

Goal: Get autocompletion for branch names on the bash alias `alias gco="git checkout"`

Context: Pop!_OS 21.10 (quite similar to Ubuntu)

## What worked for me

Copy the conent of https://github.com/git/git/blob/master/contrib/completion/git-completion.bash to `~/.git-completion.bash`

Add the follwing lines to the beginning of your `.bash_aliases`

```
# git bash completion
source ~/.git-completion.bash

# allow auto completion
__git_complete gco _git_checkout
```

Restart bash or `source ~/.bash_aliases`


## What did not work me 

I tested the following instructions without success in December 2021:

### Using the already existing git-completion.bash from my git folder

I tried to use the git-completion.bash which was already in my git folder: /usr/share/bash-completion/completions/git. However this file was slightly different to the one on github. Using the file from my directory I ran into the following issue:

When using tab for the auto completion I got:
`bash: [: 1: unary operator expected`

Using the file directly from github resolved that issue for me.

### Not using __git_complete

In this guide https://davidwalsh.name/git-branch-autocompletion the part `__git_complete gco _git_checkout` is not mentioned. That did not work for me.

### More sources

- https://stackoverflow.com/questions/9869227/git-autocomplete-in-bash-aliases
- https://stackoverflow.com/questions/342969/how-do-i-get-bash-completion-to-work-with-aliases

