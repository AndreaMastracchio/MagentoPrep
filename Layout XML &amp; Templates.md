---
tags:
  - Magento
  - Frontend
Fonte: https://developer.adobe.com/commerce/frontend-core/guide/layouts/
sticker: emoji//1f980
---
## Concetti fondamentali dei layout in Magento 2

In Magento 2, la struttura delle pagine è definita attraverso file XML che determinano l'organizzazione e il contenuto delle pagine. Gli elementi principali sono:

- **Layout**: Definisce la struttura generale della pagina, specificando come sono organizzati i contenitori e i blocchi.
    
- **Contenitori (Containers)**: Agiscono come segnaposto strutturali all'interno del layout, organizzando i blocchi senza contenere direttamente contenuti visibili. Esempi comuni includono `header`, `footer`, `main`, `sidebar`.
    
- **Blocchi (Blocks)**: Rappresentano unità di contenuto visibile, come elenchi di prodotti, carrelli, menu, ecc. Ogni blocco è associato a una classe PHP e a un template `.phtml` per il rendering del contenuto.
    

---

## Tipi di file di layout

Magento 2 utilizza diversi tipi di file XML per gestire i layout:

1. **Layout della pagina (Page Layout)**: Definisce la struttura scheletrica della pagina, come il numero di colonne. Esempio: `1column.xml`, `2columns-left.xml`.
    
2. **Configurazione della pagina (Page Configuration)**: Specifica dettagli come meta tag, script, e include blocchi e contenitori specifici per una determinata pagina.
    
3. **Layout generico (Generic Layout)**: Utilizzato per contenuti restituiti tramite AJAX, email o frammenti HTML, definendo la struttura all'interno del tag `<body>`.[Rixxo - B2B eCommerce Experts+4Adobe Developer+4Adobe Developer+4](https://developer.adobe.com/commerce/frontend-core/guide/layouts/types/?utm_source=chatgpt.com)
    

---

## Handle dei layout

Gli _handle_ sono identificatori univoci che determinano quale file di layout viene applicato a una determinata pagina. I principali tipi di handle includono:

- **Handle per tipo di pagina**: Associati a tipi di pagina specifici, come `catalog_product_view` per la pagina del prodotto.
    
- **Handle per pagina specifica**: Riferiti a pagine con parametri specifici, ad esempio `catalog_product_view_type_simple_id_128` per un prodotto con ID 128.
    
