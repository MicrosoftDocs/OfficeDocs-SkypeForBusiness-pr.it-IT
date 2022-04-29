---
title: Pianificare e gestire le chiamate di emergenza
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: Informazioni sulle chiamate di emergenza, incluse le informazioni su indirizzi di emergenza, routing delle chiamate di emergenza e chiamate di emergenza dinamiche.
ms.openlocfilehash: f059f55281df2925511b85941fefbb675d781852
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125451"
---
# <a name="manage-emergency-calling"></a>Gestire le chiamate di emergenza

Questo articolo descrive i concetti che è necessario conoscere per gestire le chiamate&mdash; di emergenza, include informazioni su indirizzi di emergenza, indirizzi dinamici per gli interventi di emergenza e routing delle chiamate di emergenza. Questo articolo usa la terminologia seguente:

- **Indirizzo per gli interventi di emergenza** : indirizzo&mdash; civicoI'indirizzo fisico o stradale di un luogo di lavoro per l'organizzazione.

  Ad esempio, l'indirizzo *12345 North Main Street, Redmond, WA 98052* viene utilizzato per instradare le chiamate di emergenza alle autorità di emergenza appropriate e per facilitare l'individuazione del chiamante di emergenza.

- **Luogo** : in genere un piano, un edificio, un'ala o un numero di ufficio. Il luogo è associato a un indirizzo per gli interventi di emergenza per fornire una posizione più esatta all'interno di un edificio. Puoi associare un numero illimitato di luoghi a un indirizzo per gli interventi di emergenza. Ad esempio, se l'organizzazione ha più edifici, è consigliabile includere le informazioni sulla posizione di ogni edificio e di ogni piano all'interno di ogni edificio.  

- **Posizione per gli interventi di emergenza** : una posizione è un indirizzo&mdash; civico con un luogo facoltativo. Se la tua azienda ha più posizioni fisiche, è probabile che ti serviranno più posizioni per gli interventi di emergenza. 

  Quando crei un indirizzo per gli interventi di emergenza, viene creato automaticamente un ID posizione univoco per questo indirizzo. Se ad esempio aggiungi un luogo a un indirizzo&mdash; per gli interventi di emergenza, se aggiungi un piano a un indirizzo&mdash; dell'edificio viene creato un ID posizione per la combinazione dell'indirizzo e del luogo per gli interventi di emergenza.  In questo esempio saranno presenti due ID posizione: uno per l'indirizzo civico; per l'indirizzo civico aggiunto e il luogo associato.

  Quando assegni una posizione per gli interventi di emergenza a un utente o a un sito, l'ID posizione univoco è associato all'utente o al sito.

- **Indirizzo registrato** : indirizzo per gli interventi di emergenza assegnato a ogni utente. Un indirizzo registrato viene a volte definito indirizzo di emergenza statico o indirizzo record. Attualmente, gli indirizzi registrati non sono supportati per il routing diretto. Ricontrollare presto per verificare la disponibilità di aggiornamenti.

>[!Note]
>Esistono alcune differenze nella gestione delle chiamate di emergenza a seconda che usi i Piani per chiamate Microsoft, Connessione con operatore o Routing diretto per la [connettività PSTN](pstn-connectivity.md). Queste considerazioni sono descritte in questo articolo.

## <a name="emergency-address-validation"></a>Convalida dell'indirizzo di emergenza

Per assegnare un indirizzo per gli interventi di emergenza a un utente o a un identificatore di rete, è necessario verificare che l'indirizzo per gli interventi di emergenza sia contrassegnato come "convalidato". La convalida dell'indirizzo garantisce la legittimità dell'indirizzo e non può essere modificato dopo l'assegnazione. 

Se definisci un indirizzo per gli interventi di emergenza utilizzando la funzionalità di ricerca della mappa degli indirizzi nell'interfaccia di amministrazione di Teams, l'indirizzo viene contrassegnato automaticamente come convalidato. Poiché non è possibile modificare un indirizzo&mdash; per gli interventi di emergenza convalidato se cambia il formato o la rappresentazione dell'indirizzo, è necessario creare un nuovo indirizzo con il formato aggiornato.


