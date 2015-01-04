Install scripts to install sgminer easily under Linux.  

Note: FULL credit goes to GreenRaccoon23. I only have a testing environment for Ubuntu/Xubuntu and have streamlined a few things and also customized some of the paths for compiling the Spreadcoin GPU miner.

- Recommended: Xubuntu/Ubuntu 14.04
- Catalyst Driver does not support versions greater than 14.04
- Arch at your own risk.... I'd love to know if it works or not :-)

In reality your best bet is to understand what each of these scripts is doing, more info here:

https://darkcointalk.org/threads/noob-proof-how-to-install-sgminer-amd-drivers-and-gpu-mine-darkcoin-under-linux-ubuntu-64-bit.1813/  
http://ubuntuforums.org/showthread.php?t=2243387&p=13117766

However, in a nutshell...

- sgminer1.in - installs common dependencies and other updates
- sgminer2.in - installs Catalyst driver (14.9)
- sgminer3.in - installs AMD APP SDK 2.9
- sgminer4.in - compiles SGMiner (spreadcoindx11-sgminer)
- sgminer5.in - creates batch file for mining

My recommendation is to install spreadcoind between steps 4 and 5. At this point the system should be updated and stable. Using the commands listed below it should be really straightforward but note that it takes about 15 minutes to sync the blockchain.

*************************************************************************
** Install spreadcoind before proceeding ********************************
```
mkdir ~/spreadcoin64
cd ~/spreadcoin64
wget http://spreadcoin.net/files/spreadcoin64.tar.xz
tar -xvf spreadcoin64.tar.xz
mkdir ~/.spreadcoin
cat >  ~/.spreadcoin/spreadcoin.conf << EOF
server=1
rpcallowip=*.*.*.*
rpcuser=user
rpcpassword=pass
EOF
cd /usr/bin
sudo ln -s ~/spreadcoin64/spreadcoind .
cd ~/
spreadcoind
```
** Wait for daemon to fully sync
** this can take awhile... check progress using ./spreadcoind getinfo
*************************************************************************

**Ubuntu/Xubuntu/Anybuntu/Debian Users**  
Download, extract, and make executable:  
```
cd ~  
git clone https://github.com/snogcel/sgminer-install-scripts
cd sgminer-install-scripts  
chmod +x *.in  
./INSTALL
```
  
**Arch Linux Users**  
Download, extract, and make executable:  
```
cd ~  
git clone https://github.com/snogcel/sgminer-install-scripts  
cd sgminer-install-scripts  
chmod +x *.in  
./INSTALL
```
  
