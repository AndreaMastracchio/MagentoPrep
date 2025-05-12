---
sticker: emoji//1f980
tags:
  - Magento
  - Frontend
Fonte: https://developer.adobe.com/commerce/frontend-core/guide/themes/
---
## Themes

Un tema in Magento 2 è un componente che definisce l'aspetto visivo dell'applicazione, sia per il **frontend (storefront)** che per il **backend (Admin)**. Utilizza una combinazione di **template personalizzati**, **layout**, **stili CSS/LESS** e **immagini**. I temi possono essere sviluppati da terze parti e distribuiti come pacchetti aggiuntivi, simili ad altri componenti del sistema.

## Temi predefiniti disponibili

Magento 2 offre due temi di base:

- **Luma**: un tema dimostrativo che mostra le capacità del sistema.
    
- **Blank**: una base minimale pensata per lo sviluppo di temi personalizzati.
    
Sebbene sia possibile utilizzare il tema Luma in un negozio live, è fortemente consigliato **non modificare direttamente i file dei temi Luma o Blank**. Le modifiche potrebbero essere sovrascritte durante gli aggiornamenti del sistema. Invece, è preferibile creare un nuovo tema che **erediti** da uno di questi.

## Ereditarietà dei temi

Magento 2 supporta un sistema di **ereditarietà dei temi**, che consente di estendere un tema esistente modificando solo i file necessari. Se un file non viene trovato nel tema corrente, il sistema lo cerca nel tema genitore, nei file di vista del modulo o nella libreria. Questo meccanismo riduce la duplicazione del codice e semplifica la manutenzione.

## Struttura di un tema

Un tema è organizzato in una directory con la seguente struttura:

```

app/design/frontend/<Vendor>/<theme_name>/
├── <Vendor>_<Module>/
│   ├── web/
│   │   ├── css/
│   │   │   ├── source/
│   ├── layout/
│   │   ├── override/
│   ├── templates/
├── etc/
├── i18n/
├── media/
├── web/
│   ├── css/
│   │   ├── source/
│   ├── fonts/
│   ├── images/
│   ├── js/
├── composer.json
├── registration.php
├── theme.xml
```

- `theme.xml`: dichiara il tema e, opzionalmente, il tema genitore.
    
- `registration.php`: registra il tema nel sistema.
    
- `composer.json`: (opzionale) definisce le dipendenze del tema.
    
- `web/`: contiene risorse statiche come CSS, JavaScript, immagini e font.
    
- `i18n/`: include file di traduzione.

## Creazione di un nuovo tema

Per creare un nuovo tema:

1. **Crea la directory del tema**: `app/design/frontend/<Vendor>/<theme_name>/`.
    
2. **Aggiungi `theme.xml`**: definisce il nome del tema e, se necessario, il tema genitore.
    
3. **Aggiungi `registration.php`**: registra il tema nel sistema.
    
4. **(Opzionale) Aggiungi `composer.json`**: per la gestione delle dipendenze.
    
5. **Crea le directory per CSS, JS, immagini e font**: all'interno della cartella `web/`.
    
6. **Applica il tema tramite l'Admin Panel**: naviga su `Content > Design > Configuration`, seleziona lo store view desiderato, clicca su "Edit" e scegli il tuo tema dal menu a tendina "Applied Theme" .


```
<theme xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:Config/etc/theme.xsd">
     <title>Orange</title>
     <parent>Magento/blank</parent>
     <media>
         <preview_image>media/preview.jpg</preview_image>
     </media>
</theme>

```

## Creare un tema per l'area Admin

Per creare un tema personalizzato per l'area di amministrazione di Magento 2, segui questi passaggi:

1. **Crea una directory per il tema**:
    
    Posiziona la nuova directory in `app/design/adminhtml/<Vendor>/<theme>`
    
2. **Aggiungi il file `theme.xml`**:
    
    Definisci le informazioni del tema, come il titolo e il tema padre.
    
3. **Aggiungi `registration.php`**:
    
    Registra il tema nel sistema di Magento.
    
4. **(Facoltativo) Aggiungi `composer.json`**:
    
    Se desideri distribuire il tema tramite Composer.
    
