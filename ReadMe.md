Instructions

1. Create Drone Server.

- see .drone playbook
- ansible version 2.15.0
- Install do collection
  - ansible-galaxy collection install community.digitalocean
- Run playbook
  - ansible-playbook -v -i do_hosts.yml drone-server.yml

2. Create/Edit drone.yml in repository if necessary.

3. Launch drone and add this repository from Github.

4. Add private and public key as secrets in via drone cli.
   - install drone cli
   - export drone environment vars:
     - export DRONE_SERVER=https://drone.tira.com.ro
       export DRONE_TOKEN=xxxxxxx
       drone info
   - add secrets (private + public key)
     - drone secret add --repository dantira/drone-test --name do_public_key --data @/home/user/.ssh/keys/key.pub

5. Add secrets for ansible step via Dashboard.
   - ansible_extra_vars -> digital_ocean-token=xxxx

6. Run Build.


