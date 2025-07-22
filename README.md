# set-english-locale.sh
Setting system locale to English in arch linux distro  Cachy Os.
Setting system locale to English in arch linux distro 
Cachy Os.

✅ How to save and run:

1. Open a terminal and run:

nano set-english-locale.sh


2. Paste the script below:

#!/bin/bash

echo "🔧 Setting system locale to English (en_US.UTF-8)..."

# 1. Enable only en_US.UTF-8 in /etc/locale.gen
sudo sed -i 's/^#\s*\(en_US.UTF-8 UTF-8\)/\1/' /etc/locale.gen
sudo sed -i '/^sq_/d' /etc/locale.gen   # Remove Albanian locales if present
sudo sed -i '/^#.*sq_/d' /etc/locale.gen

# 2. Generate locales
sudo locale-gen

# 3. Set system-wide locale
sudo bash -c 'cat > /etc/locale.conf << EOF2
LANG=en_US.UTF-8
LC_ALL=en_US.UTF-8
EOF2'

# 4. Clean personal environment overrides (optional)
sed -i '/LC_/d' ~/.bashrc 2>/dev/null
sed -i '/LANG=/d' ~/.bashrc 2>/dev/null
echo "export LANG=en_US.UTF-8" >> ~/.bashrc
echo "export LC_ALL=en_US.UTF-8" >> ~/.bashrc

echo "✅ Locale successfully set to English (en_US.UTF-8). Please reboot."



3. Save and exit:

Press Ctrl + O, then Enter to save.

Press Ctrl + X to exit.



4. Make it executable:

chmod +x set-english-locale.sh


5. Run it with root permission:

sudo ./set-english-locale.sh



Then reboot your system to apply the new locale settings.

If you download the tar version here are the steps to install it:

tar -xvf set-english-locale.tar.gz
cd set-english-locale
chmod +x set-english-locale.sh
sudo ./set-english-locale.sh

And don't forget to spread the blessed word i use "Arch Linux Btw ".

