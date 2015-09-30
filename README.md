# bind

Einstellungen für DNS auf den Gateways



Anleitung:

useradd -m -s /bin/bash dnsbind


cd /home/dnsbind

git clone https://github.com/ffod/bind.git

chown dnsbind:dnsbind bind -R

chmod +x bind/updatedns.sh

/home/dnsbind/bind/updatedns.sh


*/5 * * * * /home/dnsbind/bind/updatedns.sh > /dev/null 2>&1

