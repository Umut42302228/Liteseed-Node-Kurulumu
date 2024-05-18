# Liteseed-Node-Kurulumu


## Kurulum:
```console
# güncelleme
sudo apt update -y && sudo apt upgrade -y
sudo apt install docker.io -y

git clone https://github.com/liteseed/edge

cd ./edge
docker build -t edge .

sudo docker volume create liteseed

#key oluşturacağız
docker run -v liteseed:/data edge generate
docker run -v liteseed:/data edge migrate

screen -S liteseed
docker run -v liteseed:/data edge start
# akabinde ctrl a d ile çıkalım.

# bu komutla cüzdan adresimizi öğrenip test tokeni isteyelim
docker run -v liteseed:/data edge balance
# cüzdan adresini hello@liteseed.xyz mail adresıne göndererek token isiyoruz.
```

> Token geldikten sonra devam edilecek.


```console
# Burada tırnakların içersinde bir github veya twitter bağlantını koy.
docker run -v liteseed:/data edge stake -u "https://ruesandora.com"

# bu sefer bu komutu girdiğinizde token elinizde kalmayacak ve stake kısmı Yes olacaktır.
docker run -v liteseed:/data edge balance

# screen içersine girip durdurup tekrar başlatalım.
screen -r liteseed
docker run -v liteseed:/data edge start
```


```console
cd /var/lib/docker/volumes/liteseed/_data
cat signer.json
# bu komut ile private keyinizi yedekleyebilirsiniz.
```

