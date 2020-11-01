# remote-sublime
Enables Sublime Text to be activated on remote file from command line. Instructions are credited to: 
  * [emamie](https://stackoverflow.com/questions/37458814/how-to-open-remote-files-in-sublime-text-3?answertab=votes#tab-top)
  * [RemoteSubl](https://github.com/randy3k/RemoteSubl)

## Additions
Primarily to provide a better configuration tailored to my needs. 

## Commands
#### Install on Remote Server
```bash
wget -O /usr/local/bin/rsub \https://raw.github.com/aurora/rmate/master/rmate
chmod a+x /usr/local/bin/rsub
```

## &#8595;


#### Connect to Remote Server
```bash
ssh -R 52698:localhost:52698 server_user@server_address
```

#### Alternative: Add to your ssh config
This way you do not have to type in that command every time. 
*Fill in the <..>*<br>
**Last Line Syntax:** ```RemoteForward <local machine>:<port> <remote server>:<port>```
```
Host <hostname>
	User <username>
	HostName <hostname>
	Port <port number>
	IdentityFile <path to identity file>
	RemoteForward localhost:52968 localhost:52968
```

#### Command to open a file in Sublime
```bash
rsub path_to_file/file.txt
```
#### Open ZSHRC or .bashrc (whichever you use) to make a new alias. 
```bash
alias edit="rsub"
```
