
#homebrew
#brew
#brew-cask
#brew-tap
#brew-formula
#package-manager
#brew-commands

you can do three things here 

1. install a terminal package 
2. GUI application using **cask**
3. clone a github repo using **tap**

### locations

brew is installed and installs all the packages and related file in usr/local

Homebrew downloads and installs packages in the cellar directory.
The cellar location:/usr/local/Cellar

```
The packages are installed in usr/local/Cellar (original)

Then the installed packages are symlinked into 
/usr/local  Which actually means symlinked into (if needed): 

/usr/local/bin  (if a binary file present in a package)
/usr/local/lib  (if a lib file is present in a package)
/usr/local/include (if a include header is there in the orginal package)

```

![[Screenshot 2023-07-20 at 6.40.03 PM.png]]

The /usr/local/bin directory must take precedence over /bin, /usr/bin,   /sbin and /usr/sbin, see .bash_profile.

```
To check this: 

echo $PATH 

The $PATH is searched from beginning to end, with the first matching executable being run.
thus we also need to add a path of an executable if its not present in it. which if the package is installed from brew will never be the case. 

```
for a reminder :

|   |   |
|---|---|
|||
|/usr/local/bin|Locally installed software that a normal user may run.|
|/usr/local/sbin|Locally installed programs for system administration.|
|/bin|User utilities fundamental to both single-user and multi-user environments.|
|/usr/bin|Common utilities, programming tools, and applications.|
|/sbin|System programs and administration utilities fundamental to both single-user and multi-user environments.|
|/usr/sbin|System daemons & system utilities (executed by users).|

## Terms

### Formula 

**brew formula**  - its a ruby script which defines / installs a package and create the links (in manner discussed above) and manage that package.

```
The formula contains information such as:
	Where the package tar ball, 
	containing the package source, can be downloaded from.
	What package dependencies it has. How to install the package.
```
Example 

![[Screenshot 2023-07-20 at 6.46.48 PM.png | 500]]

### Cask 

Cask is an extension of Homebrew. Just like a formula they are Ruby scripts but they are used to download and install GUI applications.

The Casks on the macOS can be found at:  
```
/usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask/ Casks/<package-name>.rb!
```


![[Screenshot 2023-07-20 at 6.51.43 PM.png | 500]]


### Tap

A tap refers to a Git repository and the repository name starts with “homebrew-“

it can be used to clone a git repository and then install it via brew.

```
brew tap                                (Show all current tapped repositories)
brew tap <user/repository>             (clone a homebrew repository)
brew tap <user/repository-name>  <url>  (clone a public repository from the url)
brew untap <user/repository-name>        (remove the repo)
```

## Brew commands

```
brew --version
brew doctor                   ( checks for potential problem )
brew help <command>           (  Print help information for a brew command)
```

##### search install remove formulas 

```
1. brew search <file>       ( searches for formula and casks in brew repo online)
2. brew info <formula>       (get the info related to the formula and cask )
3. brew list                ( Show all installed formulae and casks)
4. brew install <formula>
5. brew reinstall <formula>
6. brew uninstall <formula>
The package will not be uninstalled if other formulae depends on the formula.  
Use the --force argument if you want to ignore this check.

7. brew cleanup              (Delete all old versions for all installed formulae.)
8. brew cleanup <formula>    (Delete older versions of the specified formula.)
9. brew cleanup -n           ( Display all formulae that will be removed (dry run))

10. brew install --cask <text>   (intalls a GUI application)
11. brew uninstall --cask <text>  (uninstalls a GUI application)
```

##### Updates and Upgrades

```
1. brew update               ( Updates all the packages and Homebrew itself to the latest version)

2. brew upgrade             ( Upgrade outdated casks and outdated, unpinned formulae using the same options they were originally installed with)

3. brew outdated            ( list all the casks and formulae that have an updated version available)

4. brew upgrade <formula>    ( Upgrade the specified formula.)

5. brew pin <formula>       (  Pin the specified formula, preventing them from being upgraded when issuing the brew upgrade formula command.)

6. brew unpin <formula>

7. brew update-reset         ( Fetch and reset Homebrew and all tap repositories (or any specified repository) using git to their latest origin/HEAD.)
```