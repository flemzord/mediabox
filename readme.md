# MediaBox 
[![Build Status](https://travis-ci.org/flemzord/mediabox.svg?branch=master)](https://travis-ci.org/flemzord/mediabox) 

## Requirements

- Debian 9 or Ubuntu 18.04 target system
- Python
- Sudo
- Ansible


## HOW TO 


0) Clone the repository   

```git clone https://github.com/flemzord/mediabox.git```

1) Copy the file containing the variables and adapt it to your needs

```cp vars.yml.dist vars.yml && nano vars.yml```

2) Launch the ansible playbook against the server that will host MediaBox  

```ansible-playbook play.yml -i "MY_IP,"```

3) Your MediaBox is ready to go

### Config for plexdrive

The default behavior is to use the local storage of your server.
You can target a remote storage using PlexDrive if you need it:



1) Create your access key and your private key at https://rclone.org/drive/#making-your-own-client-id

2) Launch plexdrive and follow the built-in instructions  

```plexdrive mount -c /opt/plexdrive -o allow_other /mnt/plexdrive```

3) Disable the rclone service

```systemcl stop rclone && systemctl disable rclone```

3) Enable the rclone service

```systemctl enable plexdrive && systemcl start plexdrive```

4) Enjoy

## MISC
### Directory used

- /mnt/unionfs (use local (rw) and rclone (ro))    
- /mnt/local    
- /mnt/plexdrive
