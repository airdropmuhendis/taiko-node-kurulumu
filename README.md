<h1 align="center"> Taiko Node Kurulumu

# Ödüllü bir node değil ancak proje güven veriyor isteyenler kurabilir.

## Sunucuyu nerden nasıl alacağınızı bilmiyorsanız node eğitim serimizi izleyebilirsiniz. [Node Eğitim Serisi](https://www.youtube.com/playlist?list=PLKxGUfdcj7MVXls2OvTpwx6CnpVJN685w)

Minimum sitem Gereksinimleri:
2 CPU
6 GB RAM
50 GB SSD

#ilk olarak yeni bir metamask cüzdan oluşturun çünkü sizden private key isteyecek private keyi cüzdanınızda hesap bilgileri kısmından görebilirsiniz.
Daha sonra taiko.xyz websistesine gidip bridge kullanarak Ethereum A1 ve Taiko A1 ağını ekleyin. ve her iki ağada faucetten token alın.


## Hazırlık

```
sudo apt-get update
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```
```
sudo apt install screen
```
Docker kurulumu farklı yöntemler kullanarakta kurabilirsiniz.
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
Docker Test etmek için bunu çalıştırın.
```
sudo docker run hello-world

```
```
git clone https://github.com/taikoxyz/simple-taiko-node.git
cd simple-taiko-node
```
```
screen -S Taiko
```
 Bu kısımda en alttaki kısmı aşağıdaki gibi olacak şekilde değiştirin detaya videodan ulaşabilirsiniz.
```
cp .env.sample .env
sudo nano .env

```
```
ENABLE_PROPOSER=true
L1_PROPOSER_PRIVATE_KEY= metamskten aldığınız private key
L2_SUGGESTED_FEE_RECIPIENT= cüzdan adresiniz
```
```
docker compose up -d
```
logları görmek için
```
docker compose logs -f
```
