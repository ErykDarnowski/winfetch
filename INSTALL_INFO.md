### Manual
For people who are allergic to package managers.

Note: By not installing Winfetch via a package manager, you will not be able to automatically update Winfetch. Each time a new version is released, you will have to go through these steps again.

#### Using `git`

First, clone this repository:
```
$ git clone git@github.com:ErykDarnowski/winfetch.git
```
Reset the repository to the latest release:
```
$ cd winfetch
$ git reset --hard v0.0.0
```
Then, move the `winfetch.ps1` file to somewhere on your PATH:
```
$ mv .\winfetch.ps1 ~\.local\bin\
```

#### Using `powershell`

To download the script directly use:
```pwsh
# download development version
Invoke-WebRequest "https://raw.githubusercontent.com/ErykDarnowski/winfetch/master/winfetch.ps1" -OutFile ~\.local\bin\winfetch.ps1 -UseBasicParsing

# download a specific version
Invoke-WebRequest "https://raw.githubusercontent.com/ErykDarnowski/winfetch/v2.0.0/winfetch.ps1" -OutFile ~\.local\bin\winfetch.ps1 -UseBasicParsing
```

To execute winfetch directly without saving the file to disk use:
```pwsh
Invoke-WebRequest "https://raw.githubusercontent.com/ErykDarnowski/winfetch/master/winfetch.ps1" -UseBasicParsing | Invoke-Expression
```

---

#### Legacy systems

Run this command in `cmd.exe` to download the batch file (for systems that can't run PowerShell 5+):

```batch
bitsadmin /transfer winfetchjob /download /priority foreground "https://raw.githubusercontent.com/ErykDarnowski/winfetch/legacy/winfetch.bat" "C:\your\path\here\winfetch.bat"
```