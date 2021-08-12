
```powershell
ECHO %CD%
#DIR
#CD . # Path to your git projects folder
git clone "https://github.com/Gesugao-san/git-submodules-train__skeleton"
git submodule deinit --all
#git mv "submodules/git-submodules-train__core" "submodules/core"
git submodule add "https://github.com/Gesugao-san/git-submodules-train__core" "submodules/core"
git submodule sync 
```
