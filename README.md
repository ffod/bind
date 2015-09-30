# bind

Einstellungen für DNS auf den Gateways



Anleitung:

useradd -m -s /bin/bash dnsbind


cd /home/dnsbind
git clone https://github.com/freifunkhamburg/bind
chown dnsbind:dnsbind bind -R
/home/dnsbind/bind/updatedns.sh


*/5 * * * * /home/dnsbind/bind/updatedns.sh > /dev/null 2>&1

Das Logging des dhcpd wird nun konfiguriert. Die Datei /etc/rsyslog.d/dhcpd.conf anlegen mit dem Inhalt
local7.warn /var/log/dhcpd.log

Danach die Logdatei anlegen
touch /var/log/dhcpd.log
chown root:adm /var/log/dhcpd.log
chmod 600 /var/log/dhcpd.log

Nun in der Datei /etc/rsyslog.conf die Zeile
mail,news.none;              -/var/log/messages
in
mail,news.none;local7.none              -/var/log/messages
ändern.

Und die Zeile
*.*;auth,authpriv.none;              -/var/log/syslog
in
*.*;auth,authpriv.none;local7.none              -/var/log/syslog
ändern.

Nun rsyslog neustarten
service rsyslog restart
