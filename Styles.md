---
tags:
  - Magento
  - Frontend
Fonte: https://developer.adobe.com/commerce/frontend-core/guide/responsive-design/
sticker: emoji//1f980
---
## Cos'è il Responsive Web Design (RWD)

Il Responsive Web Design (RWD) consente ai siti web di adattarsi automaticamente a diverse dimensioni di schermo, offrendo un'esperienza utente ottimale su dispositivi desktop, tablet e mobile. In Magento 2, i temi predefiniti **Blank** e **Luma** adottano un approccio _mobile-first_, garantendo che il contenuto sia accessibile e ben visualizzato su tutti i dispositivi. [developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/responsive-design/?utm_source=chatgpt.com)

---

## Struttura dei Temi Responsive

Magento 2 utilizza **LESS** come pre-processore CSS per gestire gli stili. La struttura tipica di un tema responsive include:[developer.adobe.com+1developer.adobe.com+1](https://developer.adobe.com/commerce/frontend-core/guide/css/?utm_source=chatgpt.com)[developer.adobe.com+1developer.adobe.com+1](https://developer.adobe.com/commerce/frontend-core/guide/layouts/xml-instructions/?utm_source=chatgpt.com)

- `web/css/source/_theme.less`: per definire le variabili di stile.
    
- `web/css/source/_extend.less`: per estendere gli stili esistenti.[Pinterest+5Graphic Design Junction+5developer.adobe.com+5](https://graphicdesignjunction.com/2013/09/responsive-ecommerce-magento-themes/?utm_source=chatgpt.com)
    
- `web/css/source/_responsive.less`: per gestire i media query e i breakpoint.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/responsive-design/?utm_source=chatgpt.com)
    

Questi file consentono di personalizzare l'aspetto del tema in modo modulare e mantenibile.

---

##  Breakpoint e Media Query

I **breakpoint** determinano i punti in cui il layout del sito cambia per adattarsi a diverse dimensioni di schermo. Magento 2 definisce breakpoint standard come:

- `@screen__xs`: fino a 480px
    
- `@screen__s`: fino a 768px
    
- `@screen__m`: fino a 1024px[venustheme.com+2ArtVersion+2modulebazaar.com+2](https://www.artversion.com/web-design/magento-commerce/responsive-web-design-for-magento-stores/?utm_source=chatgpt.com)
    

Per applicare stili specifici a determinati breakpoint, si utilizzano i **media query** in combinazione con i mixin LESS:[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/responsive-design/mobile/?utm_source=chatgpt.com)

`.media-width(@extremum, @break) when (@extremum = 'max') and (@break = @screen__s) {     // Stili per schermi fino a 768px }`

È possibile aggiungere breakpoint personalizzati modificando le variabili nel file `_responsive.less`. [developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/responsive-design/breakpoints/?utm_source=chatgpt.com)

---

## Creazione di un Tema Mobile-Specifico

Per creare un tema specifico per dispositivi mobili:

1. **Eredita** dal tema Blank o Luma.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/css/?utm_source=chatgpt.com)
    
2. **Rimuovi** gli stili desktop nel file `default_head_blocks.xml`:[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/responsive-design/mobile/?utm_source=chatgpt.com)
    
    `<page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">     <head>         <remove src="css/styles-l.css" />     </head> </page>`
    

3. **Aggiungi** gli stili mobile nel file `default_head_blocks.xml`:
    
    `<page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">     <head>         <css src="css/styles-m.css" />     </head> </page>`
    

4. **Utilizza** i mixin `.media-width()` per applicare stili specifici ai breakpoint desiderati. [developer.adobe.com+1developer.adobe.com+1](https://developer.adobe.com/commerce/frontend-core/guide/responsive-design/mobile/?utm_source=chatgpt.com)
    

---

## Personalizzazione degli Stili Responsive

Per personalizzare gli stili responsive:

- **Estendi** gli stili esistenti nel file `_extend.less`.
    
- **Override** delle variabili nel file `_theme.less`.
    
- **Organizza** gli stili in file separati per componenti, come `_buttons.less`, `_header.less`, ecc.
    

Questa struttura modulare facilita la manutenzione e l'espansione del tema. [developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/css/quickstart/customize-styles/?utm_source=chatgpt.com)

---

## Esempio Pratico: Modifica del Colore dei Pulsanti

Per modificare il colore dei pulsanti primari:[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/css/?utm_source=chatgpt.com)

1. Nel file `_theme.less`, definisci una nuova variabile:[developer.adobe.com+1developer.adobe.com+1](https://developer.adobe.com/commerce/frontend-core/guide/css/quickstart/customize-styles/?utm_source=chatgpt.com)
    
    `@button-primary__background: #ff6600;`
    

2. Nel file `_buttons.less`, applica la variabile:
    
    `.action.primary {     background-color: @button-primary__background; }`
    

3. Compila gli stili e svuota la cache per applicare le modifiche.

## Approccio Mobile-First

Magento 2 adotta un approccio _mobile-first_ nel design responsive, iniziando la progettazione per dispositivi mobili e adattandosi progressivamente a schermi più grandi. I temi predefiniti **Blank** e **Luma** seguono questa filosofia, garantendo un'esperienza utente ottimale su tutti i dispositivi.

---

## Gestione dei Breakpoint

I **breakpoint** definiscono i punti in cui il layout del sito cambia per adattarsi a diverse dimensioni di schermo. Magento 2 utilizza variabili LESS per gestire i breakpoint, come:

- `@screen__xs`: fino a 480px
    
- `@screen__s`: fino a 768px[peerdh.com+1developer.adobe.com+1](https://peerdh.com/blogs/programming-insights/implementing-css-grid-for-responsive-layouts-in-laravel?utm_source=chatgpt.com)
    
- `@screen__m`: fino a 1024px[magezon.com+3LambdaTest+3peerdh.com+3](https://www.lambdatest.com/blog/responsive-css-media-queries-for-responsive-design/?utm_source=chatgpt.com)
    

Per applicare stili specifici a determinati breakpoint, si utilizzano i **media query** in combinazione con i mixin LESS:

`.media-width(@extremum, @break) when (@extremum = 'max') and (@break = @screen__s) {     // Stili per schermi fino a 768px }`

È possibile aggiungere breakpoint personalizzati definendo nuove variabili nel file `_variables.less` del tema. [developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/responsive-design/breakpoints/?utm_source=chatgpt.com)

---

## Struttura dei File CSS

Magento 2 utilizza LESS come pre-processore CSS. La struttura tipica dei file CSS in un tema include:

- `web/css/source/_theme.less`: per definire le variabili di stile.
    
- `web/css/source/_extend.less`: per estendere gli stili esistenti.
    
- `web/css/source/_responsive.less`: per gestire i media query e i breakpoint.
    

Questi file consentono di personalizzare l'aspetto del tema in modo modulare e mantenibile.

---

## Inclusione dei Fogli di Stile

Per includere i fogli di stile nel tema, è consigliabile utilizzare i file di layout XML. Ad esempio, per includere un file CSS personalizzato, si può aggiungere il seguente codice nel file `default_head_blocks.xml`:

`<page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">     <head>         <css src="css/custom.css" />     </head> </page>`

Questo approccio garantisce che i fogli di stile siano caricati correttamente in tutte le pagine del sito.