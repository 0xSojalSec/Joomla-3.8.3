# Joomla-3.8.3-Exploit
Second Order SQL injection using python
This is an exploit that targets the privilege escalation vulnerability found in certain Joomla! versions. 

## Vulnerability Information
| **CVE:**                |   CVE-2018-6376    |
|-------------------------|--------------------|
| **NVD Published Date:** |    01/30/2018      |
| **Base Score**          |   9.8 Critical     |
| **Vulnerability Type**  |Privilege Escalation|

### Official CVE Description: 
In Joomla! before 3.8.4, the lack of type casting of a variable in a SQL statement leads to a SQL injection vulnerability in the Hathor postinstall message. 

### What is Joomla!
Joomla! is a content management system (CMS) that is free and open-sourced. This platform is used to build web sites and online applications. It has a variety of features that allows people to use it for a diverse range of web-based content including websites, intranets, e-commerce sites, and so much more. Furthermore, Joomla! offers development features that allow developers to build upon the framework. It is also based on PHP and MySQL and uses object-oriented programing techniques.

## Exploit Usage
To use this exploit, you must know the credentials of at least one user and they must have enough permissions to be able to access the administrator page of Joomla!


### Configuring the Exploit Script
Next, you need to open the JoomlaExploit.py script and then modify the specified values below.
The detailed usage of each value is described in comments within the python script.

```
url = "http://localhost/Joomla!/administrator/index.php"
url2 = "http://localhost/Joomla!/administrator/index.php?option=com_admin&view=profile&layout=edit&id=182"
user = "Test"
passwd = "Test"
name = "Test"
userEmail = test@test.com

```

### Running the Exploit
Once you have modified the payload to fit your specific enviornment, you just need to run the script via a command line using the command below. The command will work if you are in the same directory as the python script, otherwise you will need to use the absolute path.

```
python3 ./JoomalExploit.py
```

Needed dependencies are `BeaufifulSoup4` and `requests`. If not already installed, they can be installed using the following commands:

```
pip3 install bs4
pip3 install requests
```

## Full PoC Walkthrough + Written Guide
I have also written a detailed walkthrough of this exploit. It includes setting up Joomla!, manually exploiting Joomla!, and a reference to the JoomlaExploit.py code. This code and the article fully compliment eachother. The blog post can be found here:

[Joomla! Privilege Escalation Exploit](https://medium.com/@keishauber131/joomla-privilege-escalation-exploit-fc80a44905ff?sk=69a5edaaded2d372bf9ff1d888b4230e)

## Disclaimer
This script was developed to automate the exploitation used against the CVE-2018-6376 vulnerability found in certain versions of Joomla!. It is a PoC and this script should only be used for educational purposes.   
