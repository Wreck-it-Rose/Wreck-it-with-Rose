---
modified: 04-23-2025 @ 09:35
---
## Primer - Things You Should Know First:

>[!abstract]+ **Resources already available to you**
> - [**Quartz Site**](https://quartz.jzhao.xyz/)
> 	- The official Quartz site is a wonderful resource and easy to navigate if you know what you're looking for. Keep this in your back pocket as a reference.
> - [**Nicole van der Hoeven YouTube Tutorial**](https://www.youtube.com/watch?v=6s6DT1yN4dw)
> 	- Nicole provides a much needed and solid guide for those who prefer video instruction. It covers the basics and will get you up and running. Not all steps are covered in the amount of detail I personally prefer.  This approach might trip you up as you follow along (like it tripped me 🤕).


## Foundation and Terminology:
### **node.js**
The over-simplified version as it relates to [Quartz](https://quartz.jzhao.xyz/) and [Obsidian](https://obsidian.md/):
- Quartz, uses node.js to execute JavaScript on the 'backend' via terminal commands on your device to generate static-site information from Markdown files (Obsidian's bread and butter).
- JavaScript natively runs in an internet browser environment (often referred to as the 'frontend') which can be limiting for certain use cases.
- [node.js](https://nodejs.org/en/about) is a runtime which facilitates the execution of JavaScript code directly on your device. Without node.js, Quartz couldn't transform your precious local files into a magnificent personalized website.

A vastly more technical explanation of Quartz architecture can be found [here](https://quartz.jzhao.xyz/advanced/architecture)

### **Node Version Manager (NVM)**
Now that we've established the crucial importance of node.js, we need to manage it:
- As you may have deduced, node.js was NOT developed solely for Quartz's implementation.
- Quartz, as well as other projects, are built with respect to specific versions of node.js.
- One does not simply update, or roll-back, a singular installation of node.js without the risk of breaking a program which depends on the original version.
- This is where NVM comes in:
	- It allows you to install multiple versions of node.js
	- It also facilitates switching between those versions via terminal command line instructions. 

If you're still onboard this crazy train, let's install **node.js** with **NVM**:

1. open your device's terminal and enter the following:
	- replace *v0.40.2*  with latest stable version of NVM -> [check here](https://github.com/nvm-sh/nvm?tab=readme-ov-file#install--update-script) 
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.2/install.sh | bash
```

^fbfb59

- Let's break this down a little further for you curious mittens:
	- *curl -o-* :  downloads and installation script from the provided URL and outputs it in a standard manner.
	- | (*vertical pipe symbol*): This output is then sent to *bash* to be executed.
	- 
![[Screenshot 2025-04-22 at 10.47.43 PM.png]]

2. After the above command has completed running, let's verify it was installed correctly:
```bash
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")" [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
```
- Let's break this down too:
	- Simply: this command checks to see if the correct environment variable is set for NVM and expands NVM functionality to the appropriate (current) directory if necessary. This ensures nvm instructions will run correctly in the terminal.
	- why is the snippet I provided different from the snippet suggested in the above image?
		- *Either snippet can be used*, but the snippet I provided in the code block offers more flexibility because it standardizes where configuration files are located in respect to different applications.
			- Use the image snippet if you ALWAYS want NVM to be installed in the default location.
			- Use the snippet provided in the code block if you'd rather respect the `XDG_CONFIG_HOME` environment variable. (this results in a more standardized configuration directory).
	
3.  Let's check the installed version of NVM:
```bash
nvm -v
```

![[Screenshot 2025-04-23 at 8.23.46 AM.png]]
- The NVM version displayed should match the version you indicated in the installation instruction in [[Start Here#^fbfb59 | Step 1]].

4. Now to find and the right node.js version:
```bash
nvm -ls remote
```





