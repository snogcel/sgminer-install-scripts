Install scripts to install sgminer easily under Linux.  

Note: FULL credit goes to GreenRaccoon23 - really nicely done, I just changed a few settings to utilize the Spread miner.

More detailed instructions under these guides:  
https://darkcointalk.org/threads/noob-proof-how-to-install-sgminer-amd-drivers-and-gpu-mine-darkcoin-under-linux-ubuntu-64-bit.1813/  
http://ubuntuforums.org/showthread.php?t=2243387&p=13117766

*************************************************************************
** Install spreadcoind before proceeding ********************************

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
./spreadcoind

** Wait for daemon to fully sync
** this can take awhile... check progress using ./spreadcoind getinfo
*************************************************************************

**Ubuntu/Xubuntu/Anybuntu/Debian Users**  
Download, extract, and make executable:  
```
cd ~  
git clone https://github.com/snogcel/sgminer-install-scripts
cd sgminer-install-scripts  
mv sgminer-install-scripts/s*.in .  
chmod +x *.in  
rm -df sgminer-install-scripts  
```
  
**Arch Linux Users**  
Download, extract, and make executable:  
```
cd ~  
git clone https://github.com/snogcel/sgminer-install-scripts  
cd sgminer-install-scripts  
mv sgminer-install-scripts/a*.in .  
chmod +x *.in  
rm -df sgminer-install-scripts  
```
  
