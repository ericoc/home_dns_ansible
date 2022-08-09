## Quick Home DNS Ansible Example

This is just a quick example of an Ansible playbook and role that I can use to synchronize
changes on the two bind name servers running in my "home-lab".

Whenever I push changes to my private Git repository of zone files and named/bind configuration,
this playbook is automatically executed to synchronize the changes on each of my home name servers.

On Git pushes to the main branch of my `home.ericoc.com` DNS zone repository, a GitHub web-hook was set up to interact with
my Ansible Tower installation's API. I used the Ansible Tower API to automatically execute a "Job Template" to run this `home_dns.yaml`
playbook and role to safely test and synchronize any DNS changes on each of my home name servers in an automated way.

Additionally, while at Sidecar, my co-worker (Kyle) and I set up "chat-ops" using Ansible Tower, as well as RunDeck,
in order to perform deploys directly from Slack by saying something like "`/deploy sidecar`" in a special channel to
a `hubot` installation which my co-worker maintained. (un-related shout-out to [@kyleparisi](https://github.com/kyleparisi/) !) I maintained the Ansible Tower, as well as RunDeck, installations.

I was also co-creator of a small project called "[Zeromon](https://github.com/zeromonio/zeromon)" which was an Ansible project that deployed a fully working Zabbix installation on an AWS EC2 instance, or Digital Ocean droplet. While Kyle maintained the website and front-end/marketing, I used Ansible within the Zeromon playbook to install the Zabbix server and agent software as well as Apache, PHP, MySQL, Postfix SMTP server, and more.
