# Ubuntu environment settings

## Print the PATH:
    echo $PATH
The output may include acouple of directories which are seperated by __:__.

> There are two type of environment variables one is on system level and one is on user level.

## System Level
    /etc/environment
    /etc/profile
    /etc/bash.bashrc
    
## User Level
    ~/.profile
    ~/.bash_profile 
    ~./bash_login
    ~/.bashrc
    
## Example
    sudo vi /etc/profile 
    
    PATH=$PATH:$JAVA_HOME/bin  
    export PATH
    
    source /etc/profile
Except for the /etc/environment file.
   
   
Reference: https://help.ubuntu.com/community/EnvironmentVariables
    
    