5. **Aggiungi file statici e di layout**:[magecomp.com+2mgt-commerce.com+2mgt-commerce.com+2](https://www.mgt-commerce.com/blog/magento-storefronts/?utm_source=chatgpt.com)
    
    Personalizza l'aspetto dell'area Admin aggiungendo file CSS, JS e layout.

## Applicare un tema Admin

Dopo aver creato il tema, per applicarlo:

1. **Imposta l'applicazione in modalità sviluppatore**:
    
    Questo influisce sul modo in cui i file statici vengono memorizzati nella cache.
    
2. **Crea o modifica un modulo personalizzato**:
    
    Assicurati che il modulo venga caricato dopo `Magento_Theme` aggiungendo una dipendenza nel file `module.xml`.
    
3. **Dichiara il tema nel modulo**
    
    Utilizza il file `di.xml` per specificare il tema da utilizzare per l'area Admin.

## Creare un tema Storefront

Per creare un tema per il frontend (storefront):

1. **Evita di modificare i temi predefiniti**:
    
    Per garantire compatibilità e facilità di manutenzione, crea un nuovo tema invece di modificare quelli esistenti.
    
2. **Imposta l'applicazione in modalità sviluppatore**:
    
    Ciò influisce sulla memorizzazione nella cache dei file statici.
    
3. **Crea la struttura del tema**:
    
    Posiziona la directory del tema in `app/design/frontend/<Vendor>/<theme>` e aggiungi i file necessari come `theme.xml` e `registration.php`.
    
4. **Aggiungi logo e immagini**:
    
    Personalizza il tema aggiungendo un logo e configurando le dimensioni delle immagini.
## Best practices per lo sviluppo di temi

- **Estendi invece di sovrascrivere**: quando erediti da un tema predefinito, estendi gli stili esistenti invece di sovrascriverli.
    
- **Utilizza file `.xml` per le modifiche di layout**: preferisci la personalizzazione dei file di layout rispetto alla modifica diretta dei template `.phtml`.
    
- **Organizza i file CSS/LESS**: mantieni i file CSS/LESS modulari per facilitare la manutenzione.
    
- **Utilizza `view.xml` per configurare le proprietà delle immagini**: definisci dimensioni e tipi di immagini nel file `view.xml` .
    
- **Mantieni il testo traducibile**: utilizza la funzione `__()` per rendere il testo disponibile per la traduzione.
    
- **Adotta un approccio mobile-first**: assicurati che il design sia responsive e ottimizzato per dispositivi mobili.

## Strumenti per lo sviluppo

- **Modalità sviluppatore**: attiva la modalità sviluppatore con il comando `bin/magento deploy:mode:set developer` per facilitare il debug.
    
- **Grunt**: utilizza Grunt per la compilazione di file LESS e il live reload durante lo sviluppo.
    
- **Pulizia della cache**: dopo le modifiche, pulisci la cache e i file statici per vedere le modifiche applicate.

## Debugging di Template, Layout e Stili in Magento 2

### Template

Per identificare il file `.phtml` responsabile di una specifica sezione del frontend o dell'Admin:

- **Abilitare i Template Hints**:
    
    - Naviga su `Stores > Settings > Configuration > ADVANCED > Developer`.
        
    - Seleziona lo scope desiderato (es. Store View).
        
    - Nella scheda **Debug**, imposta **Template Path Hints** su `Yes`.
        
    - Salva la configurazione.
        
- **Utilizzare la CLI**:
    
    - Abilita: `bin/magento dev:template-hints:enable`
        
    - Disabilita: `bin/magento dev:template-hints:disable`
        
    - Pulisci la cache: `bin/magento cache:clean config full_page`
        
- **Visualizzazione**:
    
    - Ricarica la pagina con `?templatehints=magento` nell'URL per vedere i percorsi dei template.
        
- **Alternativa**:
    
    - Utilizza strumenti di sviluppo del browser per identificare classi CSS o testi specifici e cerca nei file `.phtml` corrispondenti nel filesystem.
        

###  Layout

Per individuare il file di layout (`.xml`) associato a un componente:

1. **Identifica il modulo** a cui appartiene il template (es. `Magento_Checkout`).
    
2. **Percorso dei layout**:
    
    - `<current_theme_dir>/<Namespace>_<Module>/layout/`
        
    - `<parent_theme_dir>/<Namespace>_<Module>/layout/`
        
    - `<module_dir>/view/frontend/layout/`
        
    - `<module_dir>/view/base/layout/`
        
3. **Esempio**:
    
    - Per il minicart, il layout si trova in `app/code/Magento/Checkout/view/frontend/layout/default.xml`.

## Aggiungere favicon personalizzate

Per aggiungere una favicon personalizzata:

1. **Tramite Admin**:
    
    Carica un'icona personalizzata nel pannello di amministrazione.
    
2. **Manuale**:[mgt-commerce.com+17tigren.com+17marcgento.com+17](https://www.tigren.com/blog/create-new-admin-user-magento-2/?utm_source=chatgpt.com
    
    Aggiungi l'icona nella directory del tema e definiscila nel layout.
    

Magento supporta vari formati di file per le favicon, tra cui `.ico`, `.png`, `.gif`, `.jpg`, `.jpeg`, `.apng` e `.svg`. Tuttavia, il formato `.ico` è il più ampiamente supportato dai browser.

## Configurare le proprietà del tema

Le proprietà delle immagini dei prodotti utilizzate nel frontend sono memorizzate nel file `view.xml` del tema. Questo file consente di configurare le dimensioni delle immagini, le opzioni della galleria e altre impostazioni relative alla visualizzazione dei prodotti.


```
<images module="Magento_Catalog">
    <image id="unique_image_id" type="image">
        <width>100</width> <!-- Image width in px -->
        <height>100</height> <!-- Image height in px -->
    </image>
</images>
```

## Configurare i video dei prodotti

È possibile aggiungere video da risorse esterne (attualmente, da YouTube e Vimeo) nelle pagine dei prodotti. I video vengono aggiunti tramite l'Admin durante la creazione o la modifica di un prodotto. Alcune opzioni dei video dei prodotti possono essere impostate nel file di configurazione `config.xml` di un modulo personalizzato, come:

- `play_if_base`: riproduzione automatica al caricamento della pagina.
    
- `show_related`: visualizzazione di video correlati.
    
- `video_auto_restart`: riproduzione automatica in loop.

## Bundling JavaScript

Il bundling di JavaScript in Magento 2 consente di combinare più file JS in un unico file, riducendo il numero di richieste HTTP e migliorando le prestazioni del sito. Questa funzionalità può essere configurata per ottimizzare il caricamento delle pagine, specialmente in ambienti di produzione.

## Localizzazione in Adobe Commerce tramite CLI

### Cos'è la localizzazione?

La localizzazione in Adobe Commerce consente di adattare l'interfaccia utente e i contenuti del tuo store per diverse lingue e regioni. Questo processo include la traduzione di testi, etichette, messaggi di sistema e altri elementi dell'interfaccia.

## Generare un dizionario di traduzione

Per personalizzare o tradurre stringhe esistenti, puoi generare un dizionario di traduzione (file CSV) utilizzando il comando:

```
bin/magento i18n:collect-phrases [-o|--output=\"<percorso/nome_file.csv>\"] [-m|--magento] <percorso_directory>
```

- `<percorso_directory>`: Directory contenente i file da cui estrarre le frasi traducibili (PHP, PHTML, XML).
    
- `-o`: Specifica il percorso e il nome del file CSV di output.
    
- `-m`: Include informazioni su moduli e temi nelle frasi raccolte (necessario per creare un pacchetto lingua).
    

**Linee guida per la traduzione:**

- Modifica solo la seconda colonna del file CSV, traducendo le frasi dall'inglese alla lingua desiderata.
    
- Mantieni intatti i segnaposto come `%1`, `%2`, ecc., assicurandoti che siano presenti nella traduzione.

## Creare un pacchetto lingua

Un pacchetto lingua consente di tradurre l'intera applicazione o specifici componenti. Per crearlo:

1. **Raccogli e traduci le frasi:**

```
bin/magento i18n:collect-phrases -o \"<percorso/xx_YY.csv>\" -m
```

`xx_YY`: Codice locale (es. `it_IT` per italiano).

2. Crea il pacchetto lingua:

```
bin/magento i18n:pack <percorso/xx_YY.csv> <locale>
```

- - `<locale>`: Codice locale (es. `it_IT`).

3. **Struttura del pacchetto:**

- Directory: `app/i18n/<Vendor>/<package>`
    
- File richiesti:
    
    - `composer.json`
        
    - `registration.php`
        
    - `language.xml`

Esempio:

```
<?xml version=\"1.0\"?>
<language xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\" xsi:noNamespaceSchemaLocation=\"urn:magento:framework:App/Language/package.xsd\">
    <code>it_IT</code>
    <vendor>mio_vendor</vendor>
    <package>it_it</package>
    <sort_order>100</sort_order>
</language>
```

## Ereditarietà dei pacchetti lingua

È possibile creare pacchetti lingua che ereditano da altri, specificando i pacchetti padre nel file `language.xml`. Questo permette di sovrascrivere solo alcune traduzioni, mantenendo le altre dal pacchetto padre.


```
<use vendor=\"padre_vendor\" package=\"padre_pacchetto\"/>
```

## Esempi pratici

### Creare un dizionario di traduzione per un modulo:

`bin/magento i18n:collect-phrases -o \"app/code/MioVendor/MioModulo/i18n/it_IT.csv\" app/code/MioVendor/MioModulo`

### ✅ Creare un pacchetto lingua completo:

`bin/magento i18n:collect-phrases -o \"it_IT.csv\" -m bin/magento i18n:pack it_IT.csv it_IT`

## Utilizzare un dizionario per personalizzare le stringhe

In Magento 2, puoi modificare le stringhe predefinite del tuo tema personalizzato caricando e utilizzando dizionari di traduzione. Questo ti consente di adattare l'interfaccia utente alle esigenze specifiche del tuo store.

### Come l'applicazione applica le localizzazioni

Quando si cambia la lingua di un negozio, l'applicazione cerca e applica le traduzioni nei dizionari corrispondenti seguendo questa sequenza:[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/translations/dictionary/?utm_source=chatgpt.com)

1. Traduzioni del modulo: `<module_dir>/i18n/`
    
2. Pacchetto di traduzione: `app/i18n/`
    
3. Traduzioni del tema:
    
    - `<parent_theme_dir>/i18n/` (iterato attraverso tutti i temi genitori)
        
    - `<current_theme_dir>/i18n/`
        
4. Database (le traduzioni presenti nel database hanno la precedenza e sovrascrivono le traduzioni memorizzate in altre posizioni).[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/translations/dictionary/?utm_source=chatgpt.com)
    

La priorità delle traduzioni segue l'ordine inverso, con le traduzioni del database che hanno la priorità più alta e le traduzioni del modulo la più bassa.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/translations/dictionary/?utm_source=chatgpt.com)

### Sovrascrivere le stringhe del tema genitore per la lingua predefinita

La priorità delle traduzioni descritta sopra si applica anche alla lingua predefinita `en_US`. Puoi quindi utilizzare il file `en_US.csv` per personalizzare le stringhe utilizzate nella lingua predefinita.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/translations/dictionary/?utm_source=chatgpt.com)

Ad esempio, nel tema Luma, il file `<Magento_Luma_theme_dir>/i18n/en_US.csv` contiene le seguenti modifiche:[developer.adobe.com+1developer.adobe.com+1](https://developer.adobe.com/commerce/frontend-core/guide/translations/dictionary/?utm_source=chatgpt.com)


```
`"Add to Wish List", "Wish List" "Add to Compare", "Compare" "Your Checkout Progress", "Checkout Progress" "Card Verification Number", "CVV"`
```

È importante ricordare che se generi un dizionario per il tuo tema utilizzando lo strumento i18n con i nomi e le posizioni convenzionali per il dizionario, il dizionario esistente verrà sovrascritto.

Per aggiungere stringhe personalizzate:

1. Genera il dizionario per il tuo tema.
    
2. Modifica i valori necessari nella colonna di destra.
    
3. Aggiungi stringhe personalizzate come nuove righe se le stringhe che desideri sostituire non sono presenti nel dizionario.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/translations/dictionary/?utm_source=chatgpt.com)
    

Lo strumento i18n non crea un dizionario se i file del tema non contengono stringhe da tradurre. In questo caso, aggiungi manualmente il file.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/translations/dictionary/?utm_source=chatgpt.com)

