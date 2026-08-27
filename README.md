# Digital Identity Protection V3

V3 ajoute une première couche de surveillance réelle depuis le navigateur :
- génération de variantes et homoglyphes ;
- requêtes RDAP via rdap.org lorsque le service et CORS le permettent ;
- interrogation Certificate Transparency via crt.sh lorsque disponible ;
- scoring et alertes ;
- export JSON ;
- profil sauvegardable localement ;
- emplacement prévu pour un proxy/backend Cloudflare Brand Protection.

## Architecture de production recommandée

Navigateur -> API/Worker sécurisé -> sources de veille -> stockage historique -> moteur de scoring -> alerting.

Ne jamais placer un token Cloudflare/API secret dans `index.html`.

Cloudflare Brand Protection fournit aujourd'hui des recherches de domaines et de logos, des matches, une API et des alertes. L'intégration production doit passer par un backend/worker et respecter les droits d'utilisation du service.

RDAP est le protocole standard de données d'enregistrement des gTLD, en remplacement de WHOIS.

Cette V3 reste un prototype : elle ne garantit pas une couverture exhaustive d'Internet et ne constitue pas une preuve juridique.
