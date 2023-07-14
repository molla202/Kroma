<div align="center">
  <h1>KROMA REHBER </h1>
</div>



 * [Topluluk kanalımız](https://t.me/corenodechat)<br>
 * [Topluluk Twitter](https://twitter.com/corenodeHQ)<br>
 * [CreditCoin Website](https://creditcoin.org/)<br>
 * [Discord](https://discord.com/invite/creditcoin)<br>
 * [Twitter](https://twitter.com/Creditcoin)<br>


## Sistem Gereksinimleri
| Bileşenler | Minimum Gereksinimler | 
| ------------ | ------------ |
| CPU |	4 |
| RAM	| 8 GB |
| Storage	| 250 GB SSD |

## Update edelim
```bash
sudo apt update; sudo apt upgrade 
```
## Docker kurulumu
```bash
sudo apt-get update && sudo apt install jq git && sudo apt install apt-transport-https ca-certificates curl software-properties-common -y && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - && sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" && sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin && sudo apt-get install docker-compose-plugin 
```
## Dosyaları çekiyoruz
```
git clone https://github.com/kroma-network/kroma-up.git && cd kroma-up
```
## kuruyoruz
```
./startup.sh
```
## env yapılandırması
```
vim .env
```
not: metemask cüzdna olsuturuyoruz yada boş ama içinde sepholia mal bulunan cüzdanda olur çünkü private keyini alıp yazıcaz ona göre. kalan kısım aynı şekilde eksikleri tamamlayınız
çıkmak için    :wq yazıyoruz.enterla

![image](https://github.com/molla202/Kroma/assets/91562185/ad4dff0b-de1f-4023-af3c-038f77e09af6)

## node baslatıyoruz
not öncelikle düzeltme yapmamız lazım bir dosyada  krome node kısmında bir user: root eklıyoruz yetki verme mevzusu sona ctrl+x y enterla kaydedip cıkıyoruz
```
nano docker-compose.yml
```

![image](https://github.com/molla202/Kroma/assets/91562185/f3d8e2a1-e7e4-493f-b119-08e07abc71b6)

```
docker compose --profile vanilla up -d
```
not: loga bakalım akıyormu
```
docker logs -f kroma-node
```

## validator başlatıyoruz
```
docker compose --profile validator up -d
```

## Deposit validator
```
docker compose exec kroma-validator kroma-validator deposit --amount <amount-wei> # must be set
```
## Logları kontrol ediyoruz...
```
docker logs -f kroma-node
```

```
docker logs -f kroma-validator
```






