## Projects with submodules

# Notes for git commands to manage project with submodules within submodules
## When adding new submodule:
### run git submodule add [URL] [Project Name]
#### ** Note: above will clone project fetch files and folders but will only fetch the folder name of submodules (subsubmodules) not the files
### git submodule update --init --recursive
#### ** Note:  Running just git submodule update will not fetch subsubmodules file for new projects, running git submodule update --init --recursive instead will clone the subsubmodules files. problem though is --init --recursive will try to update other submodules too. 

## When updating submodule already in project:
### run git submodule update --remote
#### Pulling in Upstream Change
##### The simplest model of using submodules in a project would be if you were simply consuming a subproject and wanted to get updates from it from time to time but were not actually modifying anything in your checkout. Let’s walk through a simple example there.
##### Git will by default try to update ALL of your submodules when you run git submodules update --remote. If you have a lot of them, pass the name of the submodule you want updated.

#### Pulling Upstream Changes
##### Simply running git pull to get your newly commited changes is not enough

## questions to ask
- do you need to run git submodule update --init --recursive inside parent submodule or can you run in root of projects
- git submodules update --remote only gets updates from submodules not the root of project?
- when running git submodule update --remote (ie git fetch > git merge) in root I can see change in project as (new commit) do I need to merge or not?
- if update is done on local machine inside submodule, how do you push to github.
- How do you fetch from new subsubmodules using --init --recursive flags with out fetching incorrectly from other submodules
  
## remove submodule
To remove a submodule you need to:

Delete the relevant section from the .gitmodules file.
Stage the .gitmodules changes git add .gitmodules
Delete the relevant section from .git/config.
Run git rm --cached path_to_submodule (no trailing slash).
Run rm -rf .git/modules/path_to_submodule (no trailing slash).
Commit git commit -m "Removed submodule "
Delete the now untracked submodule files rm -rf path_to_submodule

