# ubuntu-nvidia-brightness-issue
Brightness Control failure on Ubuntu Nvidia-gpu laptops

Problem : Brightness Control failure on modern laptops with nvidia gpu. Here is a list of what did NOT work.

THESE DONT FIX THE ISSUE

1. xrandr : Only adds opacity higher values add milky brightness
	bash : xrandr —output eDP —brightness 1.0
    
2. ls /sys/class/backlight/
	for b in /sys/class/backlight/*; do
	  echo "== $b =="
  	  cat $b/brightness
	  done

SOLUTION


Step 1 : Navigate to grub
	    sudo nano /etc/default/grub
Step 2 : GRUB_CMDLINE_LINUX_DEFAULT="quiet splash pcie_aspm=force acpi_backlight=native"

Step 3: CTRL+O to write out and enter to save, CTRL+X to close

Brightness control issue resolved.
