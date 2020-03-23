# 11 - SSH Setup for flere Github kontoer
## Multiple SSH Keys settings for different github account
* Kilde :
  * [Multiple SSH Keys settings for different github account](https://gist.github.com/jexchan/2351996)  
  * [How to manage multiple SSH key pairs](https://www.redhat.com/sysadmin/manage-multiple-ssh-key-pairs)  
  * [How can multiple private keys be used with ssh?](https://askubuntu.com/questions/1962/how-can-multiple-private-keys-be-used-with-ssh)  
### Create different public key
create different ssh key
```
ssh-keygen -t rsa -b 4096 -C "user1@domain1.com" -f ~/.ssh/id_rsa_MyGithub1 
ssh-keygen -t rsa -b 4096 -C "user2@domain2.com" -f ~/.ssh/id_rsa_MyGithub2 
```
for example, 2 keys pairs created at:
```
~/.ssh/id_rsa_MyGithub1
~/.ssh/id_rsa_MyGithub1.pub
~/.ssh/id_rsa_MyGithub2
~/.ssh/id_rsa_MyGithub2.pub
```
then, add these two keys as following
```
$ ssh-add ~/.ssh/id_rsa_MyGithub1
$ ssh-add ~/.ssh/id_rsa_MyGithub2
```
you can delete all cached keys before
```
$ ssh-add -D
```
finally, you can check your saved keys
```
$ ssh-add -l
```
### Modify the ssh config
```
$ cd ~/.ssh/
$ touch config
$ subl -a config
```
Then added
```
#MyGithub1 account
Host github.com-MyGithub1
	HostName github.com
	User git1
	IdentityFile ~/.ssh/id_rsa_MyGithub1

#MyGithub2 account
Host github.com-MyGithub2
	HostName github.com
	User git2
	IdentityFile ~/.ssh/id_rsa_MyGithub2
```
* NOTE!
  * *Host*    
            Restricts the following declarations (up to the next Host or Match keyword) to be only for those hosts that match one of the pat‐
             terns given after the keyword.  If more than one pattern is provided, they should be separated by whitespace.  A single ‘*’ as a
             pattern can be used to provide global defaults for all hosts.  The host is usually the hostname argument given on the command
             line (see the CanonicalizeHostname keyword for exceptions).
  * *HostName*  
             Specifies the real host name to log into.  This can be used to specify nicknames or abbreviations for hosts.  Arguments to
             HostName accept the tokens described in the TOKENS section.  Numeric IP addresses are also permitted (both on the command line
             and in HostName specifications).  The default is the name given on the command line.
  * *User*  
             Specifies the user to log in as.  This can be useful when a different user name is used on different machines.  This saves the
             trouble of having to remember to give the user name on the command line.  
  * *IdentityFile*  
             Specifies a file from which the user's DSA, ECDSA, Ed25519 or RSA authentication identity is read.  The default is ~/.ssh/id_dsa,
             ~/.ssh/id_ecdsa, ~/.ssh/id_ed25519 and ~/.ssh/id_rsa.  Additionally, any identities represented by the authentication agent will
             be used for authentication unless IdentitiesOnly is set.  If no certificates have been explicitly specified by CertificateFile,
             ssh(1) will try to load certificate information from the filename obtained by appending -cert.pub to the path of a specified
             IdentityFile.  
             Arguments to IdentityFile may use the tilde syntax to refer to a user's home directory or the tokens described in the TOKENS sec‐
             tion.  
             It is possible to have multiple identity files specified in configuration files; all these identities will be tried in sequence.
             Multiple IdentityFile directives will add to the list of identities tried (this behaviour differs from that of other configura‐
             tion directives).  
             IdentityFile may be used in conjunction with IdentitiesOnly to select which identities in an agent are offered during authentica‐
             tion.  IdentityFile may also be used in conjunction with CertificateFile in order to provide any certificate also needed for
             authentication with the identity.
### Modify your Git config
for MyGithub1
```
$ git config user.name "user1"
$ git config user.email "user1@domain1.com" 
```
for MyGithub2
```
$ git config user.name "user2"
$ git config user.email "user2@domain2.com" 
```
### Move public keys respective github accounts
  * [See copy an SSH Key](https://github.com/sekt1953/ESP32-Seniorhus-2020-1#setup-git-ssh-)  
