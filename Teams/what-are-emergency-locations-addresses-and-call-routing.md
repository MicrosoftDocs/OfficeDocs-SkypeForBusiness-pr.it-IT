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
description: Informazioni sulle chiamate di emergenza, incluse le informazioni sugli indirizzi di emergenza, il routing delle chiamate di emergenza e le chiamate di emergenza dinamiche.
ms.openlocfilehash: db78ff3b8384cc923daa24f119852240fc1744d6
ms.sourcegitcommit: 2ddbaecb0bb7776dc5ab88727b1335e7e46d3704
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/17/2022
ms.locfileid: "62881521"
---
# <a name="manage-emergency-calling"></a>Gestire le chiamate di emergenza

Questo articolo descrive i concetti&mdash; che è necessario conoscere per gestire le chiamate di emergenza, incluse informazioni sugli indirizzi di emergenza, gli indirizzi di emergenza dinamici e il routing delle chiamate di emergenza. Questo articolo usa la terminologia seguente:

- **Indirizzo di emergenza** : indirizzo civicol'indirizzo&mdash; fisico o stradale di un luogo di lavoro per l'organizzazione.

  Ad esempio, l'indirizzo *12345 North Main Street, Redmond, WA 98052* viene usato per instradare le chiamate di emergenza alle autorità di spedizione appropriate e per facilitare l'individuazione del chiamante di emergenza.

- **Luogo** : in genere un piano, un edificio, un'ala o un numero di ufficio. Luogo è associato a un indirizzo di emergenza per fornire una posizione più esatta all'interno di un edificio. È possibile avere un numero illimitato di posizioni associate a un indirizzo per gli interventi di emergenza. Ad esempio, se l'organizzazione ha più edifici, è consigliabile includere informazioni sul luogo per ogni edificio e per ogni piano all'interno di ogni edificio.  

- **Luogo per gli interventi** di emergenza: una località è un indirizzo civico&mdash; con un luogo facoltativo. Se l'azienda ha più di una posizione fisica, è probabile che siano necessarie più località di emergenza. 

  Quando si crea un indirizzo per gli interventi di emergenza, per questo indirizzo viene creato automaticamente un ID località univoco. Se ad esempio si aggiunge un luogo a&mdash; un indirizzo per gli interventi di emergenza, se si aggiunge un piano a&mdash; un indirizzo dell'edificio, viene creato un ID posizione per la combinazione dell'indirizzo e del luogo per gli interventi di emergenza.  In questo esempio saranno disponibili due ID località: uno per l'indirizzo civico; uno per l'indirizzo civico unito e il luogo associato.

  Quando si assegna una posizione per gli interventi di emergenza a un utente o a un sito, si tratta di questo ID posizione univoco associato all'utente o al sito.

- **Indirizzo registrato** : indirizzo di emergenza assegnato a ogni utente. Un indirizzo registrato viene talvolta definito indirizzo di emergenza statico o indirizzo del record. Attualmente gli indirizzi registrati non sono supportati per il routing diretto. Torna presto alla ricerca di aggiornamenti.

>[!Note]
>Esistono alcune differenze nel modo in cui si gestiscono le chiamate di emergenza a seconda che si utilizziNo piani per chiamate Microsoft, Connessione con operatore o Routing diretto per la [connettività PSTN](pstn-connectivity.md). Queste considerazioni sono descritte in questo articolo.

## <a name="emergency-address-validation"></a>Convalida dell'indirizzo di emergenza

Per assegnare un indirizzo di emergenza a un utente o a un identificatore di rete, è necessario assicurarsi che l'indirizzo di emergenza sia contrassegnato come "convalidato". La convalida dell'indirizzo assicura che l'indirizzo sia legittimo e che non possa essere modificato dopo l'assegnazione. 

