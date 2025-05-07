# Installing Git on Your Computer

In this workshop, we will be working with a version control software called
`git`.

First, let's make sure you have `git` installed. You can find general install
instructions on [Github](https://github.com/git-guides/install-git). The
approach depends on your operating system:

* **Windows:** You can install `git` via [git for
  Windows](https://gitforwindows.org).
* **Mac:** It is very likely `git` is already on your Mac. You can open a
  terminal and run `git version` to make sure. If it's not installed, you can
  install it using [Homebrew](https://brew.sh) by running the command `brew
  install git`. You can also install `git` in a `conda` environment, if you're
  using Anaconda. Simply run `conda install git`.
* **Linux:** You can use whatever package management system your distribution
  uses to install `git`. For Debian/Ubuntu, this is `apt`. Specifically, run the
  command `sudo apt-get install git-all` in a terminal.

# Creating a Github Account

Next, you need to make sure you have a Github account. If you have already
signed up on Github, go ahead and login right now. If you have not created an
account, go to [this link](https://github.com/join) and create an account with
your email address. Be sure to check your email in order to validate your
account. Once you've created an account, sign into Github.

# Creating Git Authentication Tools

Github is an online platform to provides a place to store updates to code
repositories you might work with. It works tightly with the `git` software, and
provides additional tools to facilitate working with repositories. In order to
keep your code safe, Github has some security settings in place that we need to
work through before we can use it to its fullest extent.

First, if you haven't already, create an authentication token which will be
used in order to interact with Github. Go to this
[link](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
and follow the steps to create the authentication token on Github. 
<br>
1. In the upper-right corner of any page on GitHub, click your profile photo, then click ⚙️Settings.
2. In the left sidebar, click  <>Developer settings.
3. In the left sidebar, under  Personal access tokens, click Tokens (classic).
4. On the right upper corner, Click Generate new token and click Generate new token (classic).
5. Make sure to click `repo` under 'Select scopes' when creating a personal access token.

**Be sure to save the token in a safe place on your computer. If you lose it,
you'll have to create another one.**

Another secure approach that is easier to use on a day-to-day basis, but more
complicated to install, is to set up SSH keys. See this
[link](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
for more details.


