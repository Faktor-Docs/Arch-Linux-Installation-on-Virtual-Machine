##### 1. Create New Virtual Drive and select Arch Linux ISO File
###### Oracle Virtual Box is used for installation
###### Start virtual machine and select Install Arch Linux(Option-1)
##### 2. Check internet connectivity
	ping google.com
##### 3. Update Keyring
	pacman -Sy archlinux-keyring
##### 4. Start Installation(with UI)
	archinstall
##### 5. If archinstall command not found, install it
	pacman -Sy archinstall
###### Preffered Options:<br>
######	- Mirror Region: India
######	- Drives: Select Created Virtual Drive(sda)
######	- Disc layout: Wipe all select drive
######	- Extension: btrfs
######	- Set root password
######	- Create user account and enable it as a sudo user
######	- Additional package: git
######	- Network Configuration: Use Network manager
######	- Set time zone
######	- Proceed to installation
##### 6. After Installation, Yes to chroot environment
##### 7. Install required packages
	pacman -Sy firefox libreoffice-fresh flatpak make
##### 8. Exit from chroot environment
	exit
##### 9. Shutdown
	shutdown now
##### 10. Remove iso file and start virtual machine again
###### Login with the user creaed in ttyl environment
#### Install GUI
###### Here GNOME Desktop is considered. We can explore other options like Plasma-KDE, Cinnamon etc...
##### 11. Check compatible graphics controller
	lspci | grep -e VGA
##### 12. Update and upgrade
	sudo pacman -Syyu
##### 13. Install virtual box graphics utility
	sudo pacman -S virtualbox-guest-utils
##### 14. Install Display server(xorg)
	sudo pacman -S xorg xterm xorg-xinit
##### 15. To test display server
	startx
##### 16. Install Desktop Environment
	sudo pacman -S gnome
##### 16. Install terminal
	sudo pacman -S gnome-terminal
##### 17. Start GDM service
	sudo systemctl start gdm.service
###### If the enviroment chaged to GNOME Desktop open terminal and execute from next command
##### 18. Enable GDM service
	sudo systemctl enable gdm.service
##### 19. Reboot to confirm changes
	reboot
