# Taiko Node Kurulum Rehberi

<h1 align="center"> Merhaba Taiko Node Kurulum Rehberi <br> by Hercules</h1>

## [Bu rehber Herculess'ten alıntılanmıştır.](https://github.com/herculessx/Taiko-Testnet-Node)

## 🟢 Ön bilgi

Node kurabilmeniz için öncelikle Platform testnetini yapmanız gerekiyor. Platform testnetinde kullandığınız cüzdan adresini burada kullanacağız. Sistem 6060 port ile çalışıyor celestia gibi node kurduysanız çakışacaktır buna dikkat ediniz. <br>

Platform testneti ile ilgili Bilgi <br>

* [Platform Tesneti](https://twitter.com/Hercules4413/status/1608026986164748288)


### Explorer:
 * [Explorer](https://l2explorer.a1.taiko.xyz/)

 
 ### Linkler
 * [Hercules Telegram](https://t.me/HerculesNode)
 * [Hercules Twitter](https://twitter.com/Hercules4413)
 * [Taiko Dc](https://discord.gg/taikoxyz)
 
 ## 🟢 Sistem özellikleri

Minimum:
- CPU with 2+ cores
- 4GB RAM
- 500 Gb 


Önerilern:
- Fast CPU with 4+ cores
- 16GB+ RAM
- High-performance SSD with at least 1TB of free space


## 🟢 Sistem Güncelleme
```shell
sudo apt update
```

```shell
sudo apt upgrade
```

```shell
apt install docker-compose
```


## 🟢 Docker Setup
```shell

sudo apt-get update && sudo apt install jq && sudo apt install apt-transport-https ca-certificates curl software-properties-common -y && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - && sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" && sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin && sudo apt-get install docker-compose-plugin

```

```shell
chmod +x /usr/local/bin/docker-compose

```

## 🟢 1. Taiko dosyalarını indirin

```
git clone https://github.com/taikoxyz/simple-taiko-node.git
```

Screen Oluşturalım
```
screen -S taiko
```

taiko Klasörüne Giriş yapalım
```
cd simple-taiko-node
```

.env dosyası oluşturalım. Bu dosyayı oluşturduktan sonra Taiko platform testnetinde kullandığınız adresin Private keyini Tilki cüzdanınızdan alacaksınız ve .env dosyasına kaydedeceksiniz. 
```
cp .env.sample .env
```

.Env dosyasına girelim burada değiştirmeniz gereken en alttaki bölüm. <br>

```
nano .env
```

<br>

*ENABLE_PROPOSER=true  ( Falseden true çeviriyoruz ) <br>
*L1_PROPOSER_PRIVATE_KEY= Cüzdanımızın private keyini yazıyoruz <br>
*L2_SUGGESTED_FEE_RECIPIENT= Cüzdan adresimizi yazıyoruz. <br>
*ctrl + x Yes diyerek kaydediyoruz. <br>

<br>

![image](https://user-images.githubusercontent.com/101635385/210138160-c01d12f1-c1d1-40b5-96f0-ac907d3110cc.png)

<br>

Private Key nasıl alınır sağdaki 3 noktaya tıklayın --- >> ardından hesap bilgileri --- >> Özel anahtarı dışa aktar

![image](https://user-images.githubusercontent.com/101635385/210151390-4342cbb3-5c1c-4e35-96ff-fde422ac08bb.png)

<br>

![image](https://user-images.githubusercontent.com/101635385/210151407-a7b0aa7e-ae39-47cc-b1ab-2697e0d25edf.png)





## 🟢 Çalıştırma

Bu işlem sonrası kurulum yapacak ve senkronize olmaya başlayacaktır.

```
docker compose up
```

![image](https://user-images.githubusercontent.com/101635385/210138255-d7c31fb4-bbe4-4d6d-8703-6ee16f1a0b47.png)


## 🟢 Explorer üzerinden block görüntüleme 

Explorer üzerinden adresinizi yazın aşağıdaki resimdeki gibi ise sorun yok tabi önce senkronize olması gerekiyor. 

 * [Explorer](https://l2explorer.a1.taiko.xyz/)

![image](https://user-images.githubusercontent.com/101635385/210138905-3baea6ea-5424-4197-b4c4-0c23d9578247.png)


## 🟢 Log Görme

Eğer başta screen oluşturmadıysanız bir screeen oıluşturup logları görebilirsiniz.

```
cd simple-taiko-node
docker compose logs -f
```


## 🟢 Durdurma

Bu işlem sonrası kurulum yapacak ve senkronize olmaya başlayacaktır.

```
docker compose down
```

## 🟢 Nodeyi silme

Bu işlem sonrası kurulum yapacak ve senkronize olmaya başlayacaktır.

```
docker compose down -v
cd
rm -fr simple-taiko-node
```

Forklamayı ve beğenmeyi unutmayınız :)
