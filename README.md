<h1 align="center"> Taiko Node Kurulumu


![image](![image](![image](https://user-images.githubusercontent.com/113446368/214262400-05448dd5-e457-478f-aa41-786d160eca33.png))


## Aleo, tamamen özel uygulamalar sunan ilk platformdur. Aleo'nun amacı, web üzerinde özel uygulamalar oluşturmak, dağıtmak ve çalıştırmak için sağlam destek sunacak merkezi olmayan, açık kaynaklı bir ağ oluşturmaktır. Aleo'da özel uygulamaları kolay bir şekilde yazmak için Leo adında bir programlama dili geliştiriyorlar.

## Video [Linki](https://youtu.be/Gh8dX0xfA0g) 

## Bu rehberde sizlerle beraber Aleonun ödüllü olan Testnet 3 adımına katılacağız. Ödül için 25 milyon Aleo kredisi ayırılmış. Prover yanı burdaki kısım ödülün %30 veya 7,5 milyon krediye karşılık gelir. detaylara [burdan](https://www.aleo.org/post/testnet-3-incentives-kickoff) ulaşabilirsiniz.

## Bu testnette garanti ödül yok yani katılan herkes ödül kazanmayacak ve sistem gereksinimleri çok yüksek olduğu için kurup kurmamak sizin kararınız. ödüller minning benzeri bir sistem olan kredi kazanma üzerine odaklanmış yani sisteminiz çok iyi olmalı. blok yakaladıkça kredi kazanırsınız bu krediler karşılığında ödül dağıtımı olacak.

Sistem Gereksinimleri:

- CPU: 16-cores (32-cores önerilen)
- RAM: 16GB (32GB önerilen)
- HDD: 128GB 
- Network: 10 Mbps

## Sunucuyu nerden nasıl alacağınızı bilmiyorsanız node eğitim serimizi izleyebilirsiniz. [Node Eğitim Serisi](https://www.youtube.com/playlist?list=PLKxGUfdcj7MVXls2OvTpwx6CnpVJN685w)


  ## Root yetkisi almak için aşağğıdaki kodu giriyoruz bazı sunucularda bunu sürekli girmemiz gerekiyor. eğer bunu girmezseniz yazdığınız kodun başına sudo komutunu yazarkata devam edebilirsiniz ancak karışıklık olmaması için aşğıdaki komutu yazmanızı tavsiye ederim. ( root: Windows cihazlarda olduğu gibi yönetici olarak çalıştırmamıza, yani bize yetki veren bir komuttur.)
  ```
  sudo su
  cd
  ```
## Aşşağıdaki komutlarla sunucumuzdaki güncellemeleri, yükseltmeleri kontrol ediyoruz, sondaki -y işareti gelen onay işlemlerini otamatik olarak onaylanmasını sağlayacaktır. kısaca kurulum için sunucumuzu hazır hale getiriyoruz.


```
sudo apt update && sudo apt upgrade -y
```
```
 sudo apt install pkg-config curl git build-essential libssl-dev
 ```
 screen kur
```
sudo apt install screen -y
```
 Rust kuruyoruz.
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
```
```
source $HOME/.cargo/env
```

Port ekleme
```
apt install ufw -y 
ufw allow ssh 
ufw allow https 
ufw allow http 
ufw allow 4133
ufw allow 3033
ufw enable
```

Kurulum
```

git clone https://github.com/AleoHQ/snarkOS.git --depth 1
```
```

cd snarkOS
```
```

./build_ubuntu.sh
```
```

cargo install --path .
```
```

screen -S client
```
```

./run-client.sh
```
ctrl + A + D tuşlarıyla screenden çıkıyoruz.
cüzdan oluşturma size vereceği bilgileri kaydedin
```
snarkos account new
```
```
screen -S prover 
```
alttaki komuttan sonra sizden private key isteyecek az önce kaydettiğimiz bilgiler arasında private key bulunuyor onu yapıştırın.
```
./run-prover.sh
```
ctrl + A + D tuşlarıyla screenden çıkıyoruz.

Nodenuz çalışmaya başladıktan sonra [burdan](https://www.aleo.network/) cüzdan adresinizi aratarak kredilerinizi görebilirsiniz.


