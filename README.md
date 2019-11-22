# Tor_kali

## Comment se rendre totalement annonyme. 

Mise en place d'une infra sur une vm distante d'un provider assurant l'anonyma du client. Cette vm est composé de vpn et d'un container Kali. L'utilisateur se connecte par un service Tor sur au container kali assurant ainsi son anonyma complet. 

Les vpn on une configuration gérer par ansible et donc leurs nombre dépend uniquement des capacité de l'hôte. Si l'ip d'un vpn est bloqué, on passe automatiquement sur l'autre vpn. De même si une ip deviens connu et ciblé. 
On assure ansi une continuité de service ainsi que l'anonyma de l'utilisateur.

## description

L'utilisateur utilise un client tor pour passer par le réseaux tor grâce à une clé.
Les services vpn sur la machine distante sont déployer avec ansible, le container Kali aussi. Il est configurer et mis à jour automatiquement. 


![](https://i.imgur.com/y9mev4t.png)

## Implantation logique 
### 1 serveur

Sur le serveur distant on install le service tor. Puis dans /etc/tor/ on configure le service. Nous voulons une connection ssh par tor. Donc: 
'hiddenService /var/lib/hidden_service 22 127.0.0.1:22 '
Puis on crée un syslink et on démarre le service.
On récupère ensuite l'adresse de notre relais ainsi que la clé privé. Enfin on desactive la connection ssh par mot de passe.

### 2 client
Pour le client, on install aussi le service tor, puis on configure les DNS sur le relais de notre serveur:
'    ProxyCommand nc -X 5 -x localhost:9050 <serveurrelaisaddr>.onion 22 configure le service ssh pour utilisé le service tor.
  
Participants: Yannick COURRIAN, Elie BEN AYOUN, John MARX. 
