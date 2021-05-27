# "Guest Additions" installations
## On Ubuntu
Before "Insert Guest Additions CD image" :

`sudo apt install build-essential dkms linux-headers-$(uname -r)`

# User access to shared folders
To give the user the permissions to access the shared folders :

`sudo usermod -a -G vboxsf $USER`
