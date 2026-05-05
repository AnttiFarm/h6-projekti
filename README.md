# H6-project, Simple web server

This ansible playbook installs both nginx and caddy. Nginx is on default port 80, caddy is on port 8080.

The playbook also installs ufw and fail2ban and configures them.

<table>
  <tr>
    <td><img width="430" height="165" alt="2026-05-05 18_47_35" src="https://github.com/user-attachments/assets/e38fd280-8ff5-48f8-8a16-c2fe8e03d354" /></td>
    <td><img width="430" height="165" alt="2026-05-05 18_48_27" src="https://github.com/user-attachments/assets/91c29d68-a5cc-49b0-9e74-cf209400bdbf" /></td>
  </tr>
</table>

## How it works

There are 3 roles: nginx, caddy and palomuuri(firewall). The roles create two users: nginx and caddyuser. These users get directories which have the webpages. A group called web is made, anyone in this group can modify the directories of nginx and caddyuser. 

Nginx and caddy do virtually the same things: 

- Install nginx and caddy
- Create a group called web
- Create a user with a directory for keeping website files(index.html)
- Users in web-group can modify these files
- Make sure our site file is in the nginx/caddy enabled sites

Palomuuri role installs ufw and fail2ban, and configures ufw to deny everything except ports 22,80,443 and 8080 on TCP.

<pre>
./
├── ansible.cfg
├── hosts.ini
├── LICENSE
├── README.md
├── roles/
│   ├── caddy/
│   │   ├── files/
│   │   │   ├── Caddyfile
│   │   │   └── index.html
│   │   ├── handlers/
│   │   │   └── main.yml
│   │   └── tasks/
│   │       └── main.yml
│   ├── nginx/
│   │   ├── files/
│   │   │   ├── index.html
│   │   │   └── publicsite
│   │   ├── handlers/
│   │   │   └── main.yml
│   │   └── tasks/
│   │       └── main.yml
│   └── palomuuri/
│       └── tasks/
│           └── main.yml
└── site.yml
</pre>

## Setup

1. Have ansible installed, and if cloning, git.

2. Clone this repo or download zip and unpack it.

3. Find where it was unpacked in terminal.

4. Configure hosts.ini if needed, comes with just localhost configured.

5. Run site.yml

6. Go to your favorite web browser and type in localhost(or whatever you configured). By default you'll be on the nginx sites. To go to caddy, change the port to 8080.

## Authors

Antti Färm & Sanna Noronen
