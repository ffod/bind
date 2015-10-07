# bind

Einstellungen für DNS auf den Gateways



Anleitung:

useradd -m -s /bin/bash dnsbind


cd /home/dnsbind

git clone https://github.com/ffod/bind.git

chown dnsbind:dnsbind bind -R

chmod +x bind/update*

/home/dnsbind/bind/updateffod.sh
/home/dnsbind/bind/updateja.sh


*/5 * * * * root /home/dnsbind/bind/updateffod.sh > /dev/null 2>&1
*/5 * * * * root /home/dnsbind/bind/updateja.sh > /dev/null 2>&1

