# Collect data from Linky

Disclaimer, because Linky is a 100% French device, i've decided to write these words in 🇫🇷.

Il existe de nombreuses manières de récupérer ses données de consommation electrique. En fonction de votre niveau de chance ainsi que de vos aptitudes, il va être possible d'avoir une collecte plus ou moins précise.

Commonçons par le pire.

## Vous ne savez pas où se trouve votre compteur électrique

Il se peut que vous habitiez dans un logement qui ne vous donne pas accès à votre compteur. Pire, vous êtes infichu de savoir qui vous fourni votre electricité.

Dans un premier temps, il vous faudra vous créer un compte sur le site de [Enedis](https://enedis.fr)

Il y a de fortes chances que vous soyez obligé de vous rapprocher de votre compteur pour connaitre son "PDL" (qu'on peut toutefois retrouver sur les factures).

Une fois l'inscription effectuée et les autorisations de collecte acceptées, vous devriez pouvoir visualiser votre consommation journalière et même par heure !

## Vous avez un fournisseur d'électricité "2.0"

Dans ce cas là, il est surement possible de donner votre concentement à la collecte des informations Enedis par votre fournisseur d'électricité. Ainsi, vous pourrez avoir la même granularité d'information que ci-dessus mais depuis l'application de votre fournisseur.

## Vous voulez récupérer vos données via API

https://enedisgateway.tech/ est un site qui se propose de devenir l'intermediaire entre Enedis et votre système "maison". Via votre compte Enedis, vous pourrez récupérer vos données via un simple appel API. 👍

## Vous avez accès à votre compteur 🥳

Si vous avez un accès direct à votre compteur, vous avez de la chance 😉. Il est possible de se brancher dessus pour récupérer les données en temps réel. Tout passe par ce qu'on appel le module "ERL". L'accès à l'information est particulièrement aisée, néanmoins il peut y avoir quelques difficultés techniques à relever.

**La plupart des solutions fonctionne via le Wifi mais surtout nécessite une prise de courant pour alimentation.**

En effet, le courant d'alimentation proposé par le compteur Linky est bien trop faible pour beaucoup de solutions.

Néanmoins, l'appareil [LiXee ZLinky](https://zigbee.blakadder.com/LiXee_Zlinky_TIC.html) fonctionne de manière autonome via le protocole Zigbee.

Il existe aussi l'appareil [eeSmart D2L Wifi](http://eesmart.fr/modulesd2l/erl-wifi-compteur-linky/) qui fonctionne de manière autonome mais difficile de savoir si les données sont exploitables via un système maison.

Enfin, il y a [la clé "Atome"](https://www.totalenergies.fr/particuliers/nos-services/mieux-consommer/consolive) qui doit se décliner chez tout fournisseur d'énergie qui se respecte 😉

## En mode "do it yourself"

Niveau solution "maison".. on trouve des trucs vraiment prometteurs (mais attention, il faudra ET capter du Wifi au niveau du compteur ET avoir une source de courant).

- [à monter soi-même](https://faire-ca-soi-meme.fr/domotique/2016/09/12/module-teleinformation-tic/)
- [TeleInfoKit](https://342apps.net/home/)
- [WiFiTic](https://www.cartelectronic.fr/home/136-wifitic-3760313520066.html)
- [LinkyLink](https://blog.thestaticturtle.fr/linkylink-connecting-myself-to-the-energy-meter/)

Pour ma part, je me suis bien moins embêté et j'ai tout misé sur un Raspberry Pi Zero sur lequel je fais tourner un script Python au doux nom de [Linkiki](https://github.com/sylvek/linkiki).

Pour me raccorder au compteur Linky, j'utilise un module [PiTinfo v1.2](http://hallard.me/pitinfov12-light/).

Voici un très bel [exemple de ce qui ressemble le plus à mon installation](https://www.jonathandupre.fr/articles/24-logiciel-scripts/208-suivi-consommation-electrique-compteur-edf-linky-avec-raspberry-pi-zero-w/). (ou [encore](https://www.journaldulapin.com/2016/02/25/raspberry-pi-teleinfo/))
