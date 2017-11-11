# angular-from-0

all commands in here are run from your Terminal.  Each number has a footnote below.

### 1. Make your hidden files visible
Run:

```bash
defaults write com.apple.finder AppleShowAllFiles YES
```

### 2. Install Homebrew
Check to see if you have Homebrew:

```bash
brew --version
```

If not, Download Homebrew
```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### 3. Install git
Check to see if you already have git

```bash
git --version
```

If not, Download git. (see, homebrew is already making your life easy):

```bash
brew install git
```

### 4. Install node.js
Check to see if you already have it:

```bash
node --version
```
If not, Download it in two steps:

```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.31.0/install.sh | bash
```
navigate to your home directory in Finder, and look for a file called '.bash_profile'. Open it up with a text editor and add these two lines to the end of the file:

```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" # This loads nvm
```

Save the file and close it. *Quit Terminal and then reopen it.* Then run:

```bash
nvm install stable
```
### 5. Install yarn

brew ftw again:
```bash
brew install yarn
```

### 6. Install Angular CLI
```bash
yarn global add @angular/cli
```

### 7. Create a new coding directory

Run these one at a time:

"Change" into your home directory
```bash
cd ~
```

Look around, you should see your familiar folders/files here:
```bash
ls
```

Make a new directory, call it whatever you want (I called it coding):
```bash
mkdir coding
```

Look around again, you should see your new directory:
```bash
ls
```

"Change" into your new directory:
```bash
cd coding
```

Look around again, you shouldn't see anything in your folder here since you just created it:
```bash
ls
```

(Get in the habit of "changing" and "looking", this is a very important skill from the command line, it helps you navigate everywhere.)

Common uses of these commands:
```
cd ~  ##go home
cd some-folder  ## go into some folder relative to where you are right now
cd ..           ## go up one level
cd /usr/bin     ## go into some folder relative to the "root" of the file system
cd /            ## go to the root of the filesystem

ls              ## list files/directories
ls -anl         ## list files/directories including hidden ones and show metadata

cat some-file.txt   ## shows the contents of a file in the console
```

### 8. Create a new angular project
Okay, enough of that.  Change back into your new coding directory and create a new angular app (call it whatever you want, here it's called honeybadger:
```bash
ng new honeybadger
```

That should've created a new directory called lthb. Change into it and run your new server with ng serve:
```bash
cd honeybadger
ng serve
```

### 9. Check to see your app is running
Go to http://localhost:4200
If it's there, then congrats, this is the new app you've created! And it's being served out of your local computer on port 4200.  Whenever you like what you have, I can show you how to serve it out of Amazon and give it a real domain name.

### 10. Download [VS Code](https://code.visualstudio.com/)
This is a decent IDE (Integrated Development Environment).  It's like Microsoft Word for coding.
Once VS Code is running, go to File -> Open -> and select the directory that your app is in

#### SIDE NOTE
```bash
cd ~
```

Create a file called .functions
```bash
touch .functions
```
Open up that file in some text editor, you could open it in VS Code now (in VS Code go to File -> Open, etc, it should be visible under your user's home directory).  

Add the following to that file, and then save and close it.

```bash
# open vs code
code () {
    VSCODE_CWD="$PWD" open -n -b "com.microsoft.VSCode" --args $*
}
```
Once you save it and close it, close all open instances of VS Code. Restart Terminal.

From now on you can use the command "code" to open up a file or directory in VS Code.

For example cd to your angular app:
```
cd ~
cd coding
code honeybadger
```
That should open the honeybadger app with VS Code!
#### 11. END SIDE NOTE

### Experiment with your new app

Once your app is open, Navigate to app.component.html (in VS Code to open something, use CMD+P and start typing: appcomp...)
Change something in that html file.  Keep localhost:4200 open in Chrome.  See your changes!
* This file is html, so look up any tutorial on html and begin playing around with that code there.
* To get more advanced, open up app.component.ts.  This is Typescript, feel free to begin playing around with that.
* If you reach this far, let me know... there is plenty to do from here.

# Footnotes

[0] Open up a Finder window, and you'll notice a ton of new "hidden files" that you've never seen before.  These are useful because when you're coding, you'll want to be able to edit these.  If these ever get annoying, you can turn it off with this: defaults write com.apple.finder AppleShowAllFiles NO

[1] Homebrew is a package manager for Mac OS.  Think of a package manager as an App Store for certain types of software packages. Rather than trying to download and configure software yourself, a package manager lets you download many different types of software with a single command.  Homebrew can be used to download nearly everything you need.

[2] Git is a version control system. It allows you to save and track changes and share changes with other people. Super useful when you want to remember what you changed or if more than one person wants to edit some code at the same time.

[3] Node.js is a Javascript engine.  It lets you write code in Javascript and run it on your computer.  You're probably familiar with other Javascript engines: Chrome, Firefox, IE.  They're browsers, but one central thing browsers are good at is running Javascript.  Node.js will let you play around with javascript and write stuff without needing to run it in a browser (though you'll do that too).

[4] yarn is another package manager. like homebrew. Except it specializes in installing javascript and typescript packages that you will be using frequently.

[5] Angular CLI (Command Line Interface) is used for creating and running Angular projects.  Angular is a web framework made by Google.  It provides some cool UI and coding benefits for developing a web application.

[6] Angular is a framework created by Google to allow you to code complex webapps more easily.
