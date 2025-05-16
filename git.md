# GIT


### Remove large files from commits(history)   

This trick I get from copilot. [git-filter-repo](https://github.com/newren/git-filter-repo)

1. Must have python(3) + pip on the computer. In my case I have python3
    1. Check the $PATH of your python, in my computer the git-filter-repo was installed in the ~/.local/bin. I'm current using the zsh shell and must have the line "export PATH=$PATH:$HOME/.local/bin"
2. Install the tool to rewrite the repo git-filter-repo: pip3 install git-filter-repo
3. Execute in the project folder "git filter-repo --path-glob '*.apk' --invert-paths". My project is a react native.
