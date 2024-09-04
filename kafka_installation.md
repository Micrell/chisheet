**Next:** [[kafka_first_run]]
# VM installation

- Hyperviser: Parallels (MacOs arm64)
- OS: Debian 12 (https://cdimage.debian.org/debian-cd/current/arm64/iso-cd/debian-12.1.0-arm64-netinst.iso)
- Classic installation
- No graphic interface
- SSH server

# VM setup

- See [[debian]] for basic configuration
- Add NAT with Parallels, go to the network settings of the VM. Go to advanced settings and add a redirection from the port you want (2223 is fine) to the port 22 of the VM.

**We will use a ssh connexion to the VM with the MAC.** So we can keep the advantages of our terminal configuration (Zsh, Tmux ...) 
# Kafka installation

- Java 8+ must be installed on the server. We will install the latest version:
```sh
sudo apt update && sudo apt install default-jre default-jdk
```

- Download Kafka
```sh
cd
curl https://dlcdn.apache.org/kafka/3.5.0/kafka_2.13-3.5.0.tgz --output kafka_2.13-3.5.0.tgz
tar -xzf kafka_2.13-3.5.0.tgz
cd kafka_2.13-3.5.0
```