###  Creare dizionari per altre lingue

Quando crei dizionari per altre lingue nel tuo tema, utilizza le stringhe predefinite come chiavi. Non creare traduzioni utilizzando le chiavi personalizzate che potresti aver creato e sovrascritto nel tuo dizionario della lingua predefinita.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/translations/dictionary/?utm_source=chatgpt.com)

Continuando l'esempio precedente con il tema Luma, abbiamo cambiato "Add to Wish List" in "Wish List" nel file `en_US.csv`. Nel dizionario `de_DE.csv`, utilizza la chiave originale predefinita "Add to Wish List" per inserire la tua traduzione. Non utilizzare il valore personalizzato "Wish List" per le traduzioni.[developer.adobe.com+6developer.adobe.com+6developer.adobe.com+6](https://developer.adobe.com/commerce/frontend-core/guide/translations/dictionary/?utm_source=chatgpt.com)

Il dizionario della lingua utilizzerà i valori predefiniti (chiavi) nella colonna di sinistra seguiti dalla traduzione:

`"Add to Wish List", "Zur Wunschliste hinzufügen"`

## Gestione delle stringhe di traduzione nei temi Magento 2

Per garantire che tutte le stringhe personalizzate del tuo tema siano correttamente tradotte, è essenziale utilizzare le metodologie appropriate in base al tipo di file in cui le stringhe sono definite.

