# Programmation

## Bash

### En tête : 

Il est bien de commencer un script par le shebang:

```
#!/bin/bash
```

Les commentaires se font avec #. </br>
Il est recommander de mettre la date, la version, l'auteur, la description etc.

```bash
#!/bin/bash
############################
#
# Auteur : Jonathan Schlegel
#
# Date : 23/02/2023
#
# Version : 1.0
#
# Description: ce script permet d'afficher le #nom de l'utilisateur
#
# Utilisation: name utilisateur
#############################
```

### Boucle:

- While:
    ```bash
    while [ condition ];
    do
        commande
    done
    ```
    In-line: 
    
    ```bash
    while [ condition ]; do commande; done
    ```

- For:

    ```bash
    for variable in 1 2 3 4 5
    do
        commande
    done
    ```
    ```bash
    for variable in {1..5}
    do
        commande
    done
    ```
    ```bash
    for ((i=0,i<10,i++))
    do
        commande
    done
    ```
    In-line:
    
    ```bash
    for i in 1 2 3 4 5; do commande; done
    ```

### Condition:

```bash
    if [ test ]
    then
        commande
    elif
        commande
    else 
        commande
    fi    
```

### Test sur les entiers:

|   **Testeur**    |   **Signification** |
|------------------|---------------------|
|   -eq            |égal (equal)         |
|   -ne            |non égal (not equal) |
|   -gt            |plus grand que (greater than)|
|   -ge            |plus granq que ou égal (greater than or equal)|
|   -lt            |plus petit que (less than)|
|   -le            |plus petit que ou égal (less than or equal)|


### Test sur les fichiers:

|   **Testeur**    |   **Signification** |
|------------------|---------------------|
|   -e             |Le fichier existe    |
|   -s             |Le fichier à une taille supérieur à 0|
|   -z             |La variable est vide |
|   -f             |Le fichier existe(il est normal)|
|   -d             |Le répertoire existe |
|   -L             |Le fichier est un lien symbolique|

### Test chaîne de caractère:

|   **Testeur**    |   **Signification** |
|------------------|---------------------|
|   =              |les deux chaînes de caractère sont égales|
|   !=             |Les deux chaînes de caractères sont différentes|
|   <              |La première chaîne est inférieur à la seconde dans l'ordre alphabétique|
|   >              |La première chaîne est inférieur à la seconde dans l'ordre alphabétique|
|   -z             |La taille de la chaîne est nul|
|   -n             |La taille de la chaîne est non nul|

### Test condition:

|   **Testeur**    |   **Signification** |
|------------------|---------------------|
|   -o             |ET                   |
|   -a             |OU                   |

### Arguments:

|                  |                   |    
|------------------|---------------------|
|   $#             |Nombre d'arguments|
|   $*             |Tous les arguments en une variable|
|   $@             |Tous les arguments en un tableau|
|   shift          |Sélectionne le prochain argument|

### Calcul:

- variable=$((calcul))

### Résultat d'une commande dans une variable

- variable=$(commande)

## XML

|**Element**       |**Signification**    |
|------------------|---------------------|
|   .              |Element courant      |
|   ..             |Elementparent        |
|   /xxx/yyy       |Les éléments yyy enfants de l'élément xxx|
|   //yyy          |Toues les éléments yyy du document|
|   /xxx/yyy[z]    |Le z ième élément yyy|
|   /xxx/yyy/@zz   |Attribut zz de l'élément yyy|
|   /xxx/yyy[@zz='aa']|Element yyy dont l'attribut zz est égal à 'aa'|
|   /xxx/yyy[www>10]|Element yyy dont un enfant ww est supérieur à 10|


# OS


## Vi / Vim

Entrer en mode édition : a ou i <br>
Entrer en mode commande : echap

En mode commande:

|                  |                     |
|------------------|---------------------|
|   :q             |Quitter (quit)       |
|   :w             |Sauvegarder (word)   |
|   :!             |Forcer l'action      |
|   :x             |Supprimer            |

Les commandes récurrentes:


|                  |                     |
|------------------|---------------------|
|   :q!            |Quitter sans sauvegarder|
|   :wq            |Sauvergarder et quitter|


|                  |                     |
|------------------|---------------------|
|   :q             |Quitter (quit)       |
|   :w             |Sauvegarder (word)   |
|   :!             |Forcer l'action      |
|   :x             |Supprimer            |

|**Commande**      |**Utilisation**      |
|------------------|---------------------|
|   systemctl disable service|Ne s'active pas au démarrage|
|   systemctl enable service|S'active au démarrage|
|   systemctl stop service|Arrête le service|
|   systemctl start service|Démarre le service|
|   systemctl restart service|Redémarre le service|
|   systemctl reload service||
|   find       | |
|   cut||
|   grep||
|   sort||
|   chmod||
|   whereis||
|   which||
|   whatis||
|   ln||
|   less||
|   head||
|   tail||
|   lspci||
|   lshw||
|   lsusb ||
|   dmidecode||
|   lsblk||
|   fdisk||


# Service

## DNS


### Commande interroger DNS:

Avec host:

|**Commande**      |**Utilisation**      |
|------------------|---------------------|
|   host –t soa domaine|SOA du domaine   |
|   host –t ns domaine|DNS du domaine    |
|   host –t mx domaine|Mail-exchanger    |
|   host -t a FQDN|IP du DNS qui gère le FQDN|
|   host -t aaaa FQDN|IPV6 du DNS qui gère le FQDN|
|   host -t ptr IP.IP.IP.IP|FQDN de l'IP |
|   host -t txt FQDN|Fichier texte du FQDN|

Avec dig:

