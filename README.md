# infrastructure-deploy

Propose of project -> TBD


## On Ubuntu 18.04
- Install host OS manually on your machine
```
sudo apt-get install openssh-server mc net-tools nginx
sudo apt install python3-pip

sudo nano /etc/nginx/nginx.conf
service nginx restart

# Add new user
sudo adduser infra-deploy #without adding to sudoers
users #check list of users
```

## On virtual machines
```
# Buildbot packages
# On master
sudo pip3 install buildbot==1.4 buildbot-console-view==1.4 buildbot-www==1.4

# On worker
sudo pip3 install buildbot-worker==1.4
sudo pip3 install gitpython==2.1.5 tenacity==4.5.0 txrequests txgithub service_identity
```
