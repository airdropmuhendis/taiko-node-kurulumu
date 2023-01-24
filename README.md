<h1 align="center"> Taiko Node Kurulumu

```
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```
```
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg > /dev/null

```
```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
```
sudo apt-get update

```
```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

```
```
sudo docker run hello-world

```
```
git clone https://github.com/taikoxyz/simple-taiko-node.git
cd simple-taiko-node
```
```
cp .env.sample .env

```
```
docker compose up -d

```
```
ENABLE_PROPOSER=true
L1_PROPOSER_PRIVATE_KEY=(private keys from L1 network with balance)
L2_SUGGESTED_FEE_RECIPIENT=(address to which transfer fee will fall, L2 network)
```
```
docker compose up -d

```
```
docker compose logs -f
```