## <a name="emergency-address-geo-codes"></a>Codici geografici degli indirizzi di emergenza

A ogni indirizzo di emergenza può essere associato un codice geografico (latitudine e longitudine). Questi codici geografici vengono utilizzati in alcuni paesi per facilitare il routing delle chiamate di emergenza con posizioni dinamiche. 

Se definisci un indirizzo per gli interventi di emergenza utilizzando la funzionalità di ricerca della mappa degli indirizzi nell'interfaccia di amministrazione di Teams, il codice geografico viene associato automaticamente a un indirizzo per gli interventi di emergenza. È anche possibile associare codici geografici a un indirizzo se si definisce l'indirizzo usando PowerShell. 

Microsoft consiglia di creare indirizzi per gli interventi di emergenza usando la funzionalità di ricerca mappa nell Teams a interfaccia di amministrazione, in modo da garantire che gli indirizzi siano formattati, convalidati e dispongano dei codici geografici appropriati. 

>[!Important]
>Per assegnare una posizione di emergenza a un identificatore di rete per le chiamate di emergenza dinamiche, l'indirizzo di emergenza deve contenere un codice geografico appropriato.


## <a name="considerations-for-calling-plans"></a>Considerazioni per i piani per chiamate

Le sezioni seguenti descrivono come gestire le chiamate di emergenza per gli utenti del piano per chiamate Microsoft. Per scoprire se i Piani per chiamate Microsoft sono la soluzione giusta per la tua azienda, vedi [Opzioni di connettività PSTN](pstn-connectivity.md).


### <a name="emergency-call-enablement-for-calling-plans"></a>Abilitazione delle chiamate di emergenza per i piani per chiamate

Ogni utente del Piano per chiamate viene abilitato automaticamente per le chiamate di emergenza ed è richiesto di avere un indirizzo di emergenza registrato associato al numero di telefono assegnato. 

Quando la località è associata al numero di telefono dipende dal paese/area geografica:

- Nel Stati Uniti e in Canada, ad esempio, è necessaria una posizione per gli interventi di emergenza quando un numero viene assegnato a un utente.

- Per altri paesi&mdash;, come in Europa, Medio Oriente e Africa (EMEA)&mdash; è necessaria una posizione per gli interventi di emergenza quando si ottiene il numero di telefono da Microsoft 365 o quando viene trasferito da un altro provider di servizi o gestore.


### <a name="dynamic-emergency-calling-for-calling-plans"></a>Chiamate di emergenza dinamiche per i piani per chiamate

Le chiamate di emergenza dinamiche per i Piani per chiamate offrono la possibilità di configurare e instradare le chiamate di emergenza in base alla posizione corrente del client Teams. La possibilità di eseguire il routing automatico al punto di risposta per la sicurezza pubblica appropriato (PSAP) o di inviare notifiche al personale del security desk varia a seconda del paese di utilizzo dell'utente Teams.  

La posizione dinamica per il routing delle chiamate di emergenza è supportata nel Stati Uniti come indicato di seguito. 

- Se un client Teams per un Stati Uniti utente del Piano per chiamate acquisisce dinamicamente un indirizzo per gli interventi di emergenza all'interno del Stati Uniti, tale indirizzo viene utilizzato per il routing di emergenza al posto dell'indirizzo registrato e la chiamata verrà automaticamente instradata al PSAP nell'area di servizio dell'indirizzo.

- Se un client di Teams per un utente del Piano per chiamate Stati Uniti non acquisisce dinamicamente un indirizzo per gli interventi di emergenza all'interno del Stati Uniti, l'indirizzo per gli interventi di emergenza registrato viene usato per facilitare lo schermo e instradare la chiamata. Tuttavia, la chiamata verrà visualizzata per determinare se è necessario un indirizzo aggiornato prima di connettere il chiamante al PSAP appropriato.

La posizione dinamica per il routing delle chiamate di emergenza è supportata in Canada come nella Stati Uniti con la seguente eccezione: tutte le chiamate di emergenza verranno sottoposte a controllo nazionale prima di essere trasferite al PSAP.

