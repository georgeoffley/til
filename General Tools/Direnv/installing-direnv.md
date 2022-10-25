# Install Direnv

[Source](https://direnv.net/docs/installation.html)

The above link will send you to the page for installation of Direnv. However, I find it easier to install via [Homebrew](https://formulae.brew.sh/formula/direnv) or [sudo apt-get](https://www.willandskill.se/en/install-direnv-on-ubuntu-18-04-in-1-min/). 

After the install you need to [hook the program into your shell](https://direnv.net/docs/hook.html).

The above link brings you to the instructions to do this, however I find it easier to just use the [echo command](https://phoenixnap.com/kb/echo-command-linux) to add the [eval command](https://www.geeksforgeeks.org/eval-command-in-linux-with-examples/) into the needed RC file. 

So for example, on a mac just using ZSH you can run the below command:

`echo 'eval "$(direnv hook zsh)"' >> ~/.zshrc`

#GeneralTools 
	#Direnv 