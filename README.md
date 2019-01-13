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
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.
#### Solution:
```
sort data.txt | uniq -c
```
Password: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR


#### Bandit Level9 -> Level10:
The password for the next level is stored in the file data.txt in one of the few human-readable strings, beginning with several ‘=’ characters.
#### Solution:
```
strings -a data.txt

MBB
`B6ha
nK)U2u
&y@@2
5Lo%
ru@n
D}U'
e#s.	
!:/%p
*'dZ
bgM>H
M0d>uG
G@?>
"a`*
38zT
`mNg H
:U[,
c?Vh
CEhL5d
2========== the
r,!l
FMQ]2
Sf2 
5iu^B
#e1[u
k+0dbun
h.TF
>V	I
Zaf3
OWj6
GY	E
,ebr
i$Vh
CL}0Vx<M6
mB#L
S%T{`G
LUu]\
`r	$C
xL4%
!AwV
@T.a-
6NJ~
<E:C{{
!|#D
8kk#A
Ju:5s-~
{vbT
1mBO
^VS'
oFP/;l
*m&-
Q"7d
`THN
GI5M
!(Yl
G\@P
h2aO
XvMTP
Hm["V
|,ZO
n1p	A
TE[S
3EQi
)'0U
a;0\
az|Y+
w]Ov
`4F<N
t8lHX u
W.uO7
i$2w
epg~
i^eE
========== password
NHGu
5xhH
|f;P]!
~5&:
oc8,`:
>t=	yP
rV~dHm=
];,I
tw3y
[[N#
xo?C
h\h<M
&B&l
DgdJ
c	_<9>D
Igzz
//Jr
:DLq
qEk9s
ci`2
c([t
y>?+
jgF5X
T}~_Z]
========== isa
P-+i
$OGu
Ez&.
3 5w
"k"}
yA1H]W
	@m>[
fhul
&%I{
g0?W;
SXEO
Q,9_
$!T1
Z:rU
m$jJ
oM\U
g%tq_
"dPy~
ox:z
X9H]*x]
S2Fx
5Vmgn
hP}"
e&/R
czdy
h;W	
g[W%
=FQ?P\U
#u&	ZQ~f
.r@v
H.yKk
\3;W
oZ_N
U4@v
	IOG+
"{q<
=	F[
2YkI!
wt2N
-q}u
5eQP
snn`*
"T?X^
D2HM
H0&t.
$Y)&wA	Y
D%t`
\<Nj
\Zo\h]
'NL}B
*	+ta
Fj~%E
5m*rU?w[
BE3K
]o#s
i_9r
0L&,
HfA0
<h%7
9Mz;
|NJP
pb=x
AAbd<
\+pW
n_'h
f^<-KJ
J;m=
#&Op
\u~#
nd19
o?Mwf
m\uG
Z7 IS|
FN+r
4FS;
lj/f
d3hM
)/<PO
$O@]
qbvT
vXib
]Knt
:m;r
w:	vC
>{Tz
pT{%5
tYrQT(
dsTaFp
lI_z
UoUf
5{0+
Xj/^
cT>ZHE
6G5L
F2wrB
m14g
{82AX
7k6	
~$0bDWT
@Mgk
	:uy
`'8u
!"Di
I#8B
+"aH
?L'[i!#S
!H>k0J
	0l`c
kH )
=)$=
}mOU
[_g25
72\P
xQf]
7li&
========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
ypi*
lTq;
UqUY`
d&lk
wU5	
iv8!=
fBBB
^$a?
,FAl
5M_8
RcJ h
*JI;
mzy8s#
8("Ym
W	3C
c0@L<.
yP1g
?9Xc6
VkcO
ZI	-^ip
*t[z
{d2~
q7 u@
J@&C
JI9J
+TuBy
^ek$
K8P77f+
"1oq
Nd^*<
((97
47M<}
&~Zd
Sh+b
8a?E
+vex1]
Y(Zs
Cl/(;
{4x
```
Password: truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk


#### Bandit Level10 -> Level11:
The password for the next level is stored in the file data.txt, which contains base64 encoded data.
#### Solution:
```
base64 -d data.txt
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
```
Password: IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR


#### Bandit Level11 -> Level12:
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.
#### Solution:
```
cat data.txt | tr 'a-zA-Z' n-za-mN-ZA-M'
```
Password: 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu


#### Bandit Level12 -> Level13:
```
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)
#### Solution:
gzip data2.bin
bandit12@bandit:/tmp/arihant$ ls
data2.bin.gz  data.txt
bandit12@bandit:/tmp/arihant$ file data2.bin.gz 
data2.bin.gz: gzip compressed data, was "data2.bin", last modified: Sun Jan 13 19:04:03 2019, from Unix
bandit12@bandit:/tmp/arihant$ gzip -d data2.bin.gz 
bandit12@bandit:/tmp/arihant$ ls
data2.bin  data.txt
bandit12@bandit:/tmp/arihant$ 
bandit12@bandit:/tmp/arihant$ zcat data2.bin | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/arihant$ ls
data2.bin  data.txt
bandit12@bandit:/tmp/arihant$ zcat data2.bin | bzcat | file -
/dev/stdin: gzip compressed data, was "data4.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
bandit12@bandit:/tmp/arihant$ zcat data2.bin | bzcat | zcat | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/arihant$ zcat data2.bin | bzcat | zcat | tar | file -
tar: You must specify one of the '-Acdtrux', '--delete' or '--test-label' options
Try 'tar --help' or 'tar --usage' for more information.
/dev/stdin: empty
bandit12@bandit:/tmp/arihant$ zcat data2.bin | bzcat | zcat | tar x0 | file -
tar: Options '-[0-7][lmh]' not supported by *this* tar
Try 'tar --help' or 'tar --usage' for more information.
/dev/stdin: empty
bandit12@bandit:/tmp/arihant$ ls
data2.bin  data.txt
bandit12@bandit:/tmp/arihant$ zcat data2.bin | bzcat | zcat | tar xO | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/arihant$ zcat data2.bin | bzcat | zcat | tar xO | tar xO | file -
/dev/stdin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/arihant$ zcat data2.bin | bzcat | zcat | tar xO | tar xO | bzcat | file -
/dev/stdin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/arihant$ zcat data2.bin | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | file -
/dev/stdin: gzip compressed data, was "data9.bin", last modified: Tue Oct 16 12:00:23 2018, max compression, from Unix
bandit12@bandit:/tmp/arihant$ zcat data2.bin | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat | file -
/dev/stdin: ASCII text
bandit12@bandit:/tmp/arihant$ ls
data2.bin  data.txt
bandit12@bandit:/tmp/arihant$ zcat data2.bin | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
```
Password: 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL


#### Bandit Level13 -> Level14:
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on.
#### Solution:
```
cat sshkey.private 
-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAxkkOE83W2cOT7IWhFc9aPaaQmQDdgzuXCv+ppZHa++buSkN+
gg0tcr7Fw8NLGa5+Uzec2rEg0WmeevB13AIoYp0MZyETq46t+jk9puNwZwIt9XgB
ZufGtZEwWbFWw/vVLNwOXBe4UWStGRWzgPpEeSv5Tb1VjLZIBdGphTIK22Amz6Zb
ThMsiMnyJafEwJ/T8PQO3myS91vUHEuoOMAzoUID4kN0MEZ3+XahyK0HJVq68KsV
ObefXG1vvA3GAJ29kxJaqvRfgYnqZryWN7w3CHjNU4c/2Jkp+n8L0SnxaNA+WYA7
jiPyTF0is8uzMlYQ4l1Lzh/8/MpvhCQF8r22dwIDAQABAoIBAQC6dWBjhyEOzjeA
J3j/RWmap9M5zfJ/wb2bfidNpwbB8rsJ4sZIDZQ7XuIh4LfygoAQSS+bBw3RXvzE
pvJt3SmU8hIDuLsCjL1VnBY5pY7Bju8g8aR/3FyjyNAqx/TLfzlLYfOu7i9Jet67
xAh0tONG/u8FB5I3LAI2Vp6OviwvdWeC4nOxCthldpuPKNLA8rmMMVRTKQ+7T2VS
nXmwYckKUcUgzoVSpiNZaS0zUDypdpy2+tRH3MQa5kqN1YKjvF8RC47woOYCktsD
o3FFpGNFec9Taa3Msy+DfQQhHKZFKIL3bJDONtmrVvtYK40/yeU4aZ/HA2DQzwhe
ol1AfiEhAoGBAOnVjosBkm7sblK+n4IEwPxs8sOmhPnTDUy5WGrpSCrXOmsVIBUf
laL3ZGLx3xCIwtCnEucB9DvN2HZkupc/h6hTKUYLqXuyLD8njTrbRhLgbC9QrKrS
M1F2fSTxVqPtZDlDMwjNR04xHA/fKh8bXXyTMqOHNJTHHNhbh3McdURjAoGBANkU
1hqfnw7+aXncJ9bjysr1ZWbqOE5Nd8AFgfwaKuGTTVX2NsUQnCMWdOp+wFak40JH
PKWkJNdBG+ex0H9JNQsTK3X5PBMAS8AfX0GrKeuwKWA6erytVTqjOfLYcdp5+z9s
8DtVCxDuVsM+i4X8UqIGOlvGbtKEVokHPFXP1q/dAoGAcHg5YX7WEehCgCYTzpO+
xysX8ScM2qS6xuZ3MqUWAxUWkh7NGZvhe0sGy9iOdANzwKw7mUUFViaCMR/t54W1
GC83sOs3D7n5Mj8x3NdO8xFit7dT9a245TvaoYQ7KgmqpSg/ScKCw4c3eiLava+J
3btnJeSIU+8ZXq9XjPRpKwUCgYA7z6LiOQKxNeXH3qHXcnHok855maUj5fJNpPbY
iDkyZ8ySF8GlcFsky8Yw6fWCqfG3zDrohJ5l9JmEsBh7SadkwsZhvecQcS9t4vby
9/8X4jS0P8ibfcKS4nBP+dT81kkkg5Z5MohXBORA7VWx+ACohcDEkprsQ+w32xeD
qT1EvQKBgQDKm8ws2ByvSUVs9GjTilCajFqLJ0eVYzRPaY6f++Gv/UVfAPV4c+S0
kAWpXbv5tbkkzbS0eaLPTKgLzavXtQoTtKwrjpolHKIHUz6Wu+n4abfAIRFubOdN
/+aLoRQ0yBDRbdXMsZN/jvY44eM+xRLdRVyMmdPtP8belRi2E2aEzA==
-----END RSA PRIVATE KEY-----

vim sshkey.private.txt .
chmod 600 sshkey.private.txt
ssh -i sshkey.private.txt bandit14@bandit.labs.overthewire.og -p 2220
```
#### Wait! What?
```
                                                                               
Broadcast message from root@bandit (pts/24) (Sun Jan 13 20:19:24 2019):        
                                                                               
sorry, smal reboot coming up.                                                  
no time no time letz do some crime                                             
happy whatever day it is                                                       
cheers                                                                         
morla                                                                          
                                                                               

Broadcast message from root@bandit (pts/24) (Sun Jan 13 20:20:18 2019):

The system is going DOWN for reboot in 10 minutes!

Broadcast message from root@bandit (pts/24) (Sun Jan 13 20:21:18 2019):

The system is going DOWN for reboot in 9 minutes!

Broadcast message from root@bandit (pts/24) (Sun Jan 13 20:22:18 2019):

The system is going DOWN for reboot in 8 minutes!

Broadcast message from root@bandit (pts/24) (Sun Jan 13 20:23:18 2019):

The system is going DOWN for reboot in 7 minutes!
ls -al
total 24
```
#### What the hell happened to bandit!!


#### Bandit Level14 -> Level15:
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

#### Solution: 
login to bandit14
```
cat /etc/bandit_pass/bandit14
Password: 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e

cat /etc/bandit_pass/bandit14 | nc localhost 30000
```
Password: BfMYroe26WYalil77FoDi9qh59eK5xNr


#### Bandit Level15 -> Level16:
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…
#### Solution:
```
echo "BfMYroe26WYalil77FoDi9qh59eK5xNr" | openssl s_client -connect  localhost:30001 -ign_eof
CONNECTED(00000003)
depth=0 CN = localhost
verify error:num=18:self signed certificate
verify return:1
depth=0 CN = localhost
verify return:1
---
Certificate chain
 0 s:/CN=localhost
   i:/CN=localhost
---
Server certificate
-----BEGIN CERTIFICATE-----
MIICBjCCAW+gAwIBAgIENHv1njANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMTkwMTEzMTkzNDMwWhcNMjAwMTEzMTkzNDMwWjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwgZ8wDQYJKoZIhvcNAQEBBQADgY0AMIGJAoGBALOkCuqD
hi2X8nQ1Fu/p2hHx+3SeORNWt76H7Q/Wr8ZYapwViACu7h/d+Gn1Z4/1ZVN5Ukz3
fiS7UiA73eJg2iLo9rXzPw01hVB+IA4RtSTBmsUm7vwIgNDv5RsrYLl6JCGaZ+ns
/z5ihBHILWT3zvLyAn98HUiVAjAahiuwBtHxAgMBAAGjZTBjMBQGA1UdEQQNMAuC
CWxvY2FsaG9zdDBLBglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0
ZWQgYnkgTmNhdC4gU2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3
DQEBBQUAA4GBABiUJgikW8Ig5kuqkB3VCZiACRm5bsC4T5EH531RtzDi6Yywnqm3
xDbfWzLIoWpVq2U2pViIVsPmQ6nGjASQSlQhxsg9kZBaqYB26AcgrmbVIruywtij
JXvZkb10yrXeqtfK5bO8+kILa8XSBVbIXQ55Cn4HiHE7NtDZBOLBTl2/
-----END CERTIFICATE-----
subject=/CN=localhost
issuer=/CN=localhost
---
No client certificate CA names sent
Peer signing digest: SHA512
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1019 bytes and written 269 bytes
Verification error: self signed certificate
---
New, TLSv1.2, Cipher is ECDHE-RSA-AES256-GCM-SHA384
Server public key is 1024 bit
Secure Renegotiation IS supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
SSL-Session:
    Protocol  : TLSv1.2
    Cipher    : ECDHE-RSA-AES256-GCM-SHA384
    Session-ID: CD5198D92457BF75F87A0C0EAEF998DEA63F5AB78C0120DEF334AC278316D6DD
    Session-ID-ctx: 
    Master-Key: 64355AB9924363EF440CCE6C80B54FAA34982B835B2B12FA37ACFE1822FEE578565DBAED62F19A00D63BD8C5A94D2E6A
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 32 a4 5b 29 4b c8 06 db-a5 7e c7 95 4f fd c4 c1   2.[)K....~..O...
    0010 - 55 37 e5 5c a1 91 ba 50-7b 12 f4 5d e4 3a 9d 10   U7.\...P{..].:..
    0020 - 08 5e 80 e3 cc 64 8d e1-d9 16 25 84 53 35 cd 70   .^...d....%.S5.p
    0030 - ea 9e a4 33 8b c6 6e 5e-4c b9 2f 9b 61 a0 01 d4   ...3..n^L./.a...
    0040 - 1a d8 3d f5 d0 e8 9a 3c-0a 97 19 8e 19 2f ae a3   ..=....<...../..
    0050 - 40 56 a7 ed 8e 54 ec 1e-e7 83 32 1e 2e cc 4b 15   @V...T....2...K.
    0060 - 91 c3 c8 d7 f3 fd 54 75-31 9a 6f e1 9a 6c 4a 04   ......Tu1.o..lJ.
    0070 - b8 1f 29 67 5b 2e 0e 09-7e 1a ab 39 8f 96 2e 11   ..)g[...~..9....
    0080 - 45 e0 8b a0 7e bb 79 38-89 ef c1 84 de 0c a4 91   E...~.y8........
    0090 - 41 77 0a c1 e8 c0 4f 28-75 c0 58 c2 ac 6c 0a 82   Aw....O(u.X..l..

    Start Time: 1547411700
    Timeout   : 7200 (sec)
    Verify return code: 18 (self signed certificate)
    Extended master secret: yes
---
Correct!
cluFn7wTiGryunymYOu4RcffSxQluehd

closed
```
Password: cluFn7wTiGryunymYOu4RcffSxQluehd



