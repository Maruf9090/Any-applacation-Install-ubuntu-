# Any-applacation-Install-ubuntu-


How to install Kali Linux tools in Ubuntu or Linux mint
Rabius Sany

Rabius Sany
·

2 min read
·
May 29, 2023

#kali #linux #kalitools #ubuntu #linuxmint #tools #repository #ethicalhacker

Ubuntu and Linux Mint are much more stable than Kali Linux. So we can use it as our primary os. But How will we install Kali Linux tools in other Linux distros?

This article will help you in this case.

Step 1: Add Kali repository to our Linux Pc.

here is the command :

sudo sh -c "echo 'deb https://http.kali.org/kali kali-rolling main non-free contrib' > /etc/apt/sources.list.d/kali.list"

Step 2: Install GnuPG :

sudo apt install gnupg

Step 3: Now, for the system to verify Kali Linux packages, you need to add the public key of this distribution. Download it and add it with the following 2 commands:

wget 'https://archive.kali.org/archive-key.asc'

sudo apt-key add archive-key.asc

Step 4: Now we need to set the correct priority for packages from Kali Linux repositories: they will have a lower priority than the others, as a result, Kali Linux packages (for example, kernels) will not be installed automatically, but manually you can install any packages that you need.

sudo sh -c "echo 'Package: *'>/etc/apt/preferences.d/kali.pref; echo 'Pin: release a=kali-rolling'>>/etc/apt/preferences.d/kali.pref; echo 'Pin-Priority: 50'>>/etc/apt/preferences.d/kali.pref"

Step 5: Updating the package :

sudo apt update

Step 6: Now install any tools you want :

sudo apt install -t kali-rolling [package_name]

Example :

sudo apt install -t kali-rolling burpsuite

Thank you for reading.

My name is Rabius Sany.


https://medium.com/@sany4sec/how-to-install-kali-linux-tools-in-ubuntu-or-linux-mint-b2ce8453964e
