# bbb-ansible

Ansible playbook zur Installation von BBB auf einer "nackten" Ubuntu 16.04 Maschine

Roh und ungeschliffen.

## Vorgehen

* Server mit Ubuntu 16.04 mit IPv4 Adresse
* DNS Eintrag anlegen (BSP bbb.meinedomain.de)
* Sicherstellen, dass man sich als root mit SSH-Key auf den Server verbinden kann: ``ssh root@bbb.meinedomain.de`` muss ohne PW funktionieren.
* Anpassen der Einstellungen im Playbook: Alle FIXMES müssen angepasst werden
* ``ansible-playbook -u root -i "bbb.meinedomain.de," bbb.yml`` - dauert lange!
* Anschließend muss man noch einen Greenlight admin acocunt anlegen, wenn man das haben möchte. Als root auf dem Server anmelden, ``cd greenlight``, dort ``docker exec greenlight-v2 bundle exec rake user:create["Lokaler Admin","admin@bbb.local","SUOERGEHEIMESPASSWORT","admin"]``
* Das Secret fürs Moodle Plugin bekommt man mit ``bbb-conf --secret``
