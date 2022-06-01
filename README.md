# Lovelace Swipe Navigation

[![hacs_badge](https://img.shields.io/badge/HACS-Default-yellow.svg)](https://github.com/custom-components/hacs) [![hacs_badge](https://img.shields.io/badge/Buy-Me%20a%20Coffee-critical)](https://www.buymeacoffee.com/FgwNR2l)

Swipe through Lovelace views on mobile.

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
  <summary><b>Installation and tracking with HACS:</b></summary>

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

Mark Watt does an excellent job covering configuation [in this youtube video](https://www.youtube.com/watch?v=03IPN9lBEfE&t=663s).

* Configuration is done in the root of your lovelace configuration.
* If you just want to use the default config values you don't need to add a config at all.

**Config Options:**<br>

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| swipe_amount | number | 15 | Pourcentage minimum de l'écran devant être balayé pour naviguer.
| skip_tabs | string | | Une liste de vues, séparées par des virgules, à ignorer lors du passage de la souris. e.g., `1,3,5`.
| skip_hidden | boolean | true | Automatically skips hidden tabs.
| wrap | boolean | true | Wrap from first tab to last tab and vice versa.
| prevent_default | boolean | false | Prevents the browsers default horizontal swipe actions. May require a browser refresh to take effect, if using an HA companion app this can be done by closing the app and reopening.
| animate | string |  | Swipe animations. Can be: `swipe`, `fade`, `flip`. The swipe animation should be considered experimental and depending on your setup may appear buggy.

**Example:**<br>
Don't just copy the example, it won't fit your needs. Build your own using the config options above.
```yaml
swipe_nav:
  wrap: false
  animate: swipe
  skip_tabs: 5,6,7,8
  prevent_default: true
  swipe_amount: 30
  
views:
```

# Thank you
Big thanks to:
* [@themoffatt](https://github.com/themoffatt) for beating me to the punch and letting me make a duplicate project.
* [@RomRider](https://github.com/RomRider) and his [decluttering-card](https://github.com/custom-cards/decluttering-card/) for the configuration method.
