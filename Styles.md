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

## CSS e LESS in Magento 2

Magento 2 utilizza **LESS** come pre-processore CSS, semplificando la gestione di file CSS complessi. Per definire gli stili di un negozio, è possibile utilizzare sia fogli di stile CSS che LESS.[r-martins.github.io](https://r-martins.github.io/m1docs/guides/v2.4/frontend-dev-guide/css-topics/css-overview.html?utm_source=chatgpt.com)

L'applicazione Commerce fornisce una libreria UI LESS incorporata, che può essere estesa opzionalmente.

---

## Personalizzazione degli stili del tema

Per personalizzare gli stili del frontend, è necessario creare un tema di design personalizzato. Successivamente, è possibile utilizzare uno dei seguenti approcci:

- **Override dei file LESS predefiniti**: se il tema eredita dal tema Blank o Luma, è possibile sovrascrivere i file LESS predefiniti, ad esempio modificando i valori delle variabili utilizzate nei file predefiniti.
    
- **Creazione di file LESS personalizzati**: utilizzando il pre-processore LESS incorporato, è possibile creare file LESS personalizzati per definire gli stili desiderati.
    
- **Creazione di file CSS personalizzati**: è possibile creare file CSS personalizzati, compilati opzionalmente utilizzando un pre-processore CSS di terze parti.
    

---

## Struttura dei file CSS in un tema

La struttura tipica dei file CSS in un tema Magento 2 include:

- `web/css/source/_theme.less`: per definire le variabili di stile.
    
- `web/css/source/_extend.less`: per estendere gli stili esistenti.
    
- `web/css/source/_responsive.less`: per gestire i media query e i breakpoint.
    

Questi file consentono di personalizzare l'aspetto del tema in modo modulare e mantenibile.

---

## Gestione dei breakpoint

I breakpoint determinano i punti in cui il layout del sito cambia per adattarsi a diverse dimensioni di schermo. Magento 2 definisce breakpoint standard come:

- `@screen__xs`: fino a 480px
    
- `@screen__s`: fino a 768px
    
- `@screen__m`: fino a 1024px
    

Per applicare stili specifici a determinati breakpoint, si utilizzano i media query in combinazione con i mixin LESS:

less

CopiaModifica

`.media-width(@extremum, @break) when (@extremum = 'max') and (@break = @screen__s) {     // Stili per schermi fino a 768px }`

È possibile aggiungere breakpoint personalizzati definendo nuove variabili nel file `_variables.less` del tema.

---

## Sovrascrittura e estensione degli stili

Per estendere gli stili di un tema esistente, è possibile utilizzare il file `_extend.less`. Tuttavia, se si desidera sovrascrivere le variabili del tema padre, è consigliabile creare un file `_theme.less` nel proprio tema e definire le nuove variabili.

Ad esempio, per modificare il colore dei pulsanti primari:

less

CopiaModifica

`@button-primary__background: #ff6600;`

Questo approccio consente di personalizzare gli stili mantenendo una struttura modulare e facilmente manutenibile.

## Struttura dei file CSS nei temi

In Magento 2, i file CSS e LESS sono organizzati all'interno dei temi. Le directory principali relative a `<THEME_DIR>` includono:[support.weltpixel.com+5developer.adobe.com+5magesolution.com+5](https://developer.adobe.com/commerce/frontend-core/guide/css/themes/?utm_source=chatgpt.com)
- `/<Namespace>_<Module>/web/css`: per stili specifici del modulo.[developer.adobe.com+1Inchoo.net+1](https://developer.adobe.com/commerce/frontend-core/guide/css/themes/?utm_source=chatgpt.com)
    
- `/web/css`: contiene file come `print.less`, `_styles.less`, `styles-m.less` e `styles-l.less`.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/css/themes/?utm_source=chatgpt.com)
    
- `/web/css/source`: include file di configurazione LESS, come `_theme.less`, che sovrascrivono i valori delle variabili della UI library.
    

---

## Inclusione dei fogli di stile

La modalità consigliata per includere i fogli di stile è tramite i file di layout. Per applicare gli stili a tutte le pagine del negozio, è possibile estendere il file `default_head_blocks.xml` del modulo `Magento_Theme` nel proprio tema:[developer.adobe.com+1magesolution.com+1](https://developer.adobe.com/commerce/frontend-core/guide/css/themes/?utm_source=chatgpt.com)

xml

CopiaModifica

`<page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">     <head>         <css src="css/custom.css" rel="stylesheet" type="text/css" />     </head> </page>`

Per includere un file CSS esterno, utilizzare l'attributo `src_type="url"`:
[SlideServe+1developer.adobe.com+1](https://www.slideserve.com/elsnermagentodeveloper/how-to-add-remove-js-css-fonts-in-magento-2-using-layout-xml-powerpoint-ppt-presentation?utm_source=chatgpt.com)

`<css src="https://example.com/styles.css" src_type="url" rel="stylesheet" type="text/css" />`

Se il sistema non trova i file CSS inclusi, cercherà automaticamente file con estensione `.less` con lo stesso nome, grazie al meccanismo di preprocessing integrato.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/css/themes/?utm_source=chatgpt.com)

## Modalità di Compilazione LESS in Magento 2

Magento 2 supporta due modalità principali per la compilazione dei file LESS in CSS:

### 1. **Compilazione Server-Side (Predefinita)**

- **Funzionamento**: I file `.less` vengono compilati sul server utilizzando la libreria PHP Less. In modalità sviluppatore, PHP genera i file CSS al volo, a meno che non siano già presenti.
    
- **Vantaggi**:
    
    - Adatta per ambienti di produzione.
        
    - Evita il "flash of unstyled text" (FOUT).[magesolution.com+4developer.adobe.com+4Pinterest+4](https://developer.adobe.com/commerce/frontend-core/guide/css/preprocess/?utm_source=chatgpt.com)[developer.adobe.com+1developer.adobe.com+1](https://developer.adobe.com/commerce/frontend-core/guide/css/quickstart/compilation-mode/?utm_source=chatgpt.com)
        
- **Procedura**:
    
    1. Creare un file `_extend.less` nella directory `web/css/source/` del tema.
        
    2. Aggiungere le personalizzazioni desiderate.
        
    3. Pulire la cache dei file statici.
        
    4. Ricaricare la pagina per vedere le modifiche.[developer.adobe.com+2developer.adobe.com+2developer.adobe.com+2](https://developer.adobe.com/commerce/frontend-core/guide/css/debug/?utm_source=chatgpt.com)
        
- **Esempio**:  
    Per modificare il colore dei pulsanti primari:
    

less

CopiaModifica

  `.action {       &.primary {           background-color: palevioletred;           border-color: palevioletred;       }   }`

### 2. **Compilazione Client-Side (Consigliata per lo Sviluppo Temi)**

- **Funzionamento**: I file `.less` vengono compilati nel browser dell'utente utilizzando la libreria less.js.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/css/debug/?utm_source=chatgpt.com)
    
- **Vantaggi**:
    
    - Ideale per lo sviluppo e il debug dei temi.
        
    - Le modifiche si riflettono immediatamente senza la necessità di ricompilare manualmente.
        
- **Svantaggi**:
    
    - Prestazioni più lente durante il caricamento delle pagine.
        
    - Possibilità di FOUT.[developer.adobe.com+2developer.adobe.com+2developer.adobe.com+2](https://developer.adobe.com/commerce/frontend-core/guide/css/quickstart/compilation-mode/?utm_source=chatgpt.com)
        
- **Procedura**:
    
    1. Nel pannello di amministrazione, navigare su:  
        `STORES > Settings > Configuration > ADVANCED > Developer > Frontend Development Workflow`.
        
    2. Impostare il tipo di workflow su "Client-side LESS compilation".
        
    3. Pulire i file statici.
        
    4. Aggiungere le personalizzazioni nel file `_extend.less`.
        
    5. Ricaricare la pagina per vedere le modifiche.[YouTube+6developer.adobe.com+6Magento Stack Exchange+6](https://developer.adobe.com/commerce/frontend-core/guide/css/preprocess/?utm_source=chatgpt.com)[developer.adobe.com+6blog.e-zest.com+6developer.adobe.com+6](https://blog.e-zest.com/working-on-less-with-different-compilation-modes-in-magento-2?utm_source=chatgpt.com)
        

---

## Utilizzo di Grunt per la Compilazione LESS

Grunt è uno strumento JavaScript che automatizza la compilazione dei file LESS.[developer.adobe.com+4developer.adobe.com+4developer.adobe.com+4](https://developer.adobe.com/commerce/frontend-core/guide/css/debug/?utm_source=chatgpt.com)

- **Procedura**:
    
    1. Installare e configurare Grunt.
        
    2. Registrare il tema in `dev/tools/grunt/configs/themes.js`.
        
    3. Eseguire i seguenti comandi:
        
        bash
        
        CopiaModifica
        
        `grunt exec:<nome_tema> grunt less:<nome_tema> grunt watch`
        
    4. Aggiungere le personalizzazioni nel file `_extend.less`.
        
    5. Ricaricare la pagina per vedere le modifiche.[developer.adobe.com+3developer.adobe.com+3developer.adobe.com+3](https://developer.adobe.com/commerce/frontend-core/guide/themes/workflow/?utm_source=chatgpt.com)[Magento Stack Exchange](https://magento.stackexchange.com/questions/305851/magento-2-css-source-maps-not-working?utm_source=chatgpt.com)
        
- **Vantaggi**:
    
    - Automatizza la compilazione e il monitoraggio delle modifiche.
        
    - Supporta la generazione di source maps per facilitare il debug.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/css/debug/?utm_source=chatgpt.com)
        

---

## Esempio Pratico: Modifica del Colore e della Dimensione del Font dei Pulsanti

Nel file `_extend.less`, aggiungere:

`.action {     &.primary {         background-color: palevioletred;         border-color: palevioletred;         font-size: 1.5em;     } }`

Dopo aver salvato le modifiche, pulire la cache dei file statici e ricaricare la pagina per vedere l'effetto.

## Cos'è la UI Library di Magento 2

La **UI Library** è una libreria frontend modulare basata su **LESS**, progettata per assistere gli sviluppatori di temi Magento. Utilizza una serie di mixin per elementi base, facilitando lo sviluppo e la personalizzazione dei temi frontend.[Inchoo.net+3Adobe Sviluppatore+3Inchoo.net+3](https://developer.adobe.com/commerce/frontend-core/guide/css/ui-library/?utm_source=chatgpt.com)

---

## Componenti Disponibili

La UI Library fornisce la possibilità di personalizzare e riutilizzare i seguenti elementi dell'interfaccia utente e proprietà:

- **actions-toolbar**[bingdigital.com+2Inchoo.net+2Adobe Sviluppatore+2](https://inchoo.net/magento-2/not-start-using-magento2-ui-library-easy-fun/?utm_source=chatgpt.com)
    
- **breadcrumbs**[Inchoo.net](https://inchoo.net/magento-2/working-with-css-in-your-first-magento-2-project/?utm_source=chatgpt.com)
    
- **buttons**[Inchoo.net+6Adobe Sviluppatore+6Adobe Sviluppatore+6](https://developer.adobe.com/commerce/frontend-core/guide/?utm_source=chatgpt.com)
    
- **drop-downs**[Adobe Sviluppatore+1Inchoo.net+1](https://developer.adobe.com/commerce/frontend-core/guide/css/ui-library/?utm_source=chatgpt.com)
    
- **forms**[bingdigital.com+2Adobe Sviluppatore+2Inchoo.net+2](https://developer.adobe.com/commerce/frontend-core/guide/css/ui-library/?utm_source=chatgpt.com)
    
- **icons**[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/guide/css/ui-library/?utm_source=chatgpt.com)
    
- **layout**
    
- **loaders**[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/guide/css/themes/?utm_source=chatgpt.com)
    
- **messages**[Inchoo.net](https://inchoo.net/magento-2/not-start-using-magento2-ui-library-easy-fun/?utm_source=chatgpt.com)
    
- **pagination**[bingdigital.com+2Inchoo.net+2Adobe Sviluppatore+2](https://inchoo.net/magento-2/not-start-using-magento2-ui-library-easy-fun/?utm_source=chatgpt.com)
    
- **popups**[Inchoo.net+1Adobe Sviluppatore+1](https://inchoo.net/magento-2/not-start-using-magento2-ui-library-easy-fun/?utm_source=chatgpt.com)
    
- **ratings**[bingdigital.com+2Adobe Sviluppatore+2Inchoo.net+2](https://developer.adobe.com/commerce/frontend-core/guide/css/ui-library/?utm_source=chatgpt.com)
    
- **sections** (tabs e accordions)[bingdigital.com+2Inchoo.net+2Adobe Sviluppatore+2](https://inchoo.net/magento-2/not-start-using-magento2-ui-library-easy-fun/?utm_source=chatgpt.com)
    
- **tables**[YouTube](https://www.youtube.com/watch?v=ytjgXldDqHY&utm_source=chatgpt.com)
    
- **tooltips**
    
- **typography**[Adobe Sviluppatore+9Adobe Sviluppatore+9mgt-commerce.com+9](https://developer.adobe.com/commerce/frontend-core/guide/css/ui-library/?utm_source=chatgpt.com)
    
- **utilities**[Inchoo.net+1Adobe Sviluppatore+1](https://inchoo.net/magento-2/not-start-using-magento2-ui-library-easy-fun/?utm_source=chatgpt.com)
    

Ognuno di questi componenti è definito da un file `.less` dedicato che contiene i relativi mixin e variabili.

---

## Struttura della Libreria

La UI Library si trova nella directory `lib/web/css/` del progetto Magento. All'interno di questa directory, la struttura è la seguente:[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/guide/css/ui-library/?utm_source=chatgpt.com)


`lib/web ├── css/ │   ├── docs/              # Documentazione della libreria │   ├── source/ │   │   ├── lib/           # File sorgente della libreria │   │   │   ├── _actions-toolbar.less │   │   │   ├── _breadcrumbs.less │   │   │   ├── _buttons.less │   │   │   ├── _dropdowns.less │   │   │   ├── _forms.less │   │   │   ├── _grids.less │   │   │   ├── _icons.less │   │   │   ├── _layout.less │   │   │   ├── _lib.less │   │   │   ├── _loaders.less │   │   │   ├── _messages.less │   │   │   ├── _navigation.less │   │   │   ├── _pages.less │   │   │   ├── _popups.less │   │   │   ├── _rating.less │   │   │   ├── _resets.less │   │   │   ├── _responsive.less │   │   │   ├── _sections.less │   │   │   ├── _tables.less │   │   │   ├── _tooltips.less │   │   │   ├── _typography.less │   │   │   ├── _utilities.less │   │   │   └── _variables.less │   │   ├── _email-variables.less │   │   ├── _extend.less │   │   ├── _theme.less │   │   ├── _variables.less │   │   └── _widgets.less │   └── styles.less ├── fonts/ │   └── Blank-Theme-Icons/ # Font personalizzati della libreria`

Ogni file `_component.less` contiene i mixin e le variabili specifiche per un componente dell'interfaccia utente. Ad esempio, `_buttons.less` definisce gli stili e le variabili per i pulsanti.

---

## Variabili Predefinite

Se il tuo tema eredita da un tema predefinito come **Blank**, puoi facilmente personalizzare qualsiasi elemento di una pagina del negozio senza modificare direttamente il codice CSS o i template. La personalizzazione può essere effettuata semplicemente modificando nel tuo tema i valori delle variabili predefinite utilizzate nei mixin della UI Library o del tema padre.[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/guide/css/ui-library/?utm_source=chatgpt.com)

L'elenco completo di queste variabili e i loro valori predefiniti è memorizzato in `lib/web/css/source/lib/variables/`. Questa directory contiene una serie di file, corrispondenti al set di elementi della UI Library, e ciascuno dei file elenca le variabili specifiche dell'elemento. Ad esempio, `lib/web/css/source/lib/variables/_breadcrumbs.less` contiene le variabili utilizzate nel mixin `breadcrumbs()`.[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/guide/css/ui-library/?utm_source=chatgpt.com)

---

## Documentazione Integrata

Informazioni dettagliate sulla UI Library sono integrate nel repository del codice:

- `lib/web/css/docs/source/README.md` descrive la struttura della UI Library, le convenzioni di denominazione e lo stile del codice.[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/guide/css/ui-library/?utm_source=chatgpt.com)
    
- `lib/web/css/docs` contiene un set di file `.html` con informazioni dettagliate sui mixin della libreria.


## Obiettivo

Questi standard definiscono i requisiti interni per la formattazione e lo stile del codice per i team che sviluppano codice LESS e CSS. Sebbene alcune parti del codice potrebbero non essere ancora conformi a questi standard, si sta lavorando per migliorare gradualmente. Questi standard sono opzionali per gli sviluppatori di terze parti. [Adobe Sviluppatore+1Adobe Sviluppatore+1](https://developer.adobe.com/commerce/php/coding-standards/less/?utm_source=chatgpt.com)

---

## 📐 Regole Generali

###  Indentazione

- Utilizzare solo spazi per l'indentazione.
    
- Dimensione del tab: 4 spazi.[Adobe Sviluppatore+1Adobe Sviluppatore+1](https://developer.adobe.com/commerce/php/coding-standards/less/?utm_source=chatgpt.com)
    
- Indentazione: 4 spazi.[Adobe Sviluppatore+7Adobe Sviluppatore+7Adobe Sviluppatore+7](https://developer.adobe.com/commerce/php/coding-standards/js/?utm_source=chatgpt.com)
    
- Indentazione di continuazione: 4 spazi.[Adobe Sviluppatore](https://developer.adobe.com/commerce/php/coding-standards/html-style-guide/?utm_source=chatgpt.com)
    

**Corretto:**

less

CopiaModifica

`.nav {     .nav-item {         ...     } }`

---

### Formattazione

#### 🔧 Graffe

- Aggiungere uno spazio prima delle graffe aperte e un'interruzione di riga dopo.[Adobe Sviluppatore](https://developer.adobe.com/commerce/php/coding-standards/less/?utm_source=chatgpt.com)
    
- Aggiungere un'interruzione di riga prima delle graffe chiuse.
    

**Corretto:**

`.nav {     color: @nav__color; }`

**Errato:**

`.nav{color: @nav__color;}`

---

#### 🔗 Delimitatori dei Selettori

- Aggiungere un'interruzione di riga dopo ogni delimitatore di selettore.
    
- Non aggiungere spazi prima o dopo i delimitatori.[Adobe Sviluppatore](https://developer.adobe.com/commerce/php/coding-standards/less/?utm_source=chatgpt.com)
    
**Corretto:**


```
`.nav, 
.bar {     
	color: @color__base; 
}`
```

**Errato:**

`.nav, .bar {     color: @color__base; }`

---

####  Virgolette

- Utilizzare virgolette singole.
    

**Corretto:**

`.nav {     content: 'lorem ipsum'; }`

**Errato:**

`.nav {     content: "lorem ipsum"; }`

---

#### ➕ Indentazione dei Combinatori

- Aggiungere spazi prima e dopo i combinatori.[Adobe Sviluppatore](https://developer.adobe.com/commerce/php/coding-standards/less/?utm_source=chatgpt.com)
    
**Corretto:**

`.nav + .bar {     color: @bar__color; }`

**Errato:**

`.nav+.bar {     color: @bar__color; }`

---

#### Interruzioni di Riga delle Proprietà

- Iniziare ogni dichiarazione di proprietà su una nuova riga.
    

**Corretto:**


```
.nav {     
	background-color: @nav__background-color;     
	color: @nav__color; 
}
```

**Errato:**


```
.nav {     
	color: @nav__color; background-color: @nav__background-color; 
}
```

---

#### ⚙️ Indentazione dei Due Punti delle Proprietà

- Aggiungere uno spazio dopo, ma non prima, dei due punti che separano i nomi delle proprietà dai valori.
    

**Corretto:**

`.nav {     color: @nav__color; }`

**Errato:**


`.nav {     color : @nav__color; }`

---

Per ulteriori dettagli e per consultare la guida completa, visita la documentazione ufficiale di Adobe:

🔗 [Standard di Codifica LESS](https://developer.adobe.com/commerce/php/coding-standards/less/)


**Grunt** è un task runner JavaScript utilizzato per automatizzare attività ripetitive nello sviluppo frontend, come la compilazione di file LESS in CSS. Magento 2 include configurazioni predefinite per Grunt, facilitando il processo di sviluppo dei temi.[Adobe Sviluppatore+2DEV Community+2Adobe Sviluppatore+2](https://dev.to/shahednasser/how-to-make-your-front-end-development-faster-in-magento-2-using-grunt-57fl?utm_source=chatgpt.com)

---
##  Cos'è Grunt in Magento 2
##  Prerequisiti

- Assicurati che l'applicazione sia impostata in modalità **developer** o **default**.
    

---

## 🛠️ Installazione e Configurazione di Grunt

1. **Installa Node.js**: Scarica e installa Node.js dal sito ufficiale.
    
2. **Installa Grunt CLI globalmente**:
    
    `npm install -g grunt-cli`
    

3. **Configura i file necessari**:
    
    - Nella directory principale di Magento (`<Magento_root>`), copia i seguenti file:[Adobe Sviluppatore+1Adobe Sviluppatore+1](https://developer.adobe.com/commerce/frontend-core/guide/tools/grunt/?utm_source=chatgpt.com)
        
        `cp package.json.sample package.json cp Gruntfile.js.sample Gruntfile.js cp grunt-config.json.sample grunt-config.json`
        
4. **Installa le dipendenze del progetto**:
    
    bash
    
    CopiaModifica
    
    `npm install npm update`
    

---

##  Configurazione del Tema

Definisci il tuo tema nel file `dev/tools/grunt/configs/local-themes.js`. Esempio:[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/guide/tools/grunt/?utm_source=chatgpt.com)

`'my_theme': {   area: 'frontend',   name: 'Vendor/theme',   locale: 'it_IT',   files: [     'css/styles-m',     'css/styles-l'   ],   dsl: 'less' }`

---

##  Comandi Utili di Grunt

- **Compilazione dei file LESS**:
    
  `grunt exec:my_theme   grunt less:my_theme`

- **Pulizia dei file statici**:
    
  `grunt clean:my_theme`

- **Monitoraggio delle modifiche**:


  `grunt watch`

Con `grunt watch`, Grunt monitorerà le modifiche ai file e ricompilerà automaticamente i file LESS quando necessario.

---

## Debug e Source Maps

Per facilitare il debug degli stili, puoi abilitare le **CSS source maps** nel tuo browser. Quando compili i file LESS con Grunt, le source maps vengono generate automaticamente. Assicurati di abilitare l'opzione "Enable CSS source maps" nelle impostazioni degli strumenti per sviluppatori del tuo browser.

## Mixins

I **mixins** in LESS permettono di riutilizzare gruppi di dichiarazioni CSS, simili a funzioni nei linguaggi di programmazione. Possono anche accettare parametri per una maggiore flessibilità.[YouTube+5SitePoint+5Tutorials Point+5](https://www.sitepoint.com/a-comprehensive-introduction-to-less-mixins/?utm_source=chatgpt.com)

**Esempio:**

`.rounded-corners(@radius: 5px) {   border-radius: @radius;   -webkit-border-radius: @radius;   -moz-border-radius: @radius; }  .box {   .rounded-corners(10px); }`

In questo esempio, `.rounded-corners` è un mixin che applica bordi arrotondati con un raggio specificato. Il mixin viene poi utilizzato all'interno della classe `.box` con un parametro di `10px`.[Wikipedia](https://fr.wikipedia.org/wiki/Less_%28langage%29?utm_source=chatgpt.com)[Wikipedia](https://en.wikipedia.org/wiki/Less_%28style_sheet_language%29?utm_source=chatgpt.com)

Per ulteriori dettagli, consulta la guida su [Mixins in LESS](https://www.geeksforgeeks.org/less-js-mixins-using-mixins-as-functions/).[Programando o Intentándolo+6GeeksforGeeks+6GeeksforGeeks+6](https://www.geeksforgeeks.org/less-js-mixins-using-mixins-as-functions/?utm_source=chatgpt.com)

---

##  @import At-Rules

La direttiva `@import` in LESS consente di suddividere il codice in più file, migliorando l'organizzazione e la manutenibilità. A differenza del CSS standard, in LESS è possibile posizionare le dichiarazioni `@import` in qualsiasi punto del file.

**Esempio:**

`@import "variables.less"; @import "mixins.less";`

Questo approccio permette di mantenere il codice modulare e facilmente gestibile.

Per approfondimenti, visita la sezione su [@import At-Rules](https://www.geeksforgeeks.org/less-js-import-at-rules/).[GeeksforGeeks+2GeeksforGeeks+2GeeksforGeeks+2](https://www.geeksforgeeks.org/less-js-import-at-rules/?utm_source=chatgpt.com)

---

## 🧱 Nesting

Il **nesting** in LESS consente di annidare selettori all'interno di altri, rispecchiando la struttura HTML e rendendo il codice più leggibile.

**Esempio:**

`.nav {   ul {     margin: 0;     li {       display: inline-block;     }   } }`

Questo codice si traduce in CSS come:[Wikipedia](https://fr.wikipedia.org/wiki/Less_%28langage%29?utm_source=chatgpt.com)

`.nav ul {   margin: 0; } .nav ul li {   display: inline-block; }`

Per ulteriori informazioni, consulta la guida su [Nested Rules in LESS](https://www.tutorialspoint.com/less/nested_rules.htm).[Tutorials Point+4Tutorials Point+4Tutorials Point+4](https://www.tutorialspoint.com/less/nested_rules.htm?utm_source=chatgpt.com)

---

## 🔧 Variabili

Le **variabili** in LESS permettono di definire valori riutilizzabili, migliorando la consistenza e facilitando le modifiche. Le variabili sono precedute dal simbolo `@`.[Wikipedia](https://it.wikipedia.org/wiki/LESS?utm_source=chatgpt.com)

**Esempio:**

`@primary-color: #4D926F;  h1 {   color: @primary-color; }`

In questo esempio, `@primary-color` è una variabile che definisce un colore utilizzato nel selettore `h1`.

Per approfondimenti, visita la sezione su [LESS Variables](https://www.geeksforgeeks.org/how-to-represent-a-variable-in-less/).[GeeksforGeeks+2GeeksforGeeks+2GeeksforGeeks+2](https://www.geeksforgeeks.org/how-to-represent-a-variable-in-less/?utm_source=chatgpt.com)

---

Queste funzionalità di LESS sono fondamentali per lo sviluppo efficace di temi in Magento 2

## 1.  Aggiunta di attributi ai content type

Per ogni content type, Page Builder aggiunge un attributo `data-pb-style` con un valore univoco generato dinamicamente. Ad esempio:[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/page-builder/styles/?utm_source=chatgpt.com)[Adobe Sviluppatore](https://developer.adobe.com/commerce/php/coding-standards/less/?utm_source=chatgpt.com)

`<h2 data-content-type="heading"     data-appearance="default"     data-element="main"     data-pb-style="XDFNGK9">     Il mio Titolo </h2>`

Questo attributo consente di identificare e applicare stili specifici a ciascun elemento.

---

## 2.  Generazione di selettori CSS dinamici

Page Builder crea selettori CSS combinando l'ID `html-body` della pagina con l'attributo `data-pb-style`. Ad esempio:[Adobe Sviluppatore+1Adobe Sviluppatore+1](https://developer.adobe.com/commerce/frontend-core/page-builder/styles/?utm_source=chatgpt.com)[mgt-commerce.com+3Magento Tutorial and Marketing Tips+3Adobe Sviluppatore+3](https://blog.landofcoder.com/use-widgets-magento-2/?utm_source=chatgpt.com)


`#html-body [data-pb-style="XDFNGK9"] {     /* Regole CSS */ }`

Questo approccio garantisce una specificità CSS di 110, facilitando l'override degli stili con CSS personalizzati.[Adobe Sviluppatore+1Adobe Sviluppatore+1](https://developer.adobe.com/commerce/frontend-core/page-builder/styles/?utm_source=chatgpt.com)

---

## 3.  Creazione di regole CSS

Le regole CSS vengono generate in base ai valori impostati nell'editor del content type. Ad esempio, per un content type "Row" con margini e padding personalizzati:[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/page-builder/styles/?utm_source=chatgpt.com)


`#html-body [data-pb-style="WMWMCFQ"] {     justify-content: flex-start;     display: flex;     flex-direction: column;     background-position: left top;     background-size: cover;     background-repeat: no-repeat;     background-attachment: scroll;     border-style: none;     border-width: 1px;     border-radius: 0;     margin: 0 0 10px;     padding: 10px; }`

Ogni volta che un utente modifica e salva le impostazioni di un content type, Page Builder aggiorna le regole CSS corrispondenti.

---

## 4.  Creazione di fogli di stile interni

Page Builder inserisce tutte le regole CSS generate in un blocco `<style>` interno alla pagina, posizionato prima dei content type. Ad esempio:[Adobe Sviluppatore+8mgt-commerce.com+8Adobe Sviluppatore+8](https://www.mgt-commerce.com/tutorial/magento-2-page-builder/?utm_source=chatgpt.com)


`<style>     #html-body [data-pb-style="XDFNGK9"] {         /* Regole CSS */     }     /* Altre regole */ </style>`

Questo metodo consente di applicare stili specifici a ciascun content type senza la necessità di file CSS esterni.

---

##  Personalizzazione degli stili

Per personalizzare gli stili dei content type, è possibile utilizzare CSS personalizzati con una specificità superiore a 110. Ad esempio:[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/page-builder/styles/?utm_source=chatgpt.com)


`#html-body h2[data-content-type="heading"] {     font-size: 40px;     line-height: 61px;     font-weight: 700;     margin-bottom: 0; }`

Inoltre, è possibile organizzare i file `.less` in directory specifiche per ciascun content type e utilizzare file `_import.less` e `_module.less` per una gestione più efficiente degli stili. Per ulteriori dettagli su come sovrascrivere gli stili di Page Builder, consulta la guida ufficiale: [Use Modules to override styles](https://developer.adobe.com/commerce/frontend-core/page-builder/styles/use-modules-to-override-styles/).[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/page-builder/styles/use-modules-to-override-styles/?utm_source=chatgpt.com)

---

Per ulteriori informazioni su come Page Builder gestisce gli stili dei content type, puoi consultare la documentazione ufficiale: [How Page Builder styles content](https://developer.adobe.com/commerce/frontend-core/page-builder/styles/).[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/page-builder/styles/?utm_source=chatgpt.com)

## Utilizzare i Moduli per Sovrascrivere gli Stili

Quando crei un modulo di Page Builder, sia estendendo un tipo di contenuto esistente che creando un tipo di contenuto personalizzato, è consigliabile sovrascrivere gli stili direttamente all'interno del modulo. Questo approccio garantisce una maggiore modularità e facilita la manutenzione del codice.

---

##  Vantaggi dell'Utilizzo dei Moduli

- **Modularità**: Gli stili sono confinati all'interno del modulo, rendendo il codice più organizzato.
    
- **Riutilizzabilità**: Gli stili definiti nel modulo possono essere facilmente riutilizzati o sovrascritti nei temi.
    
- **Manutenibilità**: Le modifiche agli stili sono isolate, riducendo il rischio di impatti indesiderati su altre parti del sistema.
    

---

##  Passaggi per Sovrascrivere gli Stili

### 1.  Creare le Directory `adminhtml` e `frontend`

All'interno del tuo modulo, crea le directory `adminhtml` e `frontend` per separare gli stili destinati rispettivamente al pannello di amministrazione e al frontend del sito.[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/page-builder/styles/use-modules-to-override-styles/?utm_source=chatgpt.com)

bash

CopiaModifica

`<module_root>/ ├── view/ │   ├── adminhtml/ │   │   └── web/ │   │       └── css/ │   │           └── source/ │   └── frontend/ │       └── web/ │           └── css/ │               └── source/`

### 2.  Aggiungere le Directory dei Tipi di Contenuto

Per una migliore organizzazione, crea sottodirectory all'interno di `source/` che corrispondano ai tipi di contenuto che desideri sovrascrivere. Ad esempio, per il tipo di contenuto `heading`:

swift

CopiaModifica

`<module_root>/view/frontend/web/css/source/heading/`

### 3.  Creare i File `.less` e Definire gli Stili

All'interno delle directory dei tipi di contenuto, crea file `.less` per ciascuna variante di aspetto che desideri sovrascrivere. Ad esempio, per l'aspetto `default` del tipo di contenuto `heading`:


`<module_root>/view/frontend/web/css/source/heading/_default.less`

In questo file, utilizza il pattern di selettore CSS consigliato per garantire una specificità sufficiente a sovrascrivere gli stili di Page Builder:[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/page-builder/styles/use-modules-to-override-styles/?utm_source=chatgpt.com)


`#html-body [data-content-type='heading'].my-custom-class {     font-size: 40px;     line-height: 61px;     font-weight: 700;     margin-bottom: 0; }`

### 4. 📄 Creare il File `_module.less`

Il file `_module.less` è necessario per includere gli stili definiti nei file `_default.less`. All'interno di `source/`, crea il file `_module.less` e importa i file `.less` dei tipi di contenuto:[Adobe Sviluppatore](https://developer.adobe.com/commerce/frontend-core/page-builder/styles/use-modules-to-override-styles/?utm_source=chatgpt.com)


`<module_root>/view/frontend/web/css/source/_module.less`

Contenuto di `_module.less`:


`@import 'heading/_default.less';`

### 5. 🔁 Ripetere per l'Area `adminhtml`

Segui gli stessi passaggi per l'area `adminhtml` se desideri sovrascrivere gli stili anche nel pannello di amministrazione.

---

## 🧠 Considerazioni Finali

- **Specificità dei Selettori**: Assicurati che i tuoi selettori CSS abbiano una specificità superiore a quella degli stili di Page Builder (specificità di 110) per garantire che le tue regole vengano applicate correttamente.
    
- **Organizzazione**: Mantenere una struttura organizzata delle directory e dei file facilita la manutenzione e l'espansione futura del modulo.
    
- **Compatibilità**: Testa le modifiche sia nel frontend che nel backend per assicurarti che gli stili siano applicati correttamente in entrambe le aree.
    

---

Per ulteriori dettagli, consulta la documentazione ufficiale di Adobe: [Use Modules to Override Styles](https://developer.adobe.com/commerce/frontend-core/page-builder/styles/use-modules-to-override-styles/).