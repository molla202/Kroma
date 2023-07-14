<div align="center">
  <h1>KROMA REHBER </h1>
</div>

![kroma-og](https://github.com/molla202/Kroma/assets/91562185/61044d01-0239-400c-b0f8-4a7f78679f43)


 * [Topluluk kanalımız](https://t.me/corenodechat)<br>
 * [Topluluk Twitter](https://twitter.com/corenodeHQ)<br>
 * [Kroma Website](https://kroma.network/)<br>
 * [Discord](https://discord.gg/qvVNbgmK)<br>
 * [Twitter](https://twitter.com/kroma_network)<br>


## Sistem Gereksinimleri
| Bileşenler | Minimum Gereksinimler | 
| ------------ | ------------ |
| CPU |	2 |
| RAM	| 4+ GB |
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
not:( KROMA_VALIDATOR__HD_PATH="m/44'/60'/0'/0" ) metemask cüzdna olsuturuyoruz yada boş ama içinde sepholia mal bulunan cüzdanda olur çünkü private keyini alıp yazıcaz ona göre. kalan kısım aynı şekilde eksikleri tamamlayınız
çıkmak için    :wq yazıyoruz.enterla

![image](https://github.com/molla202/Kroma/assets/91562185/ad4dff0b-de1f-4023-af3c-038f77e09af6)

## node baslatıyoruz ( sadece node kuracaksanız bunu kurun validatorse atlayın validatore çalıştırdıysanız docker compose --profile vanilla down -v)
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
not öncelikle düzeltme yapmamız lazım bir dosyada  krome node kısmında bir user: root eklıyoruz yetki verme mevzusu sona ctrl+x y enterla kaydedip cıkıyoruz
```
nano docker-compose.yml
```

![image](https://github.com/molla202/Kroma/assets/91562185/f3d8e2a1-e7e4-493f-b119-08e07abc71b6)
```
docker compose --profile validator up -d
```

## Deposit validator
not: bize sepholia eth lazım en az 0.1 denmiş deposit işlemi için. aşağıdaki tam 0.1 için

```
docker exec kroma-validator kroma-validator deposit --amount 100000000000000000
```
## Logları kontrol ediyoruz...
```
docker logs -f kroma-node
```

```
docker logs -f kroma-validator
```






