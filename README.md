# bbb-lfb-ansible

Ansible playbook zur Installation von BBB auf den LFB Maschinen.

Roh und ungeschliffen.

## Vorgehen

* Server mit Ubuntu 16.04 mit IPv4 Adresse
* DNS Eintrag anlegen (BSP bbb.meinedomain.de)
* Sicherstellen, dass man sich als root mit SSH-Key auf den Server verbinden kann
* Anpassen der Einstellungen im Playbook (Das muss ausgelagert werden)
* ``ansible-playbook -u root -i "bbb.meinedomain.de," bbb.yml``
* Anschließend muss man noch einen Greenlight admin acocunt anlegen, wenn man das haben möchte. Als root auf dem Serevr anmelden, ``cd greenlight``, dort ``docker exec greenlight-v2 bundle exec rake user:create["Lokaler Admin","admin@bbb.local","SUOERGEHEIMESPASSWORT","admin"]``
