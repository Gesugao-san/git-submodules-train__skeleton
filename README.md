
---
### Cloning the repo
```powershell
ECHO %CD%
#DIR
#CD "." # Where "." is path to your git projects folder
git clone "https://github.com/Gesugao-san/git-submodules-train__skeleton"
```
---
### (Re)installation of submodules
```powershell
git submodule deinit -f "submodules/git-submodules-train__core"
RM -r -fo ".git/modules/" # Remove the files associated to the submodule
#FINDSTR /V "path =" ".gitmodules" > ".gitmodules" # ToDo: Remove any references to submodule in config (https://stackoverflow.com/a/37795902)
CD "./submodules/"
RM -r -fo "./core/"
git rm -fr --cached "./core" # Remove it from the cache without the "git"
CD ..
Clear-Content "./.gitmodules" # Remove .gitmodules contents

#git mv "submodules/git-submodules-train__core" "submodules/core"
git submodule add --name "core" "https://github.com/Gesugao-san/git-submodules-train__core" "submodules/core" # Add submodule
git ls-files --stage "submodules/core"
git submodule sync "submodules/core"
git submodule status "submodules/core"
git submodule update "submodules/core"
git submodule update --remote "submodules/core"
git submodule update --remote --rebase "submodules/core"

```
---
