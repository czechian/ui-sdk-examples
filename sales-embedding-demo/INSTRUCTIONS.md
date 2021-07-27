# Instructions for Non-Developers

The following steps will guide you through running this application on your computer for the very first time. The following steps do not aim to explain the basic concepts of frontend development.

> Use at your own risk!

(You can jump back to [README](README.md), or skip forward to [CONFIGURATION](CONFIGURATION.md) if you've done this before.)

## Instructions for MacOS

### Open Terminal

1. Open Spotlight Search (hit `CMD + Spacebar`)
1. Search for `Terminal.app`
1. Hit `Enter`

<img src="public/instructions/01-terminal-01.png" width=800>

---

### Install brew

Check if you have brew installed on your machine:

* `brew -v`
* (specific version does not matter)

<img src="public/instructions/02-brew-01.png" width=800>

If you have brew installed on your machine, proceed to [installing npm](#install-npm). Otherwise do:

1. Visit https://brew.sh/
1. Copy `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"` into your clipboard
1. Paste into your Terminal window
1. Hit `Enter`

Confirm that brew installed successfully by running `brew -v`, then proceed to [installing npm](#install-npm).

---

### Install npm

Check if you have npm installed on your machine:

* `npm -v`
* Ideally, you should be running **npm version 6.x.x**
* Different version of npm may be fine too, but it is known that **npm 7.x.x** does **not** work

<img src="public/instructions/03-npm-01.png" width=800>

If you have npm version 6 installed on your machine, proceed to [installing yarn](#install-yarn). Otherwise do:

* `brew install node@12`
* (npm version 6 will be installed with Node version 12)

> If you have different version of npm installed, you can `brew uninstall node`, and then `brew install node@12` that includes the desired npm version 6.

Confirm that npm installed successfully by running `npm -v`, then proceed to [installing yarn](#install-yarn).

---

### Install yarn

Check if you have yarn installed on your machine:

* `yarn -v`
* (specific version does not matter)

<img src="public/instructions/04-yarn-01.png" width=800>

If you have yarn installed on your machine, proceed to [checking if git is working](#check-that-git-is-working). Otherwise do:

* `npm install -g yarn`

Confirm that yarn installed successfully by running `yarn -v`, then proceed to [checking if git is working](#check-that-git-is-working).

---

### Check that git is working

* `git --version`
* (specific version does not matter)

<img src="public/instructions/05-git-01.png" width=800>

If git is working, proceed to [clonning the repository](#clone-the-repository-and-run-the-app). Otherwise do:

* `xcode-select --install`

Once Xcode command line tools are installed, confirm that git is working by running `git --version`, then proceed to [clonning the repository](#clone-the-repository-and-run-the-app).

---

### Clone the repository and run the app

First, navigate to the folder where you'd like to have this repository clonned. If the folder does not exist, you can create it first, for example:

1. `mkdir ~/Documents/my-projects`
  * Hint: `mkdir` stands for "make directory"
  * Hint: `~` means "home directory", i.e. `~/` is the same as `/Users/<your-username>/`
1. `cd ~/Documents/my-projects/`
  * Hint: `cd` stands for "change directory"

<img src="public/instructions/06-mkdir-01.png" width=800>

Now, clone the repository, enter the repository folder, enter the project folder, install the dependencies and run the app:

1. `git clone --depth 1 https://github.com/gooddata/ui-sdk-examples.git`
1. `cd ui-sdk-examples/sales-embedding-demo/`
1. `yarn install`
1. `yarn start`

<img src="public/instructions/07-start-01-clone.png" width=800>
<img src="public/instructions/07-start-02-install.png" width=800>
<img src="public/instructions/07-start-03-start.png" width=800>
<img src="public/instructions/07-start-04-running.png" width=800>

Once the app is started, your browser will most likely warn you that "Your connection is not private." Click on `Advanced` and then `Proceed to localhost (unsafe)`. In case you don't see the the `Advanced` button or the `Proceed to localhost (unsafe)` link, simply click anywhere inside the page and start typing `thisisunsafe`; see https://stackoverflow.com/questions/58802767/no-proceed-anyway-option-on-neterr-cert-invalid-in-chrome-on-macos/58957322 for more.

<img src="public/instructions/07-start-05-private.png" width=800>
<img src="public/instructions/07-start-06-advanced.png" width=800>
<img src="public/instructions/07-start-07-login.png" width=800>
<!-- <img src="public/instructions/07-start-08-login.png" width=800> -->

1. The app should now be running at https://localhost:3000, and you should see the log in form.
1. **At this point, there is no need for you to log in.**
1. Let's kill the app by hitting `CTRL + C` in Terminal, and proceed to [CONFIGURATION](CONFIGURATION.md).

> Note: Some of the links in the app (e.g. My Work, Settings) are dummy and inactive, only there to make an impression of a real application.

<img src="public/instructions/08-kill-01.png" width=800>

## Instructions for Windows

TODO

## Troubleshooting

#### gyp: No Xcode or CLT version detected!

This can happen when operating system update was installed recently. You can try:

1. `xcode-select --print-path` (typically `/Library/Developer/CommandLineTools`), then
2. `sudo rm -r -f /Library/Developer/CommandLineTools` (or whatever path you got in 1)
3. `xcode-select --install`

#### Node Sass does not yet support your current environment: OS X 64-bit

This can happen with wrong version of Node/npm. If you installed Node using brew, you can try `brew uninstall node`, and then `brew install node@12` that includes the desired version of npm.

## Screenshots

![login](public/login.png)
![homepage](public/homepage.png)
