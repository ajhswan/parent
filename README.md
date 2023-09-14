## Projects with submodules

# Notes for git commands to manage project with submodules within submodules
## When adding new submodule:
### run git submodule add <giturl> [Project Name]
#### ** Note: above will clone project fetch files and folders but will only fetch the folder name of submodules (subsubmodules) not the files
### git submodule update --init --recursive
#### ** Note:  


## questions to ask
- do you need to run git submodule update --init --recursive inside parent submodule or can you run in root of projects
- git submodules update --remote only gets updates from submodules not the root of project?
  
## remove submodule
To remove a submodule you need to:

Delete the relevant section from the .gitmodules file.
Stage the .gitmodules changes git add .gitmodules
Delete the relevant section from .git/config.
Run git rm --cached path_to_submodule (no trailing slash).
Run rm -rf .git/modules/path_to_submodule (no trailing slash).
Commit git commit -m "Removed submodule "
Delete the now untracked submodule files rm -rf path_to_submodule