- **Handle arbitrari**: Non associati direttamente a una pagina, ma utilizzati per includere layout comuni in più pagine.[Adobe Developer+2MGT Commerce+2Adobe Developer+2](https://www.mgt-commerce.com/tutorial/magento-2-layout-overview/?utm_source=chatgpt.com)[Adobe Developer](https://developer.adobe.com/commerce/frontend-core/guide/layouts/?utm_source=chatgpt.com)
    

---

## Istruzioni comuni nei file di layout

Per personalizzare i layout, Magento 2 offre diverse istruzioni XML:

- `<block>`: Definisce un blocco di contenuto.
    
- `<container>`: Crea un contenitore strutturale.
    
- `<referenceBlock>` e `<referenceContainer>`: Consentono di fare riferimento a blocchi o contenitori esistenti per modificarli.
    
- `<move>`: Sposta un blocco o contenitore in un'altra posizione.
    
- `<remove>`: Rimuove un blocco o contenitore.
    
- `<update>`: Include un altro handle di layout.
    
- `<argument>`: Passa parametri a un blocco.[Adobe Developer](https://developer.adobe.com/commerce/frontend-core/guide/layouts/practice/?utm_source=chatgpt.com)
    

---

## Personalizzazione dei layout

Per modificare o estendere i layout esistenti, è consigliabile:[MGT Commerce+15Information Technology For You+15Adobe Developer+15](https://itc-4u.com/magento-2-understand-layout-xml-files/?utm_source=chatgpt.com)

- **Estendere un layout**: Creare un nuovo file XML che aggiunge o modifica elementi rispetto al layout originale, mantenendo l'originale intatto.
    
- **Sovrascrivere un layout**: Creare un file XML con lo stesso nome del layout originale nella directory del tema personalizzato, che sostituirà completamente il layout esistente.
    

---

## Layout specifici per prodotti

Magento 2 consente di personalizzare i layout delle pagine prodotto in base al tipo di prodotto o a specifici prodotti:

- **Per tipo di prodotto**: File come `catalog_product_view_type_simple.xml` o `catalog_product_view_type_configurable.xml` si applicano rispettivamente a prodotti semplici o configurabili.
    
- **Per ID prodotto**: File come `catalog_product_view_id_45.xml` si applicano al prodotto con ID 45.
    
- **Per SKU prodotto**: File come `catalog_product_view_sku_24-WG080.xml` si applicano al prodotto con SKU `24-WG080`.[Adobe Developer+3Adobe Developer+3Adobe Developer+3](https://developer.adobe.com/commerce/frontend-core/guide/layouts/product-layouts/?utm_source=chatgpt.com)
    

---

## Esercitazioni pratiche

La documentazione fornisce esempi pratici su come personalizzare i layout, come ad esempio:

- **Modificare i link dell'account cliente nell'intestazione**: Trasformare i link in un menu a discesa.
    
- **Aggiungere un secondo piè di pagina**: Creare un layout con due sezioni di piè di pagina.

## Istruzioni XML nei Layout di Magento 2

Magento 2 utilizza file XML per definire la struttura e il contenuto delle pagine. Le istruzioni XML permettono di aggiungere, modificare o rimuovere elementi nella pagina.

###  Tipi di Istruzioni XML

1. **`<block>`**: Definisce un blocco, che è un'unità di contenuto visibile sulla pagina.
    
    - **Attributi comuni**:
        
        - `name`: Identificatore univoco del blocco.
            
        - `class`: Classe PHP associata al blocco.
            
        - `template`: Percorso del file `.phtml` utilizzato per il rendering.
            
2. **`<container>`**: Definisce un contenitore strutturale per organizzare i blocchi.
    
    - **Attributi comuni**:
        
        - `name`: Identificatore univoco del contenitore.
            
        - `label`: Etichetta descrittiva.
            
        - `htmlTag`: Tag HTML utilizzato (es. `div`).
            
        - `htmlClass`: Classe CSS associata.
            
3. **`<referenceBlock>` e `<referenceContainer>`**: Consentono di fare riferimento a blocchi o contenitori esistenti per modificarli o aggiungere nuovi elementi al loro interno.
    
4. **`<move>`**: Sposta un blocco o contenitore in un'altra posizione nella struttura della pagina.
    
5. **`<remove>`**: Rimuove un blocco o contenitore dalla pagina.
    
6. **`<update>`**: Include un altro handle di layout, permettendo di riutilizzare configurazioni esistenti.
    
7. **`<argument>`**: Passa parametri a un blocco, utilizzati nel suo template o nella logica PHP.[Adobe Developer](https://developer.adobe.com/commerce/frontend-core/guide/layouts/xml-instructions/?utm_source=chatgpt.com)
    
8. **`<action>`**: Invoca un metodo su un blocco, permettendo di impostare proprietà o eseguire operazioni specifiche.
    

### Attributi di Posizionamento

- **`before` e `after`**: Determinano la posizione relativa di un blocco o contenitore rispetto ad altri elementi fratelli.
    

### ⚠️ Differenze tra `<block>` e `<container>`

- **`<block>`**: Rende contenuto visibile e ha un template associato.
    
- **`<container>`**: Serve come struttura per organizzare i blocchi, ma non ha un template e non rende contenuto direttamente.[Adobe Developer](https://developer.adobe.com/commerce/frontend-core/guide/templates/override/?utm_source=chatgpt.com)

## Gestione dei Layout XML in Magento 2

Magento 2 utilizza file XML per definire la struttura e il contenuto delle pagine. Per garantire stabilità e sicurezza durante gli aggiornamenti, è consigliato **non modificare direttamente** i layout predefiniti dei moduli o dei temi. Invece, è preferibile creare file di layout che estendono o sovrascrivono quelli esistenti nel proprio tema personalizzato.

###  Impostare il Layout della Pagina

Il tipo di layout di una pagina è definito nell'attributo `layout` del nodo radice `<page>` nel file di configurazione della pagina.[Adobe Developer](https://developer.adobe.com/commerce/frontend-core/guide/layouts/xml-manage/?utm_source=chatgpt.com)

**Esempio:** Per cambiare il layout della pagina di ricerca avanzata da "1 colonna" a "2 colonne con barra sinistra", estendere il file `catalogsearch_advanced_index.xml` nel tema aggiungendo il seguente layout:[Adobe Developer](https://developer.adobe.com/commerce/frontend-core/guide/layouts/xml-manage/?utm_source=chatgpt.com)

`<page layout="2columns-left" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"       xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">   ... </page>`

### Includere Risorse Statiche (JavaScript, CSS, Font)

Per aggiungere JavaScript, CSS e altre risorse statiche, modificare la sezione `<head>` del file di configurazione della pagina. Il modo consigliato è estendere il file `default_head_blocks.xml` nel proprio tema personalizzato.[Adobe Developer+1magentopost.com+1](https://developer.adobe.com/commerce/frontend-core/guide/layouts/xml-manage/?utm_source=chatgpt.com)

**Esempio:** Per aggiungere file CSS e JavaScript locali ed esterni:[Adobe Developer](https://developer.adobe.com/commerce/frontend-core/guide/layouts/xml-manage/?utm_source=chatgpt.com)


```
`<page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"       xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">   <head>     <!-- Aggiunta di stili locali -->     <css src="css/miei-stili.css" />     <css src="Vendor_Module::css/stili-personalizzati.css" />      <!-- Aggiunta di script locali -->     <script src="Magento_Catalog::js/esempio1.js" />     <script src="Magento_Catalog/js/esempio1.js" />      <!-- Aggiunta di script con attributi async o defer -->     <script async="" src="Magento_Catalog::js/esempio1.js" />     <script defer="" src="Magento_Catalog::js/esempio1.js" />      <!-- Aggiunta di risorse esterne -->     <css src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap-theme.min.css" src_type="url" />     <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/js/bootstrap.min.js" src_type="url" />     <link rel="stylesheet" type="text/css" src="http://fonts.googleapis.com/css?family=Montserrat" src_type="url" />   </head> </page>`
```

###  Estendere e Sovrascrivere Layout

Per personalizzare i layout senza modificare direttamente i file core:

- **Estendere un layout:** Creare un file di layout che aggiunge o modifica elementi rispetto al layout originale, mantenendo l'originale intatto.
    
- **Sovrascrivere un layout:** Creare un file di layout con lo stesso nome del layout originale nella directory del tema personalizzato, che sostituirà completamente il layout esistente.


## Obiettivo: Personalizzare i link dell'account cliente nell'intestazione

Nell'esempio fornito, l'azienda fittizia _ExampleCorp_ desidera modificare il proprio tema "Orange", ereditato dal tema "Blank", per trasformare i link dell'account cliente nell'intestazione in un menu a discesa, simile a quello presente nel tema "Luma".[Adobe Developer](https://developer.adobe.com/commerce/frontend-core/guide/layouts/practice/?utm_source=chatgpt.com)

---

## Stato iniziale: Struttura predefinita dell'intestazione

Nel tema "Blank", l'intestazione presenta una struttura simile alla seguente:

html

CopiaModifica

`<div class="panel header">     ...     <ul class="header links">         <li class="item link compare" data-bind="scope: 'compareProducts'" data-role="compare-products-link">...</li>         <li class="greet welcome" data-bind="scope: 'customer'">...</li>         <li>...</li>         <li class="link wishlist" data-bind="scope: 'wishlist'">...</li>         <li class="authorization-link" data-label="or">...</li>     </ul>     ... </div>`

---

## Modifiche da apportare

Per ottenere l'effetto desiderato, è necessario:

1. **Avvolgere** la lista dei link dell'intestazione (`<ul class="header links">`) all'interno di un nuovo contenitore (`<div>`) che fungerà da menu a discesa.
    
2. **Aggiungere** un saluto personalizzato con una freccia a discesa prima della lista, che fungerà da trigger per il menu.[Adobe Developer](https://developer.adobe.com/commerce/frontend-core/guide/layouts/practice/?utm_source=chatgpt.com)
    

---

## Implementazione nel layout XML

Per implementare queste modifiche, è necessario estendere il file di layout pertinente nel tema "Orange". Ad esempio, si può creare o modificare il file `default.xml` nel percorso `app/design/frontend/ExampleCorp/orange/Magento_Theme/layout/` con il seguente contenuto:

`<page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"       xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">     <body>         <!-- Aggiunta del contenitore per il menu a discesa -->         <referenceBlock name="header.links">             <container name="customer.account.dropdown" htmlTag="div" htmlClass="customer-account-dropdown" before="-">                 <block class="Magento\Framework\View\Element\Template" name="customer.greeting" template="Magento_Theme::html/customer_greeting.phtml"/>                 <container name="customer.links.container" htmlTag="ul" htmlClass="header links">                     <!-- I link esistenti verranno spostati qui -->                 </container>             </container>         </referenceBlock>     </body> </page>`

In questo esempio:[Adobe Developer](https://developer.adobe.com/commerce/frontend-core/guide/layouts/xml-instructions/?utm_source=chatgpt.com)

- Si crea un nuovo contenitore `customer.account.dropdown` che avvolge i link dell'account cliente.
    
- Si aggiunge un blocco `customer.greeting` che utilizza un template personalizzato per visualizzare il saluto con la freccia a discesa.
    
- Si crea un contenitore `customer.links.container` che conterrà i link esistenti, mantenendo la classe CSS originale per garantire la compatibilità con gli stili esistenti.[Adobe Developer](https://developer.adobe.com/commerce/frontend-core/guide/layouts/practice/?utm_source=chatgpt.com)
    

---

##  Personalizzazione del template

Il file `customer_greeting.phtml` potrebbe contenere il seguente codice per visualizzare il saluto e la freccia a discesa:

`<div class="customer-greeting">     <span class="greet">Ciao, <?= $block->escapeHtml($block->getCustomerName()) ?></span>     <span class="dropdown-arrow"></span> </div>`

Assicurati di implementare la logica nel blocco PHP associato per recuperare il nome del cliente e gestire la visualizzazione appropriata.

---

## Risultato atteso

Dopo aver applicato queste modifiche:

- I link dell'account cliente saranno avvolti in un menu a discesa, migliorando l'organizzazione e l'estetica dell'intestazione.
    
- Il saluto personalizzato con la freccia a discesa fungerà da trigger per mostrare o nascondere i link, offrendo un'esperienza utente più interattiva e moderna.
## Layout delle Pagine Prodotto in Magento 2

Magento 2 offre un sistema flessibile per personalizzare le pagine prodotto attraverso file di layout XML. Questi file permettono di modificare la struttura e i contenuti delle pagine prodotto a diversi livelli:

### File di Layout Disponibili

- **`catalog_product_view.xml`**: Layout comune che influisce su tutti i tipi di prodotto.
    
- **`catalog_product_view_type_bundle.xml`**: Layout specifico per prodotti di tipo _bundle_.
    
- **`catalog_product_view_type_configurable.xml`**: Layout specifico per prodotti _configurabili_.
    
- **`catalog_product_view_type_downloadable.xml`**: Layout specifico per prodotti _scaricabili_.
    
- **`catalog_product_view_type_grouped.xml`**: Layout specifico per prodotti _raggruppati_.
    
- **`catalog_product_view_type_simple.xml`**: Layout specifico per prodotti _semplici_.
    
- **`catalog_product_view_type_virtual.xml`**: Layout specifico per prodotti _virtuali_.[MGT Commerce](https://www.mgt-commerce.com/blog/magento-2-grouped-products/?utm_source=chatgpt.com)
    
- **`catalog_product_view_id_{id}.xml`**: Layout applicato a un prodotto specifico identificato dall'ID. Esempio: `catalog_product_view_id_45.xml`.[MGT Commerce+3Adobe Developer+3Adobe Developer+3](https://developer.adobe.com/commerce/frontend-core/guide/layouts/product-layouts/?utm_source=chatgpt.com)
    
- **`catalog_product_view_sku_{sku}.xml`**: Layout applicato a un prodotto specifico identificato dallo SKU. Esempio: `catalog_product_view_sku_24-WG080.xml`.[Adobe Developer](https://developer.adobe.com/commerce/frontend-core/guide/layouts/product-layouts/?utm_source=chatgpt.com)
    

### 🛠️ Personalizzazione dei Layout

Per personalizzare i layout delle pagine prodotto:

1. **Creare o modificare** il file di layout corrispondente nella directory del tema personalizzato:
    
    `app/design/frontend/<Vendor>/<theme>/Magento_Catalog/layout/`
    
2. **Utilizzare le istruzioni XML** per aggiungere, modificare o rimuovere blocchi e contenitori.
    
3. **Pulire la cache** dopo aver apportato le modifiche:
        
    `bin/magento cache:clean`
    

### 🎯 Esempio: Personalizzare la Pagina di un Prodotto Semplice

Per aggiungere un blocco personalizzato alla pagina di un prodotto semplice:

1. **Creare il file** `catalog_product_view_type_simple.xml` nella directory del tema personalizzato.[Adobe Developer](https://developer.adobe.com/commerce/frontend-core/guide/layouts/product-layouts/?utm_source=chatgpt.com)
    
2. **Aggiungere il seguente contenuto**:
    
    `<?xml version="1.0"?> <page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"       xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">     <body>         <referenceContainer name="product.info.main">             <block class="Magento\Framework\View\Element\Template" name="custom.block" template="Magento_Catalog::product/custom.phtml"/>         </referenceContainer>     </body> </page>`
    

3. **Creare il template** `custom.phtml` nella directory:
       
    `app/design/frontend/<Vendor>/<theme>/Magento_Catalog/templates/product/`
    
    E aggiungere il contenuto desiderato.

## Tipi di File di Layout in Magento 2

In Magento 2, la struttura e il contenuto delle pagine sono definiti attraverso tre principali tipi di file XML di layout:

### 1. Page Layout

- **Descrizione**: Definisce la struttura generale della pagina, come il numero di colonne e la disposizione dei contenitori principali.
    
- **Caratteristiche**:
    
    - Contiene solo elementi `<container>`.
        
    - Non include blocchi (`<block>`).
        
    - Viene utilizzato per stabilire il wireframe della pagina.[Aureate Labs](https://aureatelabs.com/blog/magento-tutorials/how-to-create-a-custom-widget-in-magento-2/?utm_source=chatgpt.com)
        
- **Esempi di layout**:
    
    - `1column`
        
    - `2columns-left`
        
    - `2columns-right`
        
    - `3columns`
        
    - `empty`[Inviqa+4Sudhanshu's Blog+4Meetanshi+4](https://www.sudhanshubajaj.com/how-to-create-custom-layout-page-in-magento2/?utm_source=chatgpt.com)
        
- **Dichiarazione**: Tutti i layout di pagina utilizzati per il rendering devono essere dichiarati nel file di dichiarazione dei layout di pagina.
    
### 2. Page Configuration

- **Descrizione**: Definisce la struttura dettagliata della pagina, inclusi intestazione, piè di pagina, contenuti e metadati.
    
- **Caratteristiche**:
    
    - Contiene sia `<container>` che `<block>`.
        
    - Specifica il layout di pagina da utilizzare.
        
    - Definisce i contenuti e la struttura dettagliata all'interno del tag `<body>`.
        
- **Esempi di file**:
    
    - `catalog_product_view.xml`
        
    - `cms_page_view.xml`
        
    - `checkout_cart_index.xml`[Aureate Labs](https://aureatelabs.com/blog/magento-tutorials/how-to-create-a-custom-widget-in-magento-2/?utm_source=chatgpt.com)[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/layouts/product-layouts/?utm_source=chatgpt.com)
        
### 3.  Generic Layout

- **Descrizione**: File XML che definiscono contenuti e struttura dettagliata all'interno della sezione `<body>` della pagina.
    
- **Caratteristiche**:
    
    - Utilizzati per modificare o estendere la configurazione delle pagine esistenti.
        
    - Possono essere applicati a più pagine o a specifiche condizioni.
        
- **Esempi di file**:
    
    - `default.xml`
        
    - `catalog_category_view.xml`
        
    - `customer_account.xml`[Inviqa+2meakhilanand.blogspot.com+2Aureate Labs+2](https://meakhilanand.blogspot.com/2018/11/magento-currently-largest-open-source.html?utm_source=chatgpt.com)[Meetanshi](https://meetanshi.wordpress.com/2023/06/15/how-to-add-blocks-class-name-dynamically-into-layout-xml-file-in-magento-2/?utm_source=chatgpt.com)
        

---
## Differenze Chiave

|Tipo di File|Contenuto Principale|Scopo Principale|
|---|---|---|
|Page Layout|`<container>`|Definire la struttura generale della pagina|
|Page Configuration|`<container>`, `<block>`|Definire struttura dettagliata e contenuti|
|Generic Layout|`<container>`, `<block>`|Modificare o estendere configurazioni esistenti|

## Estendere un Layout in Magento 2

In Magento 2, estendere un layout significa aggiungere o modificare elementi specifici di una pagina senza sovrascrivere completamente il file di layout originale. Questo approccio è preferibile poiché consente di mantenere la compatibilità con gli aggiornamenti futuri del sistema.

### Struttura dei File di Layout

Per estendere un layout, è necessario creare un file XML con lo stesso nome del layout originale nella directory del tema personalizzato. La struttura del percorso è la seguente:

php-template

CopiaModifica

`app/design/frontend/<Vendor>/<theme>/<Namespace>_<Module>/layout/<layout_file>.xml`

Ad esempio, per estendere il layout `catalog_product_view.xml` del modulo `Magento_Catalog`, il file dovrebbe essere posizionato in:

swift

CopiaModifica

`app/design/frontend/<Vendor>/<theme>/Magento_Catalog/layout/catalog_product_view.xml`

### Esempio di Estensione

Supponiamo di voler spostare l'elemento `product.info.stock.sku` all'interno del contenitore `product.info.price` dopo l'elemento `product.price.final`. Il contenuto del file `catalog_product_view.xml` sarebbe:[Mageplaza](https://www.mageplaza.com/devdocs/how-extend-layout-magento-2.html?utm_source=chatgpt.com)

xml

CopiaModifica

`<page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"       xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">    <body>        <move element="product.info.stock.sku" destination="product.info.price" after="product.price.final"/>    </body> </page>`

Questa istruzione `move` sposta l'elemento specificato nella nuova posizione desiderata.

### Processo di Unione dei Layout

Magento 2 unisce i file di layout seguendo un ordine specifico:

1. Carica le dichiarazioni dei handle e le istruzioni di layout da ciascun file di layout incluso.
    
2. Appende i risultati in un formato strutturato, dove ogni handle rappresenta una configurazione di layout per una determinata pagina o sezione.
    
3. Sostituisce i segnaposto degli URL di base con i valori effettivi.
    

Questo processo garantisce che le modifiche apportate tramite l'estensione dei layout siano integrate correttamente nel sistema.

## Sovrascrivere un Layout in Magento 2

In Magento 2, la sovrascrittura di un layout consente di sostituire completamente un file di layout esistente, sia esso fornito da un modulo di base o da un tema padre. Questo approccio è utile quando le personalizzazioni necessarie non possono essere realizzate estendendo il layout esistente.

### Sovrascrivere Layout di Base

Per sovrascrivere un layout fornito da un modulo di base:

1. **Percorso del file**: crea un file XML con lo stesso nome del layout originale nel seguente percorso del tuo tema:
    `app/design/frontend/<Vendor>/<theme>/<Namespace_Module>/layout/override/base/<layout_file>.xml`
    

Ad esempio, per sovrascrivere `default.xml` del modulo `Magento_Customer`:
`app/design/frontend/ExampleCorp/orange/Magento_Customer/layout/override/base/default.xml`

2. **Contenuto del file**: inserisci nel file solo le istruzioni XML necessarie per la tua personalizzazione.
    

### 🎨 Sovrascrivere Layout di Tema

Per sovrascrivere un layout fornito da un tema padre:

1. **Percorso del file**: crea un file XML con lo stesso nome del layout originale nel seguente percorso del tuo tema figlio:    
    `app/design/frontend/<Vendor>/<theme>/<Namespace_Module>/layout/override/theme/<Parent_Vendor>/<parent_theme>/<layout_file>.xml`
    

Ad esempio, per sovrascrivere `default.xml` del modulo `Magento_Customer` nel tema padre `Magento/luma`:
`app/design/frontend/ExampleCorp/orange/Magento_Customer/layout/override/theme/Magento/luma/default.xml`

2. **Contenuto del file**: inserisci nel file solo le istruzioni XML necessarie per la tua personalizzazione.
    

---

## Considerazioni Importanti

- **Utilizzo appropriato**: la sovrascrittura di layout dovrebbe essere utilizzata solo quando le personalizzazioni non possono essere realizzate estendendo i layout esistenti.
    
- **Manutenzione**: sovrascrivere completamente un layout può rendere più difficile l'aggiornamento del sistema, poiché le modifiche apportate nei file originali non saranno presenti nei file sovrascritti.
    
- **Pulizia della cache**: dopo aver creato o modificato un file di layout, è necessario pulire la cache di Magento per applicare le modifiche:

  `bin/magento cache:clean`
## Cos'è un Template in Magento 2

In Magento 2, i template definiscono la struttura HTML dei blocchi visualizzati nelle pagine del sito. Sono file `.phtml` (PHP) o `.html` (per Knockout.js) che determinano l'output visivo dei blocchi definiti nei layout XML. I template non contengono logica decisionale; la loro inclusione e visibilità sono gestite dai file di layout.[developer.adobe.com+1developer.adobe.com+1](https://developer.adobe.com/commerce/frontend-core/guide/?utm_source=chatgpt.com)

---

## Dove si Trovano i Template

I template possono essere localizzati in due modi:

- **Dichiarazione nel layout XML**: specificando l'attributo `template` all'interno di un blocco.
    
    Esempio:

  `<block class="Magento\Catalog\Block\Category\View" name="category.image" template="Magento_Catalog::category/image.phtml"/>`

- **Dichiarazione nella classe PHP del blocco**: utilizzando la proprietà protetta `$_template`.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/templates/override/?utm_source=chatgpt.com)
    
    Esempio:

  `protected $_template = 'Magento_Review::view.phtml';`

---

## Posizione dei File Template

- **Template di modulo**: `<module_dir>/view/frontend/templates/<path_to_templates>`[developer.adobe.com+3developer.adobe.com+3developer.adobe.com+3](https://developer.adobe.com/commerce/frontend-core/guide/templates/override/?utm_source=chatgpt.com)
    
    Esempio:
      `app/code/Magento/Catalog/view/frontend/templates/product/widget/new/content/new_grid.phtml`

- **Template di tema**: `<theme_dir>/<Namespace>_<Module>/templates/<path_to_templates>`[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/templates/override/?utm_source=chatgpt.com)
    
    Esempio:
  `app/design/frontend/ExampleCorp/orange/Magento_Catalog/templates/product/widget/new/content/new_grid.phtml`

---

## Regole di Override dei Template

Quando esistono file di template con lo stesso nome:

- I template del tema sovrascrivono quelli del modulo.
    
- I template del tema figlio sovrascrivono quelli del tema padre.
    

Per modificare l'output di un template esistente, è consigliabile sovrascrivere il template nel proprio tema personalizzato, evitando modifiche dirette ai file originali.

---

## Template Root

Il file `root.phtml`, situato in `<Magento_Theme_module_dir>/view/base/templates/root.phtml`, è il template principale per tutte le pagine del frontend. Contiene la dichiarazione `<!DOCTYPE>` e definisce le sezioni `<head>` e `<body>` delle pagine. Può essere sovrascritto in un tema come qualsiasi altro file di template.[developer.adobe.com+1developer.adobe.com+1](https://developer.adobe.com/commerce/frontend-core/guide/templates/override/?utm_source=chatgpt.com)

---

##  Accesso agli Argomenti nei Template

Gli argomenti definiti nei file di layout possono essere accessibili nei template tramite i metodi `get{ArgumentName}()` e `has{ArgumentName}()`.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/templates/override/?utm_source=chatgpt.com)

Esempio:

- Nel layout:
    

  `<argument name="store_name" xsi:type="string">ExampleCorp</argument>`

- Nel template:
    

  `$block->getData('store_name');   $block->getStoreName();`

È importante evitare l'istanziazione di nuovi oggetti all'interno dei template; tutti gli oggetti necessari dovrebbero essere passati dal blocco associato.

---

## Personalizzazione dei Template

Per personalizzare un template:

1. Individua il template associato al blocco o alla pagina che desideri modificare.
    
2. Copia il file del template nella directory del tuo tema personalizzato, mantenendo la stessa struttura di directory.
    
3. Apporta le modifiche desiderate al file copiato.
    
4. Pulisci la cache di Magento per applicare le modifiche:
    
    `bin/magento cache:clean`
## Template Email in Magento 2

I template email in Magento 2 sono file HTML che definiscono la struttura e il contenuto delle email transazionali inviate dal sistema, come conferme d'ordine, fatture e notifiche di spedizione. Questi template possono essere personalizzati per riflettere l'identità del brand e migliorare l'esperienza del cliente.

---

## Metodi di Personalizzazione

### 1. **Personalizzazione Basata su Tema**

È possibile sovrascrivere i template email predefiniti creando file con lo stesso nome all'interno della directory del tema personalizzato, seguendo questa struttura:
`app/design/frontend/<Vendor>/<theme>/<ModuleVendor>_<ModuleName>/email/<template_file>.html`

Ad esempio, per sovrascrivere il template `order_new.html` del modulo `Magento_Sales`, il percorso sarà:[developer.adobe.com+1developer.adobe.com+1](https://developer.adobe.com/commerce/frontend-core/guide/templates/email/?utm_source=chatgpt.com)

`app/design/frontend/ExampleCorp/orange/Magento_Sales/email/order_new.html`

Magento utilizza un meccanismo di fallback, cercando i template nell'ordine: tema corrente → tema padre → modulo.

### 2. **Personalizzazione Tramite Admin**

È possibile creare e modificare template email direttamente dal pannello di amministrazione:

1. Navigare su **Marketing > Comunicazioni > Template Email**.
    
2. Cliccare su **Aggiungi Nuovo Template**.
    
3. Nel campo **Carica Template Predefinito**, selezionare il template da modificare e cliccare su **Carica Template**.
    
4. Modificare i campi:
    
    - **Nome Template**: nome identificativo del template.
        
    - **Oggetto Template**: oggetto dell'email.
        
    - **Contenuto Template**: corpo dell'email, dove è possibile inserire variabili e HTML.
        
    - **Stili Template**: CSS inline per lo stile dell'email.
        
5. Salvare il template.
    
6. Per assegnare il nuovo template:
    
    - Navigare su **Store > Configurazione > Vendite > Email di Vendita**.
        
    - Selezionare il tipo di email (es. Ordine) e scegliere il nuovo template dal menu a tendina.
        
    - Salvare la configurazione.[developer.adobe.com+2developer.adobe.com+2developer.adobe.com+2](https://developer.adobe.com/commerce/frontend-core/guide/templates/override/?utm_source=chatgpt.com)[Fiverr.com+8itoris.com+8developer.adobe.com+8](https://www.itoris.com/magento-2-email-templates-manager.html?utm_source=chatgpt.com)[swissuplabs.com+3hungersoft.com+3developer.adobe.com+3](https://www.hungersoft.com/info/magento2-customize-email-templates-using-admin?utm_source=chatgpt.com)
        

---

## Personalizzazione di Header e Footer

I template email includono header e footer tramite le seguenti direttive:

- `{{template config_path="design/email/header_template"}}`
    
- `{{template config_path="design/email/footer_template"}}`[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/templates/email/?utm_source=chatgpt.com)
    

Per personalizzarli:

- **Basato su Tema**: creare i file `header.html` e `footer.html` nella directory `email` del tema personalizzato, seguendo la struttura:

`app/design/frontend/<Vendor>/<theme>/Magento_Email/email/header.html app/design/frontend/<Vendor>/<theme>/Magento_Email/email/footer.html`

- **Tramite Admin**: modificare i file direttamente nel pannello di amministrazione seguendo la procedura descritta nella sezione precedente.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/templates/email/?utm_source=chatgpt.com)
    

---

## Aggiunta del Logo nelle Email

Per aggiungere un logo personalizzato nelle email:

- **Basato su Tema**: posizionare il file del logo (es. `logo_email.png`) nella directory:[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/templates/email/?utm_source=chatgpt.com)

`app/design/frontend/<Vendor>/<theme>/Magento_Email/web/logo_email.png`

- **Tramite Admin**: navigare su **Contenuto > Design > Configurazione**, selezionare il tema desiderato, cliccare su **Modifica** e, nella sezione **Email**, caricare il logo nel campo **Logo Email**.[developer.adobe.com](https://developer.adobe.com/commerce/php/module-reference/module-email/?utm_source=chatgpt.com)
    

Nota: i formati supportati sono JPG, GIF e PNG. È consigliabile utilizzare un'immagine 3 volte più grande delle dimensioni desiderate per garantire una buona qualità su dispositivi ad alta densità di pixel.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/templates/email/?utm_source=chatgpt.com)

---

##  Utilizzo di Variabili nei Template

Magento supporta l'uso di variabili nei template email, che vengono sostituite con valori dinamici al momento dell'invio. Esempi comuni includono:

- `{{var customer.name}}`
    
- `{{var order.increment_id}}`
    
- `{{config path="general/store_information/phone"}}`[developer.adobe.com+2developer.adobe.com+2magetrend.com+2](https://developer.adobe.com/commerce/frontend-core/guide/templates/email-migration/?utm_source=chatgpt.com)[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/templates/email/?utm_source=chatgpt.com)
    

È possibile creare variabili personalizzate navigando su **Sistema > Altre Impostazioni > Variabili Personalizzate**.

---

##  Personalizzazione dello Stile delle Email

Per personalizzare lo stile delle email:

- **CSS Inline**: inserire stili direttamente nel campo **Stili Template** durante la creazione o modifica del template nel pannello di amministrazione.
    
- **LESS nel Tema**: modificare i file LESS nel tema personalizzato, come `_email-extend.less`, per applicare stili globali alle email.
    

Esempio di percorso:

`app/design/frontend/<Vendor>/<theme>/web/css/source/_email-extend.less`

## Cos'è un Layout Handle nelle Email

In Magento 2, i layout handle sono utilizzati nei template email relativi alle vendite (ordini, fatture, spedizioni e note di credito) per rendere sezioni complesse come l'elenco degli articoli ordinati e il riepilogo dei totali.

Ad esempio, nel template `order_new.html`, viene utilizzato il layout handle `sales_email_order_items` per includere l'elenco degli articoli:[Magento Stack Exchange+2developer.adobe.com+2GitHub+2](https://developer.adobe.com/commerce/frontend-core/guide/templates/email-layout-handle/?utm_source=chatgpt.com)

`{{layout handle="sales_email_order_items" order_id=$order_id area="frontend"}}`

Questo handle fa riferimento al file XML `sales_email_order_items.xml`, situato in `app/code/Magento/Sales/view/frontend/layout/`, che definisce la struttura e i blocchi da rendere.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/templates/email-layout-handle/?utm_source=chatgpt.com)

---

## Struttura del Layout Handle

Il file `sales_email_order_items.xml` include:

- Un blocco principale `Magento\Sales\Block\Order\Email\Items` con il template `Magento_Sales::email/items.phtml`.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/templates/email-layout-handle/?utm_source=chatgpt.com)
    
- Un blocco secondario `Magento\Sales\Block\Order\Totals` con il template `Magento_Sales::order/totals.phtml`, che mostra i totali dell'ordine.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/templates/email-layout-handle/?utm_source=chatgpt.com)
    

Questi blocchi sono responsabili della generazione dell'HTML per le sezioni corrispondenti nell'email.

---

## Personalizzazione dei Layout Handle

Per personalizzare l'aspetto delle sezioni rese dai layout handle:

1. **Override dei Template**: Copia i file `.phtml` corrispondenti nel tuo tema personalizzato, mantenendo la stessa struttura di directory, e modifica il layout secondo le tue esigenze.
    
2. **Modifica dei File XML**: Copia il file XML del layout handle nel tuo tema, seguendo la struttura:
   `app/design/frontend/<Vendor>/<theme>/Magento_Sales/layout/sales_email_order_items.xml`

Apporta le modifiche necessarie per personalizzare la struttura dei blocchi.

---

## Considerazioni Importanti

- **Compatibilità**: Assicurati che le personalizzazioni siano compatibili con la struttura dei dati fornita al layout handle.
    
- **Cache**: Dopo aver apportato modifiche ai template o ai layout, pulisci la cache di Magento per applicare le modifiche:

  `bin/magento cache:clean`

- **Aggiornamenti**: Evita di modificare direttamente i file core di Magento per facilitare gli aggiornamenti futuri. Utilizza sempre override nel tema personalizzato.

## Cos'è un ViewModel in Magento 2

Un ViewModel è una classe che funge da intermediario tra il layout XML e il template `.phtml`, fornendo dati e logica al template senza doverli includere direttamente nel blocco. Questo approccio promuove una migliore separazione delle responsabilità, rendendo il codice più modulare, testabile e riutilizzabile.[developer.adobe.com](https://developer.adobe.com/commerce/php/development/components/view-models/?utm_source=chatgpt.com)

---

## Quando Utilizzare i ViewModel

I ViewModel sono disponibili in Adobe Commerce e Magento Open Source dalla versione 2.2 in poi. È consigliabile utilizzarli quando:[developer.adobe.com+8developer.adobe.com+8developer.adobe.com+8](https://developer.adobe.com/commerce/php/development/components/view-models/?utm_source=chatgpt.com)

- Si desidera iniettare funzionalità nei file template senza compromettere la compatibilità retroattiva.
    
- Si vuole evitare l'uso di helper nei template, pratica sconsigliata.[developer.adobe.com](https://developer.adobe.com/commerce/php/development/components/view-models/?utm_source=chatgpt.com)
    
- Si preferisce mantenere la logica di presentazione separata dalla logica di business.
    

Se è necessaria la compatibilità con versioni precedenti a Magento 2.2, è preferibile continuare a utilizzare i blocchi.

---

## Come Scrivere un ViewModel

### 1. **Definizione della Classe ViewModel**

Creare una classe che implementa l'interfaccia `Magento\Framework\View\Element\Block\ArgumentInterface`. Questa classe conterrà i metodi pubblici accessibili dal template.[magecomp.com+2learningmagento.com+2technicallysound.in+2](https://learningmagento.com/useful-of-view-model-in-magento-2/?utm_source=chatgpt.com)
Esempio:

`<?php namespace ExampleCorp\Catalog\ViewModel;  use Magento\Framework\View\Element\Block\ArgumentInterface;  class MyNewViewModel implements ArgumentInterface {     public function getCustomData()     {         return 'Dati personalizzati';     } }`

### 2. **Registrazione nel Layout XML**

Associare il ViewModel a un blocco nel file di layout XML, passando la classe come argomento.[developer.adobe.com+1technicallysound.in+1](https://developer.adobe.com/commerce/php/development/components/view-models/?utm_source=chatgpt.com)

Esempio:

`<block name="examplecorp.new.viewmodel" template="ExampleCorp_Catalog::example.phtml">     <arguments>         <argument name="view_model" xsi:type="object">ExampleCorp\Catalog\ViewModel\MyNewViewModel</argument>     </arguments> </block>`

### 3. **Utilizzo nel Template**

Nel file `.phtml`, accedere ai metodi del ViewModel tramite la variabile `$block->getViewModel()`.

Esempio:

`<?php $viewModel = $block->getViewModel(); echo $viewModel->getCustomData(); ?>`

---

## Considerazioni Aggiuntive

- **Condivisione delle Istanza**: A partire da Magento 2.3.2, le istanze dei ViewModel sono condivise per impostazione predefinita. Per creare una nuova istanza ogni volta, impostare l'attributo `shared="false"` nel layout XML.[technicallysound.in+3developer.adobe.com+3Mage Mastery+3](https://developer.adobe.com/commerce/frontend-core/guide/layouts/xml-manage/?utm_source=chatgpt.com)
    
    Esempio:

  `<argument name="view_model" xsi:type="object" shared="false">ExampleCorp\Catalog\ViewModel\MyNewViewModel</argument>`

- **Posizione dei File**: Seguire la convenzione PSR-4 per la struttura delle directory, posizionando i ViewModel in `app/code/ExampleCorp/Catalog/ViewModel/`.
    
- **Evita l'Uso di Helper nei Template**: L'uso di helper direttamente nei template è sconsigliato. Utilizzare invece i ViewModel per fornire i dati necessari.[developer.adobe.com](https://developer.adobe.com/commerce/php/development/components/view-models/?utm_source=chatgpt.com)

## Cos'è l'XSS

Il Cross-Site Scripting (XSS) è una vulnerabilità che consente agli attaccanti di iniettare codice malevolo (come JavaScript) nelle pagine web visualizzate dagli utenti. In Magento 2, questo può compromettere la sicurezza del sito e dei dati degli utenti.

---

## Tipi di XSS

1. **Persistente (Stored XSS)**: Il codice malevolo viene salvato nel database e mostrato a tutti gli utenti che accedono alla pagina compromessa.
    
2. **Riflesso (Reflected XSS)**: Il codice malevolo viene inviato tramite una richiesta e immediatamente restituito nella risposta, senza essere memorizzato.
    
3. **Basato su DOM (DOM-based XSS)**: Il codice malevolo viene eseguito direttamente nel browser dell'utente, manipolando il Document Object Model (DOM) senza interagire con il server.
    

---

## Prevenzione dell'XSS in Magento 2

### 1. **Validazione e Sanitizzazione dell'Input**

- **Validazione**: Verifica che i dati inseriti dagli utenti rispettino il formato previsto.
    
- **Sanitizzazione**: Rimuove o modifica i caratteri potenzialmente pericolosi dai dati inseriti.
    

È consigliabile eseguire queste operazioni il più vicino possibile al punto in cui i dati vengono utilizzati nella vista (HTML, mobile) per garantire la sicurezza. [developer.adobe.com](https://developer.adobe.com/commerce/php/development/security/cross-site-scripting/?utm_source=chatgpt.com)

### 2. **Escaping dell'Output**

Prima di visualizzare dati dinamici nelle pagine, è fondamentale eseguire l'escaping per evitare l'esecuzione di codice malevolo. Magento 2 fornisce la classe `\Magento\Framework\Escaper` per facilitare questa operazione.

Esempio in un template `.phtml`:

php

CopiaModifica

`<?= $escaper->escapeHtml($data); ?>`

Questo metodo converte i caratteri speciali in entità HTML sicure.[LinkedIn](https://www.linkedin.com/pulse/how-avoid-xss-vulnerabilities-custom-magento-2-modules-role-escapehtml-cfage?utm_source=chatgpt.com)

### 3. **Utilizzo di Metodi di Escaping Specifici**

Magento 2 offre diversi metodi per l'escaping, ognuno adatto a un contesto specifico:

- `escapeHtml()`: Per contenuti HTML.
    
- `escapeUrl()`: Per URL.[Stack Overflow](https://stackoverflow.com/questions/6151296/magento-xss-prevention?utm_source=chatgpt.com)
    
- `escapeJs()`: Per JavaScript.
    
- `escapeCss()`: Per CSS.
    
- `escapeHtmlAttr()`: Per attributi HTML.
    

È importante utilizzare il metodo appropriato in base al contesto per garantire una protezione efficace.

### 4. **Content Security Policy (CSP)**

Implementare una Content Security Policy aiuta a prevenire l'esecuzione di script non autorizzati. Magento 2 supporta la configurazione di CSP per rafforzare la sicurezza del sito.

---

## Esempio Pratico

Supponiamo di voler visualizzare il nome di un cliente inserito tramite un modulo. Per prevenire l'XSS, utilizziamo l'escaping:

php

CopiaModifica

`<?= $escaper->escapeHtml($customerName); ?>`

Questo garantisce che eventuali caratteri speciali nel nome del cliente non vengano interpretati come codice HTML o JavaScript.