Se si definisce un indirizzo per gli interventi di emergenza usando la funzionalità di ricerca della mappa degli indirizzi nell'interfaccia di amministrazione di Teams, l'indirizzo viene automaticamente contrassegnato come convalidato. Poiché non è possibile modificare un indirizzo di&mdash; emergenza convalidato se il formato o la rappresentazione dell'indirizzo cambia, è necessario creare un nuovo indirizzo con il formato aggiornato.


## <a name="emergency-address-geo-codes"></a>Codici geografici degli indirizzi di emergenza

A ogni indirizzo di emergenza può essere associato un codice geografico (latitudine e longitudine). Questi codici geografici vengono usati in alcuni paesi per facilitare l'instradamento delle chiamate di emergenza con posizioni dinamiche. 

Se si definisce un indirizzo per gli interventi di emergenza usando la funzionalità di ricerca della mappa degli indirizzi nell'interfaccia di amministrazione di Teams, il codice geografico viene associato automaticamente a un indirizzo di emergenza. È anche possibile associare i codici geografici a un indirizzo se si definisce l'indirizzo usando PowerShell. 

Microsoft consiglia di creare indirizzi di emergenza usando la funzionalità di ricerca mappa nell'interfaccia di amministrazione di Teams, che garantisce che gli indirizzi siano formattati, convalidati e che siano disponibili i codici geografici appropriati. 

>[!Important]
>Per assegnare una posizione di emergenza a un identificatore di rete per le chiamate di emergenza dinamiche, l'indirizzo di emergenza deve contenere un codice geografico appropriato.


## <a name="considerations-for-calling-plans"></a>Considerazioni per i piani per chiamate

Le sezioni seguenti descrivono come gestire le chiamate di emergenza per gli utenti del Piano chiamate Microsoft. Per scoprire se i piani per chiamate Microsoft sono la soluzione giusta per l'azienda, vedere [Opzioni di connettività PSTN](pstn-connectivity.md).


### <a name="emergency-call-enablement-for-calling-plans"></a>Abilitazione delle chiamate di emergenza per i piani per chiamate

Ogni utente del Piano chiamate è abilitato automaticamente per le chiamate di emergenza ed è necessario avere un indirizzo di emergenza registrato associato al numero di telefono assegnato. 

Quando la località è associata al numero di telefono dipende dal paese/area geografica:

- Negli Stati Uniti e in Canada, ad esempio, è necessario un luogo per gli interventi di emergenza quando a un utente viene assegnato un numero.

- &mdash;Per altri paesi, come in Europa, Medio Oriente e Africa (EMEA),&mdash; è necessaria una posizione di emergenza quando si ottiene il numero di telefono da Microsoft 365 o quando viene trasferito da un altro provider di servizi o gestore.


### <a name="dynamic-emergency-calling-for-calling-plans"></a>Chiamate di emergenza dinamiche per i piani di chiamata

Le chiamate di emergenza dinamiche per i piani di chiamata forniscono la possibilità di configurare e instradare le chiamate di emergenza in base alla posizione corrente del client Teams chiamata. La possibilità di eseguire il routing automatico al punto di risposta per la sicurezza pubblica appropriato (PSAP) o di inviare notifiche al personale dell'ufficio di sicurezza varia a seconda del paese di utilizzo dell'Teams utente.  

La posizione dinamica per l'instradamento delle chiamate di emergenza è supportata negli Stati Uniti nel modo seguente. 

- Se un client Teams per un piano per chiamate degli Stati Uniti acquisisce dinamicamente un indirizzo di emergenza negli Stati Uniti, tale indirizzo viene usato per il routing di emergenza invece dell'indirizzo registrato e la chiamata verrà automaticamente instradata al PSAP nell'area di servizio dell'indirizzo.

- Se un client Teams per un utente del piano per le chiamate degli Stati Uniti non acquisisce dinamicamente un indirizzo di emergenza negli Stati Uniti, l'indirizzo di emergenza registrato viene usato per aiutare a determinare e instradare la chiamata. Tuttavia, la chiamata verrà visualizzata per determinare se è necessario un indirizzo aggiornato prima di connettere il chiamante al PSAP appropriato.