|**Commande**      |**Utilisation**      |
|------------------|---------------------|
|   dig domaine soa|SOA du domaine       |
|   dig domaine mx |Mail-exchanger       |
|    dig -x IP.IP.IP.IP|FQDN de l'IP     |


## Routeur

|**Commande**      |**Utilisation**      |
|------------------|---------------------|
|   enable         | Entrer en mode privilégié|
|   show running   | Affiche la configuration générale|
|   show ip ospf   | Affiche les informations relatives aux processus OSPF|
|   show ip ospf neighbor| Affiche les voisins OSPF|
|   show ip ospf database| Affiche les databases OSPF|
|   show crypto isakmp| Affiche| 
| show ip interfaces brief| Montre les interfaces et leurs états|
|   copy run start / wr | Ajoute la présente configuration au redémarrage|
|   configure terminal| Entrer en mode configuration|
|   no commande    | Annule la commande|
|   exit           | Revient plus haut dans l'arborescence|
|   interface nom_interface| Sélectionne l'interface|
|   passive-interface interface| N'envoie pas de paquet OSPF |
|   show ip protocol| |
|   show ip nat translation| Affichque la table des traductions|
|    encapsulation Dot1Q X| Ajoute d'une encapsulation pour le vlan X|
|   ip address @IP @masque| Ajoute une adresse IP|
|   ip access-list extended nom_regle|Créer, sélectionne une règle|
|   permit ip @IPsource wilcard @IPdestination ildcard| Autorise une adresse de communiquer avec une autre|
|   deny ip @IPsource wilcard @IPdestination ildcard| Interdire une adresse de communiquer avec une autre|
|   permit ip any any| Permet à toute les IP sources de communiquer avec toutes les IP destinations|
|   deny ip any any| Interdit à toute les IP sources de communiquer avec toutes les IP destinations|
|   ip access-group nom_regle in/out|Applique la règle sur une interface en entrée ou sortie|
|   ip nat outside| Indique l'interface de l'adresse publique pour traduction|
|   ip nat inside| Indique l'interface de l'adresse privé pour traduction|
|   ip nat inside source static @Privé @Publique||
|   router bgp as|  |
|   neighbor @ip remote-as numero| On déclare le voisin avec son ip et son AS| |
|   network @ip_reseau mask @mask| On déclare un réseau|

redistribute ospf processus metric nombre
redistribute bgp 100 subnets metric 3


## Switch

|**Commande**      |**Utilisation**      |
|------------------|---------------------|
|   enable         |Mode privilégié      |
|   configure terminal|Mode configuration|
|   show running   | Affiche la configuration générale|
|   show vlan      |Montre les vlan      |
|   interface nom_interface|Sélectionne l'interface|
|   no shut        |Allume l'interface   |
|   exit           |Sortir               |
|   vlan XXXX      |Créer/sélectionne vlan XXX|
|   no vlan XXXX   |Supprime le vlan XXXX|
|   name vlan nom_vlan|Nomme le vlan     |
|   switchport mode trunk/access|Configure l'interface en mode trunk ou access|
|   switchport access vlan XXX|Autorise le vlan XXX sur l'interface|

## OSPF

|**Commande**      |**Utilisation**      |
|------------------|---------------------|
|   enable         |Mode privilégié      |
|   configure terminal|Mode configuration|
|   interface nom_interface|Sélectionne l'interface|
|   no shut        |Allume l'interface   |
|   exit           |Sortir               |
|   vlan XXXX      |Créer/sélectionne vlan XXX|
|   name vlan nom_vlan|Nomme le vlan     |
|   switchport mode trunk/access|Configure l'interface en mode trunk ou access|
|   switchport access vlan XXX|Autorise le vlan XXX sur l'interface|

- network @IP Wildcard area nombre
- show ip ospf neighbor
- show ip ospf database
- show ip ospf interface
- show ip route ospf
- auto-cost reference bandwidth 1000
- router-id X.X.X.X
- clear ip ospf process
- ip multicast-routing
- ip point-to-point
- show ip interface brief
- redistribute


## RIP

Séquence de commande:

- routeur rip
- version nombre
- network IP.IP.IP.IP
- timer basic update invalid holddown flush

## Apache

### Paquet 

apache2

|**Commande**      |**Utilisation**      |
|------------------|---------------------|
|   apache2ctl -v version|Obtenir la version|
|   apache2ctl -t  |Tester la configuration|
|   apache2ctl -t -D DUMP_VHOSTS||
|   apache2ctl -S|Voir les hosts virtuels et leur configuration|

|**Dossier**       |**Description**      |
|------------------|---------------------|
|   sites-available|Fichier de configuration des sites disponibles|
|   sites-enabled  |Liens symboliques vers les configurations, dans site-available, des sites activés|
|   conf-available |Fichiers de configuration des autres services disponibles|
|   conf-enabled|Liens symboliquesvers les configurations, dans conf-available, des autres services activés|
|   mods-available |Fichiers de configuration des modules d'Apache disponibles|
|   mods-enabled   |Liens symboliques vers les configurations, dans mods-available, des modules activés|
|   /var/www/html  |Dossier où l'on place les fichiers html, css, php etc
 

## SSH

Paquets:

openssh-server, openssh-client

Pour se connecter au serveur:

ssh utilisateur@IP

Il est possible d'y ajouter en option -6 pour une adresse en ipv6 et -p pour utiliser un autre port.

scp
ssh-keygen -t ed25519 -C "email@example.com"
~/.ssh/id_xxxx
~/.ssh/authorized_keys
~/.ssh

## APIPA(Automatic Private Internet Protocol Adressing)

avahi-autoipd
avahi-daemon
avahi-discover

## DHCP

### Paquet 

isc-dhcp-server

### Fichier configuration:

/etc/dhcp/dhcpd.conf

dhclient

/var/lib/dhclient/dhclient.leases 