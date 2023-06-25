# sui-testnet
for sui testnet
System Requirements
CPU	10 core
RAM	32GB
Storage	1TB SSD
OS	Ubuntu 20.04
----------------------------
sudo apt update && sudo apt upgrade -y

sudo apt install screen

screen -S sui

wget -O sui_testnet.sh https://api.nodes.guru/sui_testnet.sh && chmod +x sui_testnet.sh && ./sui_testnet.sh

***Check node

curl -s -X POST http://127.0.0.1:9000 -H 'Content-Type: application/json' -d '{ "jsonrpc":"2.0", "method":"rpc.discover","id":1}' | jq .result.info

****Check node logs

journalctl -u suid -f -o cat

***Delete node

sudo systemctl stop suid
sudo systemctl disable suid
rm -rf ~/sui /var/sui/ /usr/local/bin/sui*
rm /etc/systemd/system/suid.service