### 📄Stringhe nei template `.phtml`

- **Metodo**: Utilizza la funzione `__()` per le stringhe statiche e con variabili.
        
    `<?= __('Crea Backup') ?> <?= __('Ciao %1', $tuoValore) ?>`
    

Queste stringhe verranno raccolte dallo strumento i18n durante la generazione del dizionario.

### 📧Stringhe nei template email

- **Metodo**: Usa la direttiva `{{trans}}` per le stringhe nei template email.
       
    `{{trans "Testo dell'email"}} {{trans "%items articoli" items="numItems"}}`
    

Nota: I template email creati tramite l'Admin non vengono salvati nel filesystem e le loro stringhe non vengono aggiunte automaticamente al dizionario.

###  Stringhe nei template dei componenti UI (`.html`)

- **Metodo**: Utilizza i binding `data-bind` con `i18n` o `translate`.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/translations/theory/?utm_source=chatgpt.com)
    
    `<span data-bind="i18n: 'Accedi'"></span> <span translate="'Accedi'"></span>`
    
- **Per stringhe senza elemento HTML**:
    
    `<!-- ko i18n: 'Nessun articolo nel carrello.' --><!-- /ko --> <translate args="'Nessun articolo nel carrello.'"/>`
    
- **Per attributi HTML**:
        
    `<input type="text" data-bind="attr: {placeholder: $t('Nome')}"/>`
    

### Stringhe nei file di configurazione XML dei componenti UI

- **Metodo**: Aggiungi l'attributo `translate="true"` agli elementi stringa.
    
    `<item name="label" xsi:type="string" translate="true">Elimina</item>`
    

Per rendere effettiva la traduzione, richiama la stringa nel codice PHP:

php

CopiaModifica

`__($this->config->getData('label'))`

### Stringhe nei template Underscore (`.html`)

- **Metodo**: Usa la funzione `_.i18n()` per le stringhe.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/translations/theory/?utm_source=chatgpt.com)
    
    `<%= _.i18n('Ciao') %> <%= _.i18n('Ciao %1').replace('%1', tuoValore) %>`
    

### Stringhe nei file JavaScript (`.js`)

- **Metodo**: Includi la libreria `mage/translate` e utilizza `$t()` o `$.mage.__()`.[developer.adobe.com](https://developer.adobe.com/commerce/frontend-core/guide/translations/theory/?utm_source=chatgpt.com)
    
    `define(['jquery', 'mage/translate'], function ($, $t) {     $t('Testo da tradurre');     $.mage.__('Testo da tradurre');     $t('Ciao %1').replace('%1', tuoValore);`