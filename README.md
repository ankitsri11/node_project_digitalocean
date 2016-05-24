SnapCI sample nodejs project deployment to DigitalOcean:

Prerequisites:

On DigitalOcean droplet-
apt-get install node
apt-get install nodejs-legacy
apt-get update
apt-get install npm
npm install -g pm2

Commands to be run on SnapCI -
chmod +x ./hello.js
nohup node hello.js &
sleep 20
curl http://localhost:8080
scp hello.js deploy_user@droplet_ip:/home/deploy_user/node_project/
ssh deploy_user@droplet_ip 'pm2 start /home/deploy_user/node_project/hello.js'
