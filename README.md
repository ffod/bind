# bind

Einstellungen für DNS auf den Gateways



Anleitung:

useradd -m -s /bin/bash dnsbind

cd /home/dnsbind

su bind

git clone https://github.com/ffod/bind.git

chmod +x bind/update*

exit

/home/dnsbind/bind/updatestofrei.sh

*/5 * * * * root /home/dnsbind/bind/updatestofrei.sh > /dev/null 2>&1
