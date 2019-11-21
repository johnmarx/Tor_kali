# Tor_kali

## Comment se rendre totalement annonyme. 

Mise en place d'une infra sur une vm distante d'un provider assurant l'anonyma du client. Cette vm est composé de vpn et d'un container Kali. L'utilisateur se connecte par un service Tor sur au container kali assurant ainsi son anonyma complet. 

Les vpn on une configuration gérer par ansible et donc leurs nombre dépend uniquement des capacité de l'hôte. Si l'ip d'un vpn est bloqué, on passe automatiquement sur l'autre vpn. De même si une ip deviens connu et ciblé. 
On assure ansi une continuité de service ainsi que l'anonyma de l'utilisateur.

## description

L'utilisateur utilise un client tor pour passer par le réseaux tor grâce à une clé.
Les services vpn sur la machine distante sont déployer avec ansible, le container Kali aussi. Il est configurer et mis à jour automatiquement. 


![](https://i.imgur.com/fYQSteT.png)


Participants: Yannick COURRIAN, Elie BEN AYOUN, John MARX. 
