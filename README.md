# Lovelace Swipe Navigation

[![hacs_badge](https://img.shields.io/badge/HACS-Default-yellow.svg)](https://github.com/custom-components/hacs) [![hacs_badge](https://img.shields.io/badge/Buy-Me%20a%20Coffee-critical)](https://www.buymeacoffee.com/FgwNR2l)

Parcourez les vues de Lovelace sur le mobile.

# Features:
* Balayage animé des vues Lovelace.
* Configurer les vues à ignorer.
* Définir la longueur de balayage nécessaire.
* Option pour désactiver les actions de balayage par défaut des navigateurs.
* Possibilité de passer de la première à la dernière vue et vice versa.
* Supporte les langues RTL.

# Installation:
Ne suivez qu'une seule de ces méthodes d'installation

<details>
  <summary><b>Installation et suivi avec HACS :</b></summary>

1. Dans "Frontend", cliquez sur le plus en bas à droite, recherchez "swipe navigation" et installez.

2. Rafraîchissez la page Lovelace, vous devrez peut-être vider le cache.
</details>

<details>
  <summary><b>Manual installation:</b></summary>
  
1. Copié [swipe-navigation.js](https://github.com/maykar/lovelace-swipe-navigation/releases/latest) de la dernière version dans `/www/lovelace-swipe-navigation/`

2. Ajoutez la ressource dans `ui-lovelace.yaml` ou dans Lovelace Resources.

```yaml
resources:
  # augmenter ce numéro de version à la fin de l'URL après chaque mise à jour
  - url: /local/lovelace-swipe-navigation/swipe-navigation.js?v=1.0.0
    type: module
```

3. Rafraîchissez la page, vous devrez peut-être vider le cache.
</details>

# Config:

Mark Watt fait un excellent travail sur la configuration [dans cette vidéo youtube].(https://www.youtube.com/watch?v=03IPN9lBEfE&t=663s).

* La configuration se fait à la racine de votre configuration lovelace.
* Si vous voulez simplement utiliser les valeurs par défaut de la configuration, vous n'avez pas besoin d'ajouter une configuration du tout.

**Config Options:**<br>

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| swipe_amount | number | 15 | Pourcentage minimum de l'écran devant être balayé pour naviguer.
| skip_tabs | string | | Une liste de vues, séparées par des virgules, à ignorer lors du passage de la souris. e.g., `1,3,5`.
| skip_hidden | boolean | true | Ignore automatiquement les onglets cachés.
| wrap | boolean | true | Enveloppe du premier onglet au dernier onglet et vice versa.
| prevent_default | boolean | false | Empêche les actions de glissement horizontal par défaut des navigateurs. Il peut être nécessaire de rafraîchir le navigateur pour qu'il prenne effet. Si vous utilisez une application compagnon HA, vous pouvez fermer l'application et la rouvrir.
| animate | string |  | Animations de balayage. Peut être : `swipe`, `fade`, `flip`. L'animation de balayage doit être considérée comme expérimentale et, selon votre configuration, elle peut être boguée.

**Exemple:**<br>
Ne vous contentez pas de copier l'exemple, il ne répondra pas à vos besoins. Construisez le vôtre en utilisant les options de configuration ci-dessus.
```yaml
swipe_nav:
  wrap: false
  animate: swipe
  skip_tabs: 5,6,7,8
  prevent_default: true
  swipe_amount: 30
  
views:
```

# Merci.
Un grand merci à :
* [@themoffatt](https://github.com/themoffatt) pour m'avoir devancé et m'avoir permis de faire un projet en double.
* [@RomRider](https://github.com/RomRider) et sa [decluttering-card](https://github.com/custom-cards/decluttering-card/) pour la méthode de configuration.
