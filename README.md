# my_tech(ubuntu 18 machine)

installed **terminator**

installed **fish** - type *fish_config* on cli and follow

installed **sublime text 3**

installed **pip3** 

installed **anaconda** to run *jupyter notebook*

install gnome tweaks

sudo apt install bucklespring / use 'snap' - nostalgia

autoenv - A pip package for ease of python environment activations



## Interesting things to check out:-
https://tutorials.ubuntu.com/tutorial/basic-snap-usage#0


## Important things to remember:-

1. Where are update and apt-get files are stored?
	- /var/cache/apt/archives
	- usage: sudo apt-get install <package name>
			 sudo aot-get update
	- apt(Advanced Package Tool) : cli tool for package management on linux distros like ubuntu, debian, mint etc. 		

2. conda has some techgnical issues when running with fish shell.This link helps,
https://stackoverflow.com/questions/34280113/add-conda-to-path-in-fish/34280406#34280406

3. Much needed extentions(firefox version)
	Https everywhere,
	Grammarly,
	Wikiwand,
	ad block plus,
	momentum,
	hoxx vpn,
	onetab,
	english popup dictionary
	
	web search navigator(chrome) - keyboard shortcuts for surfing the web 
	https://github.com/infokiller/web-search-navigator


4. Using NVM(node version manager)

   If you're using Node Version Manager (nvm), you can switch to a different version of Node.js by using the `nvm use` command. Here's how you can do it:

	1. First, check the available versions of Node.js on your system with `nvm ls`. The output will show all installed versions.
	2. If you don't have the required version (16.14 or higher as per your error message), you can install it using `nvm install 16.14`.
	3. After installation, you can switch to the new version with `nvm use 16.14`.

	Now, your terminal session will use the specified version of Node.js. You can verify this by running `node -v`, which should output `v16.14`.
	
	After switching to the compatible Node.js version, try running `yarn install` again in your project directory.
	
	Remember, nvm settings are local to the terminal session. If you open a new terminal window or tab, you'll need to select the Node.js version again using `nvm use`.
