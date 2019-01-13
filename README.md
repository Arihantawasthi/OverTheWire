# OverTheWire
## Bandit :: Cracked
You will encounter many situations in which you have no idea what you are supposed to do. Don’t panic! Don’t give up! The purpose of this game is for you to learn the basics. Part of learning the basics, is reading a lot of new information.


#### Bandit Level0:
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.
#### Solution:
```
ssh bandit0@bandit.labs.overthewire.org -p 2220

This is a OverTheWire game server. More information on http://www.overthewire.org/wargames

bandit0@bandit.labs.overthewire.org's password: 
Linux bandit 4.18.12 x86_64 GNU/Linux
               
      ,----..            ,----,          .---. 
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' ' 
  |   :  | ; | ' ;    |.';  ; ;   \  \;      : 
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ; 
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"  
     \   \ .'        ;   |.'       \   \ ;     
  www. `---` ver     '---' he       '---" ire.org     
               
              
Welcome to OverTheWire!

If you find any problems, please report them to Steven or morla on
irc.overthewire.org.

--[ Playing the games ]--

  This machine might hold several wargames. 
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ and /proc/ is disabled
  so that users can not snoop on eachother. Files and directories with 
  easily guessable or short names will be periodically deleted!
	
  Please play nice:
      
    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS! 
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro 

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few usefull tools which you can find
 in the following locations:

    * pwndbg (https://github.com/pwndbg/pwndbg) in /usr/local/pwndbg/
    * peda (https://github.com/longld/peda.git) in /usr/local/peda/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /usr/local/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)
    * checksec.sh (http://www.trapkit.de/tools/checksec.html) in /usr/local/bin/checksec.sh

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us through IRC on
  irc.overthewire.org #wargames.

  Enjoy your stay!
```


#### Bandit Level0 -> Level1:
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.
#### Solution:
```
cat readme
Password: boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```


#### Bandit level1 -> level2:
The password for the next level is stored in a file called - located in the home directory.
#### Solution:
```
cat ./-
```
Password: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9


#### Bandit Level2 -> Level3:
The password for the next level is stored in a file called spaces in this filename located in the home directory.
#### Solution:
```
cat spaces/ in/ this/ filename
```

Password: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK


#### Bandit Level3 -> Level4:
The password for the next level is stored in a hidden file in the inhere directory.
#### Solution:
```
ls
cd inhere
ls -al
cat ./.hidden
```

Password: pIwrPrtPN36QITSp3EQaw936yaFoFgAB


#### Bandit Level4 -> Level5:
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.
#### Solution:
```
array=('-file00' '-file01' '-file02' '-file03' '-file04' '-file05' '-file06' '-file07' '-file08' '-file09')
for item in ${array[*]}
do
cat ./$item
printf "\n"
done
```

Password: koReBOKuIDDepwhWk7jZC0RTdopnAYKh


#### Bandit Level5 -> Level6:
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
human-readable
1033 bytes in size
not executable
#### Solution:
```
file . -type f -size 1033c ! -executable -exec file {}+ | grep ASCII
cat ./maybehere07/.file2
```
Password: DXjZPULLxYr17uwoI01bNLQbtFemEgo7


#### Bandit Level6 -> Level7:
The password for the next level is stored in the file data.txt next to the word millionth.
#### Solution:
```
grep 'millionth' data.txt
```
Password: cvX2JJa4CFALtqS87jk27qwqGhBM9plV


#### Bandit Level7 -> Level8:
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.


#### Bandit Level6 -> Level7:
The password for the next level is stored somewhere on the server and has all of the following properties:

owned by user bandit7
owned by group bandit6
33 bytes in size
#### Solution:
```
file / -size 33c -user bandit7 -group bandit6 2>/dev/null
cat var/lib/dpkg/info/bandit7.password
````
Password: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs


#### Bandit Level7 -> Level8
The password for the next level is stored in the file data.txt next to the word millionth

#### Solution:
```
grep 'millionth' data.txt
```
Password: cvX2JJa4CFALtqS87jk27qwqGhBM9plV


#### Bandit Level8 -> Level9