Per ulteriori informazioni, vedi [Pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-calling-plans"></a>Routing delle chiamate di emergenza per i piani per chiamate

Quando un utente di un piano di chiamata Teams compone un numero di emergenza, il modo in cui la chiamata viene instradata al PSAP dipende da quanto segue:

- Se l'indirizzo per gli interventi di emergenza è determinato dinamicamente dal client Teams.

- Indica se l'indirizzo per gli interventi di emergenza è l'indirizzo registrato associato al numero di telefono dell'utente.

- La rete di chiamate di emergenza di quel paese.

Ad esempio:

**Nella Stati Uniti:**

- Se un client Teams si trova in una posizione di emergenza dinamica definita dal tenant, le chiamate di emergenza da tale client vengono automaticamente instradate al PSAP che serve tale posizione geografica.

- Se un client Teams non si trova in una posizione di emergenza dinamica definita dal tenant, le chiamate di emergenza da tale client vengono sottoposte a verifica da un call center nazionale per determinare la posizione del chiamante prima di trasferire la chiamata al PSAP che serve tale posizione geografica.

- Se un chiamante di emergenza non è in grado di aggiornare la posizione per gli interventi di emergenza al centro di screening, la chiamata verrà trasferita al PSAP che serve l'indirizzo registrato del chiamante.

**In Canada, Irlanda e Regno Unito**, le chiamate di emergenza vengono prima sottoposte a verifica per determinare la posizione corrente dell'utente prima di collegare la chiamata al centro di emergenza appropriato.

**In Francia, Germania e Spagna**, le chiamate di emergenza vengono instradate direttamente al PSAP che serve l'indirizzo per gli interventi di emergenza associato al numero, indipendentemente dalla posizione del chiamante.

**Nei Paesi Bassi**, le chiamate di emergenza vengono indirizzate direttamente al PSAP per il prefisso locale del numero, indipendentemente dalla posizione del chiamante.

**In Australia**, gli indirizzi di emergenza sono configurati e instradati dal partner del vettore.

**In Giappone**, le chiamate di emergenza non sono supportate.


Per ulteriori informazioni, vedere:

- [Piani di chiamata](calling-plan-landing-page.md)
- [Configurare i piani per chiamate](set-up-calling-plans.md)
- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-operator-connect"></a>Considerazioni per Connessione con operatore

Le sezioni seguenti descrivono come gestire le chiamate di emergenza per Connessione con operatore utenti. Per scoprire se Connessione con operatore è la soluzione giusta per la tua azienda, vedi [Opzioni di connettività PSTN](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-operator-connect"></a>Abilitazione delle chiamate di emergenza per Connessione con operatore

Ogni utente Connessione con operatore viene abilitato automaticamente per le chiamate di emergenza. Le chiamate di emergenza vengono instradate automaticamente al gestore Connessione con operatore per un determinato numero.

La possibilità per un amministratore tenant di impostare l'indirizzo registrato per un utente Connessione con operatore dipenderà dalle funzionalità assegnate al numero quando il gestore lo carica in un inventario clienti. In base a questa impostazione, l'amministratore del tenant potrebbe essere richiesto&mdash; o meno oppure essere in grado&mdash; di impostare, modificare o eliminare la posizione per gli interventi di emergenza di un utente. 

### <a name="dynamic-emergency-calling-for-operator-connect"></a>Chiamate di emergenza dinamiche per Connessione con operatore

Le chiamate di emergenza dinamiche per Connessione con operatore offrono la possibilità di configurare e instradare le chiamate di emergenza in base alla posizione corrente del client Teams. La possibilità di eseguire il routing automatico al punto di risposta per la sicurezza pubblica appropriato (PSAP) o di inviare notifiche al personale del security desk varia a seconda del paese di utilizzo dell'utente Teams. 

La posizione dinamica per il routing delle chiamate di emergenza è supportata nel Stati Uniti come indicato di seguito. 

- Se un client di Teams per un Stati Uniti utente acquisisce dinamicamente un indirizzo per gli interventi di emergenza all'interno del Stati Uniti, tale indirizzo viene utilizzato per il routing di emergenza al posto dell'indirizzo registrato e la chiamata verrà automaticamente instradata al PSAP nell'area di servizio dell'indirizzo.

- Se un client di Teams per un Stati Uniti utente non acquisisce dinamicamente un indirizzo per gli interventi di emergenza all'interno del Stati Uniti, l'indirizzo per gli interventi di emergenza registrato viene usato per facilitare lo schermo e il routing della chiamata. Tuttavia, la chiamata verrà visualizzata per determinare se è necessario un indirizzo aggiornato prima di connettere il chiamante al PSAP appropriato.

La posizione dinamica per il routing delle chiamate di emergenza è supportata in Canada come nella Stati Uniti con le seguenti eccezioni: tutte le chiamate di emergenza verranno sottoposte a controllo nazionale prima di essere trasferite al PSAP.

Per ulteriori informazioni, vedi [Pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-operator-connect"></a>Routing delle chiamate di emergenza per Connessione con operatore

Quando un utente Teams Connessione con operatore compone un numero di emergenza, il modo in cui la chiamata viene instradata al PSAP dipende da quanto segue:

- Se l'indirizzo per gli interventi di emergenza è determinato dinamicamente dal client Teams.

- Indica se l'indirizzo per gli interventi di emergenza è l'indirizzo registrato associato al numero di telefono dell'utente.

- La rete di chiamate di emergenza di quel paese.

- Nel Stati Uniti e in Canada, il routing dinamico fa parte del servizio del vettore. Non è necessario ottenere questo servizio da un altro provider di servizi.

- Se un client Teams si trova in una posizione di emergenza dinamica definita dal tenant:

   - Nel Stati Uniti, le chiamate di emergenza da quel client vengono automaticamente instradate al PSAP che serve quella posizione geografica.
   - In Canada, tutte le chiamate di emergenza verranno schermate da un call center nazionale prima di trasferire la chiamata al PSAP che serve quella posizione geografica.

- Se un client Teams non si trova in una posizione di emergenza dinamica definita dal tenant, le chiamate di emergenza da tale client vengono sottoposte a verifica da un call center nazionale per determinare la posizione del chiamante prima di trasferire la chiamata al PSAP che serve tale posizione geografica.

- Se un chiamante di emergenza non è in grado di aggiornare la posizione per gli interventi di emergenza al centro di screening, la chiamata verrà trasferita al PSAP che serve l'indirizzo registrato del chiamante.


## <a name="considerations-for-direct-routing"></a>Considerazioni per il routing diretto

Le sezioni seguenti descrivono come gestire le chiamate di emergenza per gli utenti del routing diretto. Per scoprire se il routing diretto è la soluzione giusta per la tua azienda, vedi [Opzioni di connettività PSTN](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-direct-routing"></a>Abilitazione delle chiamate di emergenza per il routing diretto

Per il routing diretto, è necessario definire i criteri per le chiamate di emergenza per gli utenti utilizzando un [criterio di routing delle chiamate di emergenza Teams](manage-emergency-call-routing-policies.md) per definire i numeri di emergenza e la destinazione di routing associata. Attualmente, le posizioni per gli interventi di emergenza registrate non sono supportate per gli utenti del routing diretto.

È possibile assegnare un criterio di routing delle chiamate di emergenza a un account utente Routing diretto, a un sito di rete o a entrambi. Quando un client Teams avvia o modifica una connessione di rete, Teams esegue una ricerca del sito di rete in cui si trova il client nel modo seguente:

- Se al sito è associato un criterio di routing delle chiamate di emergenza, i criteri del sito vengono usati per configurare le chiamate di emergenza.

- Se al sito non sono associati criteri di routing delle chiamate di emergenza, se il client è connesso a un sito non definito o se il numero composto non corrisponde a nessuno dei numeri di emergenza definiti nei criteri di routing delle chiamate di emergenza associati al sito, i criteri di routing delle chiamate di emergenza associati all'account utente vengono usati per configurare le chiamate di emergenza. 

- Se il client Teams non è in grado di ottenere un criterio di routing delle chiamate di emergenza, l'utente non è abilitato per le chiamate di emergenza.


### <a name="dynamic-emergency-calling-for-direct-routing"></a>Chiamate di emergenza dinamiche per il routing diretto

Le chiamate di emergenza dinamiche per il routing diretto offrono la possibilità di configurare e instradare le chiamate di emergenza in base alla posizione corrente del client Teams. La possibilità di eseguire il routing automatico al punto di risposta per la sicurezza pubblica appropriato (PSAP) o di inviare notifiche al personale del security desk varia a seconda del paese di utilizzo dell'utente Teams.

Per gli utenti di Direct Routing, la posizione dinamica per il routing delle chiamate di emergenza è supportata solo nel Stati Uniti come indicato di seguito:

-   Se un client di Teams per un utente Stati Uniti Direct Routing acquisisce dinamicamente un indirizzo per gli interventi di emergenza all'interno del Stati Uniti, tale indirizzo viene utilizzato per il routing di emergenza e la chiamata verrà automaticamente instradata al PSAP nell'area di porzione dell'indirizzo.

-   Se un client Teams per un utente Stati Uniti Direct Routing non acquisisce dinamicamente un indirizzo per gli interventi di emergenza all'interno del Stati Uniti, la chiamata verrà visualizzata per determinare se è necessario un indirizzo aggiornato prima di connettere il chiamante al PSAP appropriato.

La posizione dinamica per il routing delle chiamate di emergenza è supportata in Canada come nella Stati Uniti con la seguente eccezione: tutte le chiamate di emergenza verranno sottoposte a controllo nazionale prima di essere trasferite al PSAP.

Per ulteriori informazioni, vedi [Configurare le chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-direct-routing"></a>Routing delle chiamate di emergenza per il routing diretto

Il criterio di routing delle chiamate di emergenza per routing diretto fa riferimento a un utilizzo PSTN online, che deve disporre della configurazione di routing diretto appropriata per instradare correttamente le chiamate di emergenza ai gateway PSTN appropriati. In particolare, è necessario assicurarsi che sia disponibile onlineVoiceRoute per la stringa di chiamata di emergenza. Per altre informazioni, vedere [Configurare il routing diretto](direct-routing-configure.md). 

> [!NOTE]
> Teams client non antepone più il segno "+" davanti ai numeri di emergenza, ovvero +911. Di conseguenza, Teams chiamate di emergenza non invieranno più un segno "+" prima del numero 911. Assicurarsi che i modelli di itinerario vocale riflettano questa modifica.

La possibilità di instradare dinamicamente le chiamate di emergenza per gli utenti di Routing diretto varia a seconda della rete di chiamate di emergenza all'interno di un determinato paese. Sono disponibili due soluzioni:

- [Provider di servizi di routing di emergenza (solo Stati Uniti)](#emergency-routing-service-providers)
- [Applicazioni per il numero di identificazione della posizione di emergenza](#emergency-location-identification-number-applications)

#### <a name="emergency-routing-service-providers"></a>Provider di servizi di routing di emergenza

Nel Stati Uniti sono presenti numerosi operatori del servizio di instradamento di emergenza certificati che possono instradare automaticamente le chiamate di emergenza in base alla posizione del chiamante.

- Se un provider di servizi di routing di emergenza è integrato in una distribuzione di routing diretto, le chiamate di emergenza con una posizione acquisita dinamicamente verranno automaticamente instradate al punto di risposta per la sicurezza pubblica (PSAP) che serve tale posizione.

-  Le chiamate di emergenza senza una posizione acquisita dinamicamente vengono prima sottoposte a verifica per determinare la posizione corrente dell'utente prima di collegare la chiamata al centro di emergenza appropriato in base alla posizione aggiornata.

Per ulteriori informazioni, vedi [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).


#### <a name="emergency-location-identification-number-applications"></a>Applicazioni per il numero di identificazione della posizione di emergenza

I controller dei confini della sessione possono includere applicazioni ELIN (Emergency Location Identification Number). Se un'applicazione SBC ELIN è integrata in una distribuzione direct routing, è necessario configurare gli indirizzi di emergenza e i numeri di telefono associati nell'applicazione ELIN, quindi caricare i record ELIN nel database delle chiamate di emergenza nel rispettivo PSTN. Teams posizioni per gli interventi di emergenza con un identificatore ELIN devono corrispondere a quelle presenti nell'applicazione ELIN.

Quando una chiamata di emergenza con una posizione acquisita dinamicamente viene instradata all'SBC appropriato, l'applicazione ELIN:

- Analizza la posizione di emergenza del chiamante.
- Corrisponde alla posizione di un record ELIN.
- Sostituisce il numero del chiamante di emergenza con il numero di telefono ELIN.
- Instrada la chiamata al PSAP che serve tale posizione, quindi i dispatcher ottengono la posizione dal record ELIN caricato.

Quando si richiama il numero di emergenza, l'applicazione ELIN esegue la sostituzione del numero inversa chiamata sostituzione a quella del chiamante di emergenza originale. 

Per ulteriori informazioni, vedi [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).


## <a name="security-desk-notification"></a>Notifica del desk di sicurezza

La notifica security desk è disponibile sia con i piani per chiamate Microsoft, Connessione con operatore che con routing diretto.

Si usa un criterio per le chiamate di emergenza Teams (TeamsEmergencyCallingPolicy) per configurare chi deve ricevere una notifica durante una chiamata di emergenza e la modalità di notifica: solo chat, conferenze in entrata e disattivate o conferenze in entrata e disattivate, ma con la possibilità di riattivare l'audio. È anche possibile specificare un numero PSTN esterno di un utente o di un gruppo per chiamare e partecipare alla chiamata di emergenza. Si noti che la parte PSTN non è autorizzata a riattivare l'audio.

I criteri per le chiamate di emergenza possono essere concessi a un account utente Teams, assegnato a un sito di rete o a entrambi.  Quando un client Teams avvia o modifica una connessione di rete, Teams esegue una ricerca del sito di rete in cui si trova il client:

- Se un criterio per le chiamate di emergenza è associato a un sito di rete, i criteri del sito vengono usati per configurare la notifica security desk.

- Se al sito non sono associati criteri per le chiamate di emergenza o se il client è connesso a un sito non definito, i criteri per le chiamate di emergenza associati all'account utente vengono usati per configurare la notifica del security desk.  

- Se il client Teams non è in grado di ottenere criteri per le chiamate di emergenza, l'utente non è abilitato per la notifica security desk.

Durante una chiamata di emergenza, un security desk viene collegato alla chiamata e l'esperienza dell'utente del security desk è controllata in base ai criteri per le chiamate di emergenza Teams. Viene avviata una chat di gruppo con ogni membro del desk di sicurezza e la posizione del chiamante di emergenza viene condivisa tramite una notifica di messaggio importante.  Se un'opzione di conferenza è configurata come parte del criterio, ogni utente del security desk viene chiamato anche come parte della conferenza.

### <a name="custom-emergency-disclaimer"></a>Dichiarazione di non responsabilità personalizzata per gli interventi di emergenza

Gli amministratori hanno la possibilità di aggiungere un banner personalizzato nel tenant per consentire agli utenti di abilitare E911. Gli utenti possono chiudere il banner quando confermano il proprio indirizzo e ricomparirà quando Teams viene riavviato. Per abilitare questa funzionalità, impostare la **dichiarazione di non responsabilità per i servizi di emergenza** in base ai criteri per le chiamate di emergenza Teams e immettere un messaggio stringa da visualizzare agli utenti. Questo campo è facoltativo quando si configurano criteri personalizzati e il campo stringa è limitato a 250 caratteri.

> [!NOTE]
> Attualmente è configurabile usando PowerShell con il criterio EnhancedEmergencyServicesDisclaimer. In futuro questa operazione sarà configurabile anche nell'interfaccia di amministrazione di Teams.

    
## <a name="related-topics"></a>Argomenti correlati

- [Gestire i criteri delle chiamate di emergenza](manage-emergency-calling-policies.md)
- [Gestire i criteri di routing delle chiamate di emergenza ](manage-emergency-call-routing-policies.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Assegnare o modificare una posizione per gli interventi di emergenza per l'utente](assign-change-emergency-location-user.md)
- [Pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md)
