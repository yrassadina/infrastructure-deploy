# infrastructure-deploy

Propose of project -> TBD


## Table of analyzed and used software

<table class="tg">
  <tr>
    <th class="tg-0pky">Domain</th>
    <th class="tg-0pky">Product</th>
    <th class="tg-0pky">Pros&amp;Cons</th>
    <th class="tg-0pky">Comment</th>
  </tr>
  <tr>
    <td class="tg-0pky" rowspan="4">CI</td>
    <td class="tg-fymr">Buildbot</td>
    <td class="tg-0pky">+More freedom and ower<br>+No UI to configure<br>-Higher costs at the start<br>-No sub-service to collect artifacts</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">TeamCity</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">Jenkins</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">Travis CI</td>
    <td class="tg-0pky">+Free for Open Source<br>+Is a service<br>-Only for Github</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky" rowspan="4">Virtualization</td>
    <td class="tg-fymr">QEMU</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">Docker</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">VMWare</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">?</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky" rowspan="2">Provisioning<br>(?)</td>
    <td class="tg-fymr">Ansible</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">?</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky" rowspan="4">"Fontend"<br>(repository,<br>issues tracker,<br>communication,<br>review,<br>collaboration)</td>
    <td class="tg-fymr">GitHub</td>
    <td class="tg-0pky">+Standart de-facto</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">Gitlab</td>
    <td class="tg-0pky">+More features as in Github</td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">Gerrit + Jira</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">?</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky" rowspan="2">Web Server</td>
    <td class="tg-fymr">nginx</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky">Will be used for artifacts sharing</td>
  </tr>
  <tr>
    <td class="tg-0pky">Apache</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky" rowspan="2">Monitoring</td>
    <td class="tg-fymr">Zabbix</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">?</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">Build System</td>
    <td class="tg-0pky">?</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky" rowspan="3">Test System</td>
    <td class="tg-fymr">Robot Framework</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0pky">Self-written ?</td>
    <td class="tg-0pky"></td>
    <td class="tg-0pky"></td>
  </tr>
  <tr>
    <td class="tg-0lax">?</td>
    <td class="tg-0lax"></td>
    <td class="tg-0lax"></td>
  </tr>
</table>





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
