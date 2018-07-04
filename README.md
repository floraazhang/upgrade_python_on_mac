# Upgrade python on Mac & Set the latest version as default in terminal and Sublime Text
> **Open Terminal**



### Use Homebrew to upgrade the latest version of Python:

	$ brew install python3


### Set the latest version as default:

	$ cp /usr/local/bin/python3.7 /usr/local/bin/python3
	$ cp /usr/local/bin/python3 /usr/local/bin/python
	
### Link the latest version in Sublime Text:
1. Open Sublime Text
2. Tools -> Build System -> New Build System...
3. In the new file, write:
	
		{
		    "cmd": [“/usr/local/bin/python3”, "-i", "-u", "$file"],
		    "file_regex": "^[ ]File \"(...?)\", line ([0-9]*)",
		    "selector": "source.python"
		}
5. Save the file with meaningful name such as<br>
	**Python3.sublime-build**<br>
	, and save it at<br>
	**~/<ENTER_YOUR_USER_NAME>/Library/Application Support/Sublime Text 3/Packages/User**
6. Tools -> Build
7. File -> New File<br>
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
8. Done