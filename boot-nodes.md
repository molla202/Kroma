
### Boot nodes değişikliği
```
sed -i.bak s/KROMA_GETH__BOOT_NODES=.*/KROMA_GETH__BOOT_NODES=enode://eb7d517a51f12d565c53fc3c2bd7d830951626403fd41ddcaa356a5a63aaf700a99856dea5f805ab52e956dbb09017c868af5c2503f0753d598449d0987d0867@p2p-0.sepolia.kroma.network:30304?discport=30303,enode://11a22dd7e0242395c0383679c046b6c37ed7bb085b5ef9229314219b6d56d676208a22ff33487e23bde4a4e2693c243ec38e18f385a5e9fcc89c01b907c65731@p2p-1.sepolia.kroma.network:30304?discport=30303/ $HOME/kroma-up/.env

sed -i.bak s/KROMA_NODE__BOOT_NODES=.*/KROMA_NODE__BOOT_NODES=enr:-J24QNScwSQ9xyCI9TuC4z55f1mUTH7UwwU6XrdRkXTry5okQDMDQVzeGXKGlCMGCjW09zZdGCLBppgx7I-IlyAHTL2GAYora1atgmlkgnY0gmlwhCvKZq2Hb3BzdGFja4O2EgCJc2VjcDI1NmsxoQI5RRcWthXDZBQIWy2V5f0F6vU5ULQ7Onz0J-jOwom-O4N0Y3CCIyuDdWRwgiMr,enr:-J24QOJ08WAtwmF8ZQf9xMYc1XNAheQYbWQmyDdsMJywUD1SLG6gfhGqgJp-wUgZTtIazd8WwUf9ziehfxF-grArB32GAYorbLu4gmlkgnY0gmlwhDRPliiHb3BzdGFja4O2EgCJc2VjcDI1NmsxoQJxu9bJv02qtIehfeOmtA8B_RWqZylpHOGOOBuWQo-xXoN0Y3CCIyuDdWRwgiMr/ $HOME/kroma-up/.env
```
```
cd $HOME/kroma-up/ && docker compose --profile validator restart
```
```
cd $HOME/kroma-up/ && docker compose --profile validator logs -f --since 1m
```