La posizione dinamica per l'instradamento delle chiamate di emergenza è supportata in Canada come negli Stati Uniti con la seguente eccezione: tutte le chiamate di emergenza verranno visualizzate a livello nazionale prima di essere trasferite al PSAP.

Per altre informazioni, vedere [Pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-calling-plans"></a>Routing delle chiamate di emergenza per i piani per chiamate

Quando un Teams chiama un numero di emergenza, il modo in cui la chiamata viene instradata al PSAP dipende da quanto segue:

- Se l'indirizzo per gli interventi di emergenza è determinato dinamicamente dal Teams client.

- Se l'indirizzo di emergenza è l'indirizzo registrato associato al numero di telefono dell'utente.

- La rete di chiamate di emergenza di quel paese.

Ad esempio:

**Negli Stati Uniti:**

- Se un client Teams si trova in una posizione di emergenza dinamica definita dal tenant, le chiamate di emergenza da quel client vengono automaticamente instradati al psap che serve tale posizione geografica.

- Se un client Teams non si trova in una posizione di emergenza dinamica definita dal tenant, le chiamate di emergenza provenienti da tale client vengono schermate da un call center nazionale per determinare la posizione del chiamante prima di trasferire la chiamata al PSAP che serve tale posizione geografica.

- Se un chiamante di emergenza non riesce ad aggiornare la posizione di emergenza al centro di screening, la chiamata verrà trasferita al PSAP che serve l'indirizzo registrato del chiamante.

**In Canada, Irlanda e** Regno Unito le chiamate di emergenza vengono prima schermate per determinare la posizione corrente dell'utente prima di connettere la chiamata al centro di spedizione appropriato.

**In Francia, Germania e Spagna** le chiamate di emergenza vengono instradati direttamente al PSAP che serve l'indirizzo di emergenza associato al numero, indipendentemente dalla posizione del chiamante.

**Nei Paesi Bassi** le chiamate di emergenza vengono instradati direttamente al PSAP per il codice di area locale del numero, indipendentemente dalla posizione del chiamante.

**In Australia**, gli indirizzi di emergenza sono configurati e instradati dal partner gestore.

**In Giappone** le chiamate di emergenza non sono supportate.


Per ulteriori informazioni, vedere:

- [Piani di chiamata](calling-plan-landing-page.md)
- [Configurare i piani per chiamate](set-up-calling-plans.md)
- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Termini e condizioni per le chiamate al numero di emergenza](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-operator-connect"></a>Considerazioni per Connessione con operatore

Le sezioni seguenti descrivono come gestire le chiamate di emergenza per Connessione con operatore utenti. Per sapere se Connessione con operatore è la soluzione giusta per l'azienda, vedere Opzioni di connettività [PSTN](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-operator-connect"></a>Abilitazione delle chiamate di emergenza per Connessione con operatore

Ogni Connessione con operatore utente viene abilitato automaticamente per le chiamate di emergenza. Le chiamate di emergenza vengono instradati automaticamente al gestore Connessione con operatore per un determinato numero.

La possibilità per un amministratore tenant di impostare l'indirizzo registrato per un utente Connessione con operatore dipenderà dalle funzionalità assegnate al numero quando il gestore lo carica in un inventario dei clienti. In base a questa impostazione, l'amministratore del tenant&mdash;&mdash; può o meno essere necessario per impostare, modificare o eliminare la posizione di emergenza di un utente. 

### <a name="dynamic-emergency-calling-for-operator-connect"></a>Chiamate di emergenza dinamiche per Connessione con operatore

Le chiamate di emergenza dinamiche per Connessione con operatore forniscono la possibilità di configurare e instradare le chiamate di emergenza in base alla posizione corrente del Teams client. La possibilità di eseguire il routing automatico al punto di risposta per la sicurezza pubblica appropriato (PSAP) o di inviare notifiche al personale dell'ufficio di sicurezza varia a seconda del paese di utilizzo dell'Teams utente. 

La posizione dinamica per l'instradamento delle chiamate di emergenza è supportata negli Stati Uniti nel modo seguente. 

- Se un client Teams per un utente degli Stati Uniti acquisisce dinamicamente un indirizzo di emergenza negli Stati Uniti, tale indirizzo viene usato per il routing di emergenza invece dell'indirizzo registrato e la chiamata verrà automaticamente instradata al PSAP nell'area di servizio dell'indirizzo.

- Se un client Teams per un utente degli Stati Uniti non acquisisce dinamicamente un indirizzo di emergenza negli Stati Uniti, l'indirizzo di emergenza registrato viene usato per visualizzare e instradare la chiamata. Tuttavia, la chiamata verrà visualizzata per determinare se è necessario un indirizzo aggiornato prima di connettere il chiamante al PSAP appropriato.

La posizione dinamica per l'instradamento delle chiamate di emergenza è supportata in Canada come negli Stati Uniti con le eccezioni seguenti: tutte le chiamate di emergenza verranno visualizzate a livello nazionale prima di essere trasferite al PSAP.

Per altre informazioni, vedere [Pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-operator-connect"></a>Routing delle chiamate di emergenza per Connessione con operatore

Quando un Teams Connessione con operatore chiama un numero di emergenza, il modo in cui la chiamata viene instradata al PSAP dipende da quanto segue:

- Se l'indirizzo per gli interventi di emergenza è determinato dinamicamente dal Teams client.

- Se l'indirizzo di emergenza è l'indirizzo registrato associato al numero di telefono dell'utente.

- La rete di chiamate di emergenza di quel paese.

- Negli Stati Uniti e in Canada, il routing dinamico fa parte del servizio del gestore. Non è necessario acquistare questo servizio da un altro provider di servizi.

- Se un Teams si trova in una posizione di emergenza dinamica definita dal tenant:

   - Negli Stati Uniti, le chiamate di emergenza da quel client vengono automaticamente instradati al PSAP che serve quella posizione geografica.
   - In Canada, tutte le chiamate di emergenza verranno schermate da un call center nazionale prima di trasferire la chiamata al PSAP che serve quella posizione geografica.

- Se un client Teams non si trova in una posizione di emergenza dinamica definita dal tenant, le chiamate di emergenza provenienti da tale client vengono schermate da un call center nazionale per determinare la posizione del chiamante prima di trasferire la chiamata al PSAP che serve tale posizione geografica.

- Se un chiamante di emergenza non riesce ad aggiornare la posizione di emergenza al centro di screening, la chiamata verrà trasferita al PSAP che serve l'indirizzo registrato del chiamante.


## <a name="considerations-for-direct-routing"></a>Considerazioni sul routing diretto

Le sezioni seguenti descrivono come gestire le chiamate di emergenza per gli utenti di Routing diretto. Per scoprire se Il routing diretto è la soluzione giusta per l'azienda, vedere Opzioni [di connettività PSTN](pstn-connectivity.md).

### <a name="emergency-call-enablement-for-direct-routing"></a>Abilitazione delle chiamate di emergenza per il routing diretto

Per il routing diretto, è necessario definire i criteri per le chiamate di emergenza per gli utenti usando un criterio Teams di [routing](manage-emergency-call-routing-policies.md) delle chiamate di emergenza per definire i numeri di emergenza e la destinazione di routing associata. Attualmente, le posizioni di emergenza registrate non sono supportate per gli utenti di Routing diretto.

È possibile assegnare un criterio di routing delle chiamate di emergenza a un account utente di Routing diretto, a un sito di rete o a entrambi. Quando un client Teams o modifica una connessione di rete, Teams esegue una ricerca del sito di rete in cui si trova il client nel modo seguente:

- Se al sito è associato un criterio di routing delle chiamate di emergenza, il criterio del sito viene usato per configurare le chiamate di emergenza.

- Se al sito non sono associati criteri di routing delle chiamate di emergenza, se il client è connesso a un sito non definito o se il numero composto non corrisponde a uno dei numeri di emergenza definiti nel criterio di routing delle chiamate di emergenza associato al sito, il criterio di routing delle chiamate di emergenza associato all'account utente viene usato per configurare le chiamate di emergenza. 

- Se il client Teams non riesce a ottenere un criterio di routing delle chiamate di emergenza, l'utente non è abilitato per le chiamate di emergenza.


### <a name="dynamic-emergency-calling-for-direct-routing"></a>Chiamate di emergenza dinamiche per il routing diretto

Le chiamate di emergenza dinamiche per il routing diretto forniscono la possibilità di configurare e instradare le chiamate di emergenza in base alla posizione corrente Teams client. La possibilità di eseguire il routing automatico al punto di risposta per la sicurezza pubblica appropriato (PSAP) o di inviare notifiche al personale del desk di sicurezza varia a seconda del paese di utilizzo dell'Teams utente.

Per gli utenti di Routing diretto, la posizione dinamica per l'instradamento delle chiamate di emergenza è supportata solo negli Stati Uniti nel modo seguente:

-   Se un client Teams per un utente di Routing diretto degli Stati Uniti acquisisce dinamicamente un indirizzo di emergenza negli Stati Uniti, tale indirizzo viene usato per il routing di emergenza e la chiamata verrà automaticamente instradata al PSAP nell'area di servizio dell'indirizzo.

-   Se un client Teams per un utente di Routing diretto degli Stati Uniti non acquisisce dinamicamente un indirizzo di emergenza negli Stati Uniti, la chiamata verrà visualizzata per determinare se è necessario un indirizzo aggiornato prima di connettere il chiamante al PSAP appropriato.

La posizione dinamica per l'instradamento delle chiamate di emergenza è supportata in Canada come negli Stati Uniti con la seguente eccezione: tutte le chiamate di emergenza verranno visualizzate a livello nazionale prima di essere trasferite al PSAP.

Per altre informazioni, vedere [Configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing-for-direct-routing"></a>Routing delle chiamate di emergenza per l'instradamento diretto

Il criterio di routing delle chiamate di emergenza per il routing diretto fa riferimento a un utilizzo PSTN online, che deve avere la configurazione di Routing diretto appropriata per instradare correttamente le chiamate di emergenza ai gateway PSTN appropriati. In particolare, è necessario assicurarsi che sia presente un OnlineVoiceRoute per la stringa di chiamata di emergenza. Per altre informazioni, vedere [Configurare il routing diretto](direct-routing-configure.md). 

> [!NOTE]
> Teams client non antepone più il segno "+" davanti ai numeri di emergenza, ad esempio +911. Di conseguenza, Teams le chiamate di emergenza non invieranno più un "+" che precede il numero 911. Assicurarsi che i criteri del percorso vocale riflettano questa modifica.

La possibilità di instradare dinamicamente le chiamate di emergenza per gli utenti di Routing diretto varia a seconda della rete di chiamate di emergenza all'interno di un determinato paese. Sono disponibili due soluzioni:

- [Provider di servizi di routing di emergenza (solo Stati Uniti)](#emergency-routing-service-providers)
- [Applicazioni per il numero di identificazione della posizione di emergenza](#emergency-location-identification-number-applications)

#### <a name="emergency-routing-service-providers"></a>Provider di servizi di routing di emergenza

Negli Stati Uniti sono disponibili numerosi provider di servizi di routing di emergenza (ESP) certificati che possono instradare automaticamente le chiamate di emergenza in base alla posizione del chiamante.

- Se un provider di servizi di routing di emergenza è integrato in una distribuzione di Routing diretto, le chiamate di emergenza con una posizione acquisita dinamicamente verranno automaticamente instradati al Punto di risposta per la sicurezza pubblica (PSAP) che serve tale posizione.

-  Le chiamate di emergenza senza una posizione acquisita dinamicamente vengono prima schermate per determinare la posizione corrente dell'utente prima di connettere la chiamata al centro di distribuzione appropriato in base alla posizione aggiornata.

Per altre informazioni, vedere [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).


#### <a name="emergency-location-identification-number-applications"></a>Applicazioni per il numero di identificazione della posizione di emergenza

I session border controller (SBC) possono includere applicazioni ELIN (Emergency Location Identification Number). Se un'applicazione ELIN SBC è integrata in una distribuzione di Routing diretto, è necessario configurare gli indirizzi di emergenza e i numeri di telefono associati nell'applicazione ELIN e quindi caricare i record ELIN nel database delle chiamate di emergenza nella rispettiva rete PSTN. Teams le posizioni di emergenza con un identificatore ELIN devono corrispondere a quelle all'interno dell'applicazione ELIN.

Quando una chiamata di emergenza con una posizione acquisita dinamicamente viene instradata all'SBC appropriato, l'applicazione ELIN:

- Analizza la posizione di emergenza del chiamante.
- Corrisponde alla posizione a un record ELIN.
- Sostituisce il numero del chiamante di emergenza con il numero di telefono ELIN.
- Instrada la chiamata al psap che serve tale posizione e quindi i dispatcher ottengono la posizione dal record ELIN caricato.

Una volta richiamato il numero di emergenza, l'applicazione ELIN farà l'operazione inversa denominata sostituzione dei numeri con quella del chiamante di emergenza originale. 

Per altre informazioni, vedere [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).


## <a name="security-desk-notification"></a>Notifica di Security Desk

La notifica del desk di sicurezza è disponibile sia con Piani per chiamate Microsoft, Connessione con operatore e routing diretto.

Si usa un criterio di chiamata di emergenza di Teams (TeamsEmergencyCallingPolicy) per configurare chi deve ricevere una notifica durante una chiamata di emergenza e come viene notificato: solo chat, conferenza in corso e disattivato o conferenza in corso e disattivato, ma con la possibilità di riattivare l'audio. È anche possibile specificare un numero PSTN esterno di un utente o gruppo da chiamare e partecipare alla chiamata di emergenza. Si noti che l'utente PSTN non è autorizzato a riattivare l'audio.

I criteri per le chiamate di emergenza possono essere concessi a un account Teams utente, assegnato a un sito di rete o a entrambi.  Quando un client Teams o modifica una connessione di rete, Teams esegue una ricerca del sito di rete in cui si trova il client:

- Se un criterio per le chiamate di emergenza è associato a un sito di rete, il criterio del sito viene usato per configurare la notifica del security desk.

- Se al sito non sono associati criteri per le chiamate di emergenza o se il client è connesso a un sito non definito, il criterio per le chiamate di emergenza associato all'account utente viene usato per configurare la notifica del desk di sicurezza.  

- Se il client Teams non riesce a ottenere un criterio per le chiamate di emergenza, l'utente non è abilitato per la notifica del security desk.

Durante una chiamata di emergenza, un desk di sicurezza viene connesso alla chiamata e l'esperienza dell'utente del security desk è controllata in base ai criteri Teams per le chiamate di emergenza. Viene avviata una chat di gruppo con ogni membro del desk di sicurezza e la posizione del chiamante di emergenza viene condivisa tramite una notifica di messaggio importante.  Se un'opzione di conferenza è configurata come parte del criterio, ogni utente del security desk viene chiamato anche come parte della conferenza.

    
## <a name="related-topics"></a>Argomenti correlati

- [Gestire i criteri delle chiamate di emergenza](manage-emergency-calling-policies.md)
- [Gestire i criteri di routing delle chiamate di emergenza ](manage-emergency-call-routing-policies.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Assegnare o modificare una posizione per gli interventi di emergenza per l'utente](assign-change-emergency-location-user.md)
- [Pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md)
