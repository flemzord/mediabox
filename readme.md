# MediaBox  

## How to start

MediaBox support only Debian 9, please install your server with debian 9. But it's possible use ubuntu 18.04.

0) Clone this repo    
```git clone https://github.com/flemzord/mediabox.git```
1) Copy vars files   
```cp vars.yml.dist vars.yml```
2) Update vars.yml
3) Launch ansible   
```ansible-playbook play.yml -i "MON_IP,"```
4) Your MediaBox is install
5) But use Google Drive storage, please config this

### Config for plexdrive

1) Create your own client id and client secret (see https://rclone.org/drive/#making-your-own-client-id).
2) Sample command line for plexdrive    
```plexdrive mount -c /opt/plexdrive -o allow_other /mnt/plexdrive```
3) Launch plexdrive    
```systemctl enable plexdrive && systemcl start plexdrive```
4) Enjoy


## Information
### Dirs

- /mnt/unionfs (use local (rw) and rclone (ro))    
- /mnt/local    
- /mnt/plexdrive