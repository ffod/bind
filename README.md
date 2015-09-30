# bind

Einstellungen für DNS auf den Gateways



Anleitung:

useradd -m -s /bin/bash dnsbind


cd /home/dnsbind
git clone https://github.com/freifunkhamburg/bind
chown dnsbind:dnsbind bind -R
/home/dnsbind/bind/updatedns.sh


*/5 * * * * /home/dnsbind/bind/updatedns.sh > /dev/null 2>&1

