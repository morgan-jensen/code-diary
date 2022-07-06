# Git Config Variables

_Background_: While my coworker was reviewing a pull request, he noticed that the git credentials were wrong for the author. They were set to the name of the previous developer that worked on that machine. I was confused, because I was with the new developer when they changed the credentials to their own. While researching what would be the cause, I learned that there are acutally 3 levels of git config variables, and that while our new coworker had changed the global variables to be theirs, the local variables inside the repository were still set to the previous developer.

## About Git Config Variables

**There are 3 levels of git variables. Each overrides the previous.**

1. System Variables: These variables will apply to any user on the machine.
2. Gloabal Variables: These variables apply to the user on every repository.
3. Local Variables: These variables are local to a specific repository.

If `git config user.name` is set within a repository, it will override the variable set with `git config --global`

**How to view the different levels**

- System level: `git config --list --system`
- Global level: `git config --list --global`
- Local level: `git config --list --local`

To check what username or email will be used at the current level, user `git config user.name` or `git config user.email`. If you are in a repository with local user variables set, it will display the local variables, otherwise it will show the lowest level's set variables (either global or system).
