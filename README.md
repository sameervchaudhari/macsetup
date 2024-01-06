- Mac installation

-  By default, Homebrew installs software packages in the user's home directory, so there should be no conflicts with system-wide installations.
-  Users have full control over their home directories, so they can install and manage software without needing administrator privileges.

- Create a Group:
  -     sudo dscl . -create /Groups/yourgroupname   [dscl (Directory Service command line utility).]
- Create a User
  -     sudo dscl . -create /Users/username
        sudo dscl . -create /Users/username RealName "Full Name"
        sudo dscl . -create /Users/username UniqueID 1001  # You can choose a unique ID
        dscl . -read /Groups/groupname
        sudo dscl . -create /Users/username PrimaryGroupID 20  # Set the primary group to 'staff'
        sudo dscl . -create /Users/username NFSHomeDirectory /Users/username
        sudo dscl . -passwd /Users/username YourPassword  # Set the user's password
        sudo mkdir /Users/username
        sudo chown username:staff /Users/username

- Install homeBrew
         /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

         (echo; echo 'eval "$(/usr/local/bin/brew shellenv)"') >> /Users/svc/.zprofile
          eval "$(/usr/local/bin/brew shellenv)"

           ==> This script will install:
              /usr/local/bin/brew
              /usr/local/share/doc/homebrew
              /usr/local/share/man/man1/brew.1
              /usr/local/share/zsh/site-functions/_brew
              /usr/local/etc/bash_completion.d/brew
              /usr/local/Homebrew
              ==> The following new directories will be created:
              /usr/local/bin
              /usr/local/etc
              /usr/local/include
              /usr/local/lib
              /usr/local/sbin
              /usr/local/share
              /usr/local/var
              /usr/local/opt
              /usr/local/share/zsh
              /usr/local/share/zsh/site-functions
              /usr/local/var/homebrew
              /usr/local/var/homebrew/linked
              /usr/local/Cellar
              /usr/local/Caskroom
-  First, ensure that the users you want to grant access to Homebrew are members of a specific group (e.g., brewusers).
-      sudo dseditgroup -o edit -a username1 -t user brewusers
       sudo dseditgroup -o edit -a username2 -t user brewusers
       sudo chgrp -R brewusers /usr/local
       sudo chmod -R g+w /usr/local


       brew help
-   for updating pasword of user
-     sudo passwd username


# Add more users as needed


<!---
sameervchaudhari/sameervchaudhari is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
