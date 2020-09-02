### .gitconfig
Here is a relatively generic `.gitconfig` file with template name/email and alias definitions. Vim serves as the config's default editor.

#### Usage
Copy and paste the desired sections into your own `.gitconfig` file. Alternatively, replace the `.gitconfig` file altogether and modify the name and email fields.

##### Windows locations
- System: `mingw32\etc\gitconfig` or `mingw64\etc\gitconfig`
- Global: `C:\Users\<username>\.gitconfig`
- Local: Git's repo `.git` folder

##### Linux locations
- System: `~etc/gitconfig`
- Global: `~home/<username>/.gitconfig` or `root/.gitconfig` with `sudo`
- Local: Git's repo `.git` folder

(I tend to use the global config)

### Custom functions
The custom functions are defined in separate bash scripts and, functionally, are the same as the aliases defined in the `.gitconfig` file. 
All scripts begin with `git-[command]`, and are called like any other git command (eg. `git gud`)

Function description:
- `git-gud` : Checkout to a branch based on a branch name substring (eg. git gut 2000 = git checkout bugs/kz/2000_crash)
- `git-majonez` : Push commits and checkout master
- `git-try-merge` : Pull latest master branch and merge current branch with it
- `git-purge-local` : Remove all branches that were deleted or merged in the origin

#### Usage
Either copy the scripts to a folder of your choosing, or leave the scripts in the repository's folder. Make sure that the scripts have execute permissions (use `chmod +x [filename]`)

Add the following code to the `bash_profile` file:
```
    #!/bin/bash
    # For git commands
    export PATH=$PATH:/Path/to/script/folder
    # Other existing export statements.
    # End of file
```

Example for this repository: `export PATH=$PATH:/c/dev/.config/git-config`

##### Windows location
`C:\Users\<username>\.bash_profile`

###### Linux location
`~/.bash_profile` 

Additionally for `Linux`, you will need to `source` the file to apply the changes: `source ~/.bash_profile`