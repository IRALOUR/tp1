## **TP1** -Claire Iralour
 ## 1. Affichage des infos des cartes réseau de mon PC: 
 ## En graphique (GUI : Graphical User Interface) 
 **Interface wifi** 
 Nom: wlo1 
 Adresse Mac: 90:78:41:45:49:12 
 Adresse IP: 10.33.1.160 

**Interface Ethernet** 
Nom: enp3s0 Adresse 
Mac: 00:d8:61:84:47:f6 
Adresse IP: 10.33.1.160 

**Gateway** 
Adresse IP: 10.33.3.253 

## **En graphique (GUI : Graphical User Interface)** 
**Afficher les informations sur une carte IP**
 Méthode: Settings 
 Nom: WIFI@YNOV Adresse
  Mac: 90:78:41:45:49:12 
  Adresse IP: 10.33.1.160

 **Question**
  Le gateway d'Ynov est un dispositif qui permet de relier un réseau local et le réseau Internet. 
## **2.Modifications des informations** 

## A. Modification d'adresse IP (part 1) ![[https://i.imgur.com/qayCDXX.png](https://i.imgur.com/qayCDXX.png)](https://i.imgur.com/qayCDXX.png](https://i.imgur.com/qayCDXX.png) "https://i.imgur.com/qayCDXX.png](https://i.imgur.com/qayCDXX.png)")  
Si la connexion au réseau est perdue c'est dû au fait qu'en changeant l'adresse Ip on peut avoir mis une adresse Ip déjà utilisée et qui n'est donc pas valide. ## B. NMAP $ nmap -sP 10.33.0.0/22 Starting Nmap 7.80 ( [https://nmap.org/](https://nmap.org/ "https://nmap.org/") ) at 2020-01-16 17:38 CET Nmap scan report for 10.33.0.11 Host is up (0.0065s latency). Nmap scan report for 10.33.0.15 Host is up (0.036s latency). Nmap scan report for 10.33.0.16 Host is up (0.95s latency). Nmap scan report for 10.33.0.35 Host is up (0.017s latency) Nmap done: 1024 IP addresses (115 hosts up) scanned in 65.94 seconds

[![](https://images-ext-1.discordapp.net/external/rxj4mp9lhktcW9JchD4gc0kdfLYthNCptK0GnLN6bGM/https/i.imgur.com/qayCDXX.png?width=331&height=300)](https://i.imgur.com/qayCDXX.png)

# II. Exploration locale en duo

### [](https://github.com/Deytron/monrepo/blob/master/Rendu%20TP1.md#3-modification-dadresse-ip)3. Modification d’adresse IP

Les adresses choisies auront été 192.168.1.1 et 192.168.1.2.

[![](https://camo.githubusercontent.com/92ef8b777b40b075185ebdda641abe51803d7b6b/68747470733a2f2f692e696d6775722e636f6d2f624646796e71372e706e67)](https://camo.githubusercontent.com/92ef8b777b40b075185ebdda641abe51803d7b6b/68747470733a2f2f692e696d6775722e636f6d2f624646796e71372e706e67)

Les deux machines se ping bien  
[![](https://camo.githubusercontent.com/fc8476af73323c9f917247b76cbd53b4e2cd5e4e/68747470733a2f2f692e696d6775722e636f6d2f614c4a6c7237652e6a7067)](https://camo.githubusercontent.com/fc8476af73323c9f917247b76cbd53b4e2cd5e4e/68747470733a2f2f692e696d6775722e636f6d2f614c4a6c7237652e6a7067)

### [](https://github.com/Deytron/monrepo/blob/master/Rendu%20TP1.md#4-utilisation-dun-des-deux-comme-gateway)4. Utilisation d’un des deux comme gateway

Impossible de partager la connexion du PC avec Wifi au PC sans Wifi. Sous Windows, à chaque fois que j’active le partage, le réseau Wifi ne fonctionne plus (réseau non identifié). Dès que le partage est désactivé, Internet fonctionne.

### [](https://github.com/Deytron/monrepo/blob/master/Rendu%20TP1.md#5petit-chat-priv%C3%A9)5.Petit chat privé

Après paramétrage, tout fonctionne dans les deux sens  
[![](https://camo.githubusercontent.com/6fa4987bf2c25de743047c45c9e36d0d906a3c0c/68747470733a2f2f692e696d6775722e636f6d2f427852594b5a6c2e706e67)](https://camo.githubusercontent.com/6fa4987bf2c25de743047c45c9e36d0d906a3c0c/68747470733a2f2f692e696d6775722e636f6d2f427852594b5a6c2e706e67)

### [](https://github.com/Deytron/monrepo/blob/master/Rendu%20TP1.md#6-wireshark)6. Wireshark

Résultats ping dans Wireshark :  
[![](https://camo.githubusercontent.com/c3ed65e04c6445b8aceb10becb5ed1fe43a18cf8/68747470733a2f2f692e696d6775722e636f6d2f335263334d63752e706e67)](https://camo.githubusercontent.com/c3ed65e04c6445b8aceb10becb5ed1fe43a18cf8/68747470733a2f2f692e696d6775722e636f6d2f335263334d63752e706e67)

Résultats netcat dans Wireshark avec quelques messages envoyés :  
[![](https://camo.githubusercontent.com/e0c27766b4894dd1e560e88584dec59d0ed5cdce/68747470733a2f2f692e696d6775722e636f6d2f717667646e654e2e706e67)](https://camo.githubusercontent.com/e0c27766b4894dd1e560e88584dec59d0ed5cdce/68747470733a2f2f692e696d6775722e636f6d2f717667646e654e2e706e67)

### [](https://github.com/Deytron/monrepo/blob/master/Rendu%20TP1.md#7-firewall)7. Firewall

#### [](https://github.com/Deytron/monrepo/blob/master/Rendu%20TP1.md#pour-autoriser-les-ping)Pour autoriser les ping

On part dans les paramètres du pare-feu Windows pour ajouter une règle de connexion entrante.  
Dans les options on sélectionne : Personnalisée > Tous les programmes  
Type de protocole : ICMPv4 (Requêtes d’écho)  
Sélectionner les adresses IP autorisées (toutes ou aucunes)  
Sélectionner les domaines  
Mettre un nom et une description  
Boum les pings rentrent  
Répéter sur le second ordinateur si l’on veut que les ping fonctionnent dans les deux sens

#### [](https://github.com/Deytron/monrepo/blob/master/Rendu%20TP1.md#pour-autoriser-netcat)Pour autoriser netcat

Même chose, on ajoute une règle de trafic entrant dans le firewall  
Dans les options on sélectionne : Port > Tous les programmes  
TCP ou UDP (peu importe)  
Ports locaux spécifiques : on en choisit un (ici 1337)  
Autoriser la connexion  
Choisir les domaines  
Bang netcat fonctionne si le port sélectionné dans le cmd est le port autorisé dans le firewall  
[![](https://camo.githubusercontent.com/1a3e8dc6ef2809cc0bddafcbd5b400f8ff5d7f83/68747470733a2f2f692e696d6775722e636f6d2f6335484a6362652e706e67)](https://camo.githubusercontent.com/1a3e8dc6ef2809cc0bddafcbd5b400f8ff5d7f83/68747470733a2f2f692e696d6775722e636f6d2f6335484a6362652e706e67)