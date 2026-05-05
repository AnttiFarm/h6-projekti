# H6-project, Simple web server

This ansible playbook installs nginx and caddy on a Debian or Ubuntu pc. It creates two users, nginx and caddyuser which hold the websites. These directories can be modified by anyone in the group "web". Nginx is on default port 80, caddy is on port 8080.

The playbook also installs ufw and fail2ban. Ufw is setup to block everything except ports 22,80,443 and 8080 on TCP.

<table>
  <tr>
    <td><img width="430" height="165" alt="2026-05-05 18_47_35" src="https://github.com/user-attachments/assets/e38fd280-8ff5-48f8-8a16-c2fe8e03d354" /></td>
    <td><img width="430" height="165" alt="2026-05-05 18_48_27" src="https://github.com/user-attachments/assets/91c29d68-a5cc-49b0-9e74-cf209400bdbf" /></td>
  </tr>
</table>

## Setup

1. Have ansible installed, and if cloning, git.

2. Clone this repo or download zip and unpack it.

3. Find where it was unpacked in terminal.

4. Configure hosts.ini if needed, comes with just localhost configured.

5. Run site.yml

6. Go to your favorite web browser and type in localhost(or whatever you configured). By default you'll be on the nginx sites. To go to caddy, change the port to 8080.

## Authors

Antti Färm & [snorh](https://github.com/snorhh/)
