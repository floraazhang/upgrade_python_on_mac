# Upgrade python on Mac & Set the latest version as default in terminal and Sublime Text
> **Open Terminal**<br>



### Use Homebrew to install the latest version of Python:
If you don't have Homebrew yet, it's not late to install it now. Installing Homebrew with one command line and save your life.
	
	/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

Install python with homebrew

	$ brew install python3
<br>


### Set the latest version as default:

	$ rm '/usr/local/bin/python'
	$ brew link python@2
<br>	


### Link the latest version in Sublime Text:
1. Open Sublime Text
2. Tools -> Build System -> New Build System...
	<img src="https://github.com/floraazhang/upgrade_python_on_mac/raw/master/img/1.png"/>
3. In the new file, write:
	
		{
		    "cmd": [“/usr/local/bin/python3”, "-i", "-u", "$file"],
		    "file_regex": "^[ ]File \"(...?)\", line ([0-9]*)",
		    "selector": "source.python"
		}
	
	<img src="https://github.com/floraazhang/upgrade_python_on_mac/raw/master/img/2.png"/>
4. Save the file with meaningful name such as<br>
	**Python3.sublime-build**<br>
	, and save it at<br>
	**~/<ENTER_YOUR_USER_NAME>/Library/Application Support/Sublime Text 3/Packages/User**
	
	<img src="https://github.com/floraazhang/upgrade_python_on_mac/raw/master/img/3.png"/>

5. Tools -> Build
6. File -> New File<br>
	Write:
	
		import sys
		print (sys.version)
		print ("hello world")
	Save it with a random name.<br>
	Run the file with **command+b**<br>
	The output should be:
	
		3.7.0 (v3.7.0:1bf9cc5093, Jun 26 2018, 23:26:24) 
		[Clang 6.0 (clang-600.0.57)]
		hello world
		[Finished in 0.1s]
	(3.7.0 is currently the latest version)
	<img src="https://github.com/floraazhang/upgrade_python_on_mac/raw/master/img/4.png"/>
7. Done