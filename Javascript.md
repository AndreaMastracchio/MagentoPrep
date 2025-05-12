---
tags:
  - Magento
  - Frontend
sticker: emoji//1f980
Fonte: https://developer.adobe.com/commerce/frontend-core/javascript/
---
## Introduzione

Magento 2 utilizza JavaScript per migliorare l'interattività del frontend e dell'Admin Panel. La piattaforma adotta RequireJS per la gestione dei moduli e Knockout.js per il data binding.

---

##  RequireJS

Magento 2 sfrutta RequireJS per il caricamento asincrono dei moduli JavaScript, migliorando le prestazioni del sito.

**Esempio di configurazione (`requirejs-config.js`):**


`var config = {     map: {         '*': {             'example': 'Vendor_Module/js/example'         }     },     paths: {         'customLib': 'Vendor_Module/js/lib/customLib'     },     shim: {         'customLib': {             deps: ['jquery'],             exports: 'customLib'         }     } };`

- **`map`**: Definisce alias per i moduli.
    
- **`paths`**: Specifica i percorsi dei moduli.
    
- **`shim`**: Configura moduli non AMD.
    

---

##  Componenti Personalizzati

Per aggiungere componenti JavaScript personalizzati:

1. **Posizionare il file**: `<theme_dir>/web/js/custom-component.js`[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/javascript/custom/?utm_source=chatgpt.com)
    
2. **Configurare RequireJS**: Aggiungere l'alias nel `requirejs-config.js`.[Adobe Sviluppatore+1Adobe Sviluppatore+1](https://developer.adobe.com/commerce/frontend-core/javascript/requirejs/?utm_source=chatgpt.com)
    
3. **Inizializzare il componente**: Utilizzare `data-mage-init` o uno script di inizializzazione.[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/javascript/init/?utm_source=chatgpt.com)
    

**Esempio di `data-mage-init`:**


`<div data-mage-init='{"Vendor_Module/js/custom-component": {}}'></div>`

---

##  Mixins

I mixins permettono di estendere o modificare il comportamento dei moduli esistenti senza sovrascriverli.

**Esempio di mixin:**

`define(function () {     'use strict';      return function (target) {         return target.extend({             newMethod: function () {                 // Nuova funzionalità             }         });     }; });`

Configurazione in `requirejs-config.js`:[Adobe Sviluppatore+1Adobe Sviluppatore+1](https://developer.adobe.com/commerce/frontend-core/javascript/init/?utm_source=chatgpt.com)


`var config = {     config: {         mixins: {             'Magento_Module/js/target-module': {                 'Vendor_Module/js/mixin': true             }         }     } };`

---

## 🧪 Inizializzazione dei Componenti

Magento 2 supporta due modalità di inizializzazione:[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/guide/themes/js-bundling/?utm_source=chatgpt.com)

- **Dichiarativa**: Utilizzando `data-mage-init`.[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/javascript/init/?utm_source=chatgpt.com)
    
- **Imperativa**: Utilizzando script JavaScript per inizializzare manualmente i componenti.
    

**Esempio di inizializzazione imperativa:**

`require(['jquery', 'Vendor_Module/js/custom-component'], function ($, customComponent) {     customComponent.initialize();`