# SDN-Forensics-IDS
Implemented SDN IDS using Ryu controller.

1. Run the following commands on the controller:
cd /home/ubuntu/ryu && ./bin/ryu-manager --ofp-tcp-listen-port 6633 ryu/app/cont1.py (Domain A)
cd /home/ubuntu/ryu && ./bin/ryu-manager --ofp-tcp-listen-port 6634 ryu/app/cont2.py (Domain B)

2. Run custom topology:
sudo python <topology_name>.py

3. Start inter domain attack:
BBh1 hping3 --flood --udp AAh1 &
BBh1 hping3 --flood --udp AAh2 &
BAh1 hping3 --flood --udp AAh1 &
BAh1 hping3 --flood --udp AAh2 & etc.

4. Start intra domain attack:
ABh1 hping3 --flood --udp AAh1 &
ABh1 hping3 --flood --udp AAh2 &
ABh2 hping3 --flood --udp AAh1 &
ABh2 hping3 --flood --udp AAh2 & etc.
