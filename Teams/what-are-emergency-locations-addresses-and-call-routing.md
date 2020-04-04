---
title: Pianificare e gestire le chiamate di emergenza
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: Informazioni sulle chiamate in caso di emergenza, incluse indicazioni su indirizzi di emergenza, routing delle chiamate di emergenza e chiamate di emergenza dinamiche.
ms.openlocfilehash: 8afe2d2af8b2aecbe3d73da03137f330aa8304b8
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141029"
---
# <a name="manage-emergency-calling"></a>Gestire le chiamate di emergenza

In questo articolo vengono illustrati i concetti che è necessario conoscere per gestire le chiamate di emergenza, che include informazioni su indirizzi di emergenza, indirizzi di emergenza dinamici e routing delle chiamate di emergenza. Questo articolo usa la terminologia seguente:

- **Indirizzo di emergenza** -indirizzo civico-l'indirizzo fisico o di strada di una posizione di business per l'organizzazione.

  Ad esempio, l'indirizzo *12345 North Main Street, Redmond, WA 98052* viene usato per instradare le chiamate di emergenza alle autorità di spedizione appropriate e per facilitare l'individuazione del chiamante di emergenza.

- **Posizionare** -in genere un piano, un edificio, un'ala o un numero di ufficio. La posizione è associata a un indirizzo di emergenza per assegnare un percorso più preciso all'interno di un edificio. È possibile avere un numero illimitato di posizioni associate a un indirizzo di emergenza. Ad esempio, se l'organizzazione ha più edifici, è consigliabile includere informazioni sul luogo per ogni edificio e per ogni piano all'interno di ogni edificio.  

- **Posizione di emergenza** : la posizione è un indirizzo civico, con un posto facoltativo. Se l'azienda ha più di una posizione fisica, è probabile che sia necessaria più di una posizione di emergenza. 

  Quando si crea un indirizzo di emergenza, per questo indirizzo viene creato automaticamente un ID posizione univoco.  Se si aggiunge una posizione a un indirizzo di emergenza, ad esempio se si aggiunge un piano a un indirizzo di un edificio, viene creato un ID posizione per la combinazione dell'indirizzo di emergenza e del luogo.  In questo esempio ci saranno due ID posizione: uno per l'indirizzo civico; uno per l'indirizzo civico Unito e il luogo associato.

  Quando si assegna una posizione di emergenza a un utente o un sito, si tratta di un ID di posizione univoco associato all'utente o al sito.

- **Indirizzo registrato** -indirizzo di emergenza assegnato a ogni utente del piano chiamante; a volte viene indicato come indirizzo di emergenza statico o indirizzo del record.  Gli indirizzi registrati non si applicano agli utenti di routing diretto.

Puoi creare indirizzi di emergenza per chiamare gli utenti del piano usando l'interfaccia di amministrazione di teams.  

>[!Note]
>Ci sono alcune differenze nel modo in cui Gestisci le chiamate di emergenza, a seconda che si stiano usando piani per chiamate telefoniche o sistemi telefonici diretti per la connettività PSTN. Queste considerazioni sono descritte in questo articolo.

## <a name="emergency-address-validation"></a>Convalida degli indirizzi di emergenza

Per assegnare un indirizzo di emergenza a un utente o a un identificatore di rete, è necessario assicurarsi che l'indirizzo di emergenza sia contrassegnato come "convalidato".  La convalida degli indirizzi garantisce che l'indirizzo sia legittimo e che non possa essere modificato dopo l'assegnazione. 

Se si definisce un indirizzo di emergenza usando la caratteristica Ricerca mappa indirizzi nell'interfaccia di amministrazione di teams, l'indirizzo viene contrassegnato automaticamente come convalidato. Non è possibile modificare un indirizzo di emergenza convalidato. Pertanto, se il formato o la rappresentazione dell'indirizzo cambia, è necessario creare un nuovo indirizzo con il formato aggiornato.


## <a name="emergency-address-geo-codes"></a>Codici Geo per l'indirizzo di emergenza

Ogni indirizzo di emergenza può avere un codice Geo (Latitudine e longitudine) associato. Questi codici Geo vengono usati in alcuni paesi per facilitare il routing delle chiamate di emergenza con posizioni dinamiche. 

Se si definisce un indirizzo di emergenza usando la caratteristica Ricerca mappa indirizzi nell'interfaccia di amministrazione di teams, il codice Geo viene automaticamente associato a un indirizzo di emergenza. È anche possibile associare i codici Geo a un indirizzo se si definisce l'indirizzo usando PowerShell. Tuttavia, Microsoft consiglia di creare indirizzi di emergenza per il piano di chiamata usando la caratteristica ricerca Mappa nell'interfaccia di amministrazione di teams, in modo che gli indirizzi vengano formattati, convalidati e dispongano dei codici Geo appropriati.  

>[!Important]
>Per assegnare una posizione di emergenza a un identificatore di rete per le chiamate di emergenza dinamiche, l'indirizzo di emergenza deve contenere un codice Geo appropriato.


## <a name="considerations-for-calling-plans"></a>Considerazioni per i piani di chiamata

Per scoprire se i piani per le chiamate sono disponibili nella propria area geografica, vedere [disponibilità di paesi e aree](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)geografiche per i piani di chiamata.


### <a name="emergency-call-enablement"></a>Abilitazione delle chiamate di emergenza

Ogni utente del piano chiamante viene abilitato automaticamente per le chiamate di emergenza ed è necessario disporre di un indirizzo di emergenza registrato associato al numero di telefono assegnato. 

Quando la posizione deve essere associata al numero di telefono dipende dal paese/area geografica:

- Negli Stati Uniti e in Canada, ad esempio, è necessaria una posizione di emergenza quando un numero viene assegnato a un utente.

- Per altri paesi, ad esempio in Europa, Medio Oriente e Africa (EMEA), è necessaria una posizione di emergenza quando si riceve il numero di telefono da Office 365 o quando viene trasferito da un altro provider o gestore di servizi.

### <a name="dynamic-emergency-calling"></a>Chiamate di emergenza dinamiche

Le chiamate di emergenza dinamiche per i piani per le chiamate Microsoft offrono la possibilità di configurare e instradare telefonate di emergenza in base alla posizione corrente del client teams. La possibilità di eseguire il routing automatico al punto di risposta di sicurezza pubblica appropriato (PSAP) o di informare il personale del servizio di sicurezza varia a seconda del paese di utilizzo dell'utente teams.  

In questo momento, solo gli utenti del piano chiamante negli Stati Uniti possono sfruttare le posizioni dinamiche per il routing delle chiamate di emergenza come indicato di seguito:

- Se un client di teams per un utente di un piano di chiamate degli Stati Uniti acquisisce in modo dinamico un indirizzo di emergenza all'interno degli Stati Uniti, tale indirizzo viene usato per il routing delle emergenze anziché per l'indirizzo registrato e la chiamata verrà indirizzata automaticamente al PSAP nell'area di servizio dell'indirizzo.

- Se un client di teams per un utente del piano di chiamate degli Stati Uniti non acquisisce in modo dinamico un indirizzo di emergenza negli Stati Uniti, l'indirizzo di emergenza registrato viene usato per aiutare lo schermo e instradare la chiamata. La chiamata verrà tuttavia visualizzata per determinare se è necessario un indirizzo aggiornato prima di connettere il chiamante alla PSAP appropriata.

Negli Stati Uniti è necessario configurare l'indirizzo civico che fa parte delle posizioni di emergenza assegnate agli identificatori di rete e includere i codici Geo associati. Per altre informazioni, vedere [pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md).


### <a name="emergency-call-routing"></a>Routing delle chiamate di emergenza

Quando un team che chiama il piano di un utente compone un numero di emergenza, in che modo la chiamata viene instradata a PSAP dipende da quanto segue:

- Se l'indirizzo di emergenza viene determinato in modo dinamico dal client teams.

- Se l'indirizzo di emergenza è l'indirizzo registrato associato al numero di telefono dell'utente.

- Rete di chiamate di emergenza di tale paese.

  **Negli Stati Uniti:**

  - Se un client teams si trova in una posizione di emergenza dinamica definita dal tenant, le chiamate di emergenza provenienti da tale client vengono automaticamente indirizzate al PSAP che serve tale posizione geografica. 

  - Se un client teams non si trova in una posizione di emergenza dinamica definita dall'inquilino, le chiamate di emergenza provenienti da tale client vengono visualizzate da un Call Center nazionale per determinare la posizione del chiamante prima di trasferire la chiamata al PSAP al servizio della posizione geografica.

  - Se un chiamante di emergenza non è in grado di aggiornare la posizione di emergenza al centro di selezione, la chiamata verrà trasferita al PSAP che serve l'indirizzo registrato del chiamante.

  **In Canada, Irlanda e Regno Unito le**chiamate di emergenza vengono dapprima visualizzate per determinare la posizione corrente dell'utente prima di connettere la chiamata al centro di distribuzione appropriato. 

  **In Francia, Germania e Spagna**le chiamate di emergenza vengono instradate direttamente al PSAP che serve l'indirizzo di emergenza associato al numero indipendentemente dalla posizione del chiamante.

  **In Olanda**le chiamate di emergenza vengono instradate direttamente al PSAP per il prefisso locale del numero indipendentemente dalla posizione del chiamante.

  **In Australia**, gli indirizzi di emergenza sono configurati e instradati dal partner vettore.

  **In Giappone**la chiamata di emergenza non è supportata.


Per altre informazioni, vedere:

- [Piani di chiamata](calling-plan-landing-page.md)

- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [Condizioni per le chiamate di emergenza](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>Considerazioni sul routing diretto

Se i piani per le chiamate non sono disponibili nell'area o se si vuole conservare il gestore esistente, valutare il [routing diretto](direct-routing-landing-page.md). Per altre informazioni, vedere [configurare il routing diretto](direct-routing-configure.md) e [gestire i criteri di routing delle chiamate di emergenza](manage-emergency-call-routing-policies.md).

### <a name="emergency-call-enablement-and-configuration"></a>Abilitazione e configurazione delle chiamate di emergenza

Devi definire i criteri per le chiamate di emergenza per gli utenti di routing diretto usando TeamsEmergencyCallRoutingPolicy per definire i numeri di emergenza e la destinazione di routing associata. Nota che i percorsi di emergenza registrati non sono supportati per gli utenti di routing diretto.

È possibile assegnare un TeamsEmergencyCallRoutingPolicy a un account utente di routing diretto di teams, a un sito di rete o a entrambi. Quando un client teams avvia o modifica una connessione di rete, teams esegue una ricerca del sito di rete in cui il client si trova nel modo seguente:

- Se un TeamsEmergencyCallRoutingPolicy è associato al sito, il criterio del sito viene usato per configurare le chiamate di emergenza.

- Se non è presente alcun TeamsEmergencyCallRoutingPolicy associato al sito oppure se il client è connesso a un sito non definito, viene usata la TeamsEmergencyCallRoutingPolicy associata all'account utente per configurare le chiamate di emergenza. 

- Se il client teams non è in grado di ottenere un TeamsEmergencyCallRoutingPolicy, l'utente non è abilitato per le chiamate di emergenza.

### <a name="dynamic-emergency-calling"></a>Chiamate di emergenza dinamiche

I client di teams per il routing diretto gli utenti possono acquisire un indirizzo dinamico di emergenza, che può essere usato per instradare le chiamate in modo dinamico in base alla posizione del chiamante. Per altre informazioni, vedere [configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md).

### <a name="emergency-call-routing"></a>Routing delle chiamate di emergenza

TeamsEmergencyCallRoutingPolicy fa riferimento a un uso PSTN online, che deve avere la configurazione di routing diretto appropriata per instradare correttamente le chiamate di emergenza ai gateway PSTN appropriati. In particolare, devi assicurarti che sia presente un OnlineVoiceRoute per la stringa di chiamata di emergenza. Per altre informazioni, vedere [configurare il routing diretto](direct-routing-configure.md). 

(Nota: i client di teams anteporre il segno "+" davanti ai numeri di emergenza in modo simile al client Skype for business, ovvero + 911. Questo comportamento verrà modificato nei prossimi mesi in modo che le chiamate di emergenza dei team non invieranno più un "+" che precede il numero; ovvero 911.)

La possibilità di instradare in modo dinamico le chiamate di emergenza per gli utenti di routing diretto varia a seconda della rete chiamante di emergenza all'interno di un paese specifico. Sono disponibili due soluzioni:

- Provider di servizi di routing di emergenza (solo Stati Uniti) 
- Applicazioni gateway ELIN (Emergency Location Identification Number)

#### <a name="emergency-routing-service-providers"></a>Provider di servizi di routing di emergenza

Negli Stati Uniti esistono numerosi provider di servizi di routing di emergenza certificati (ERSPs) che possono instradare automaticamente le chiamate di emergenza in base alla posizione del chiamante.

- Se un provider di servizi di routing di emergenza è integrato in una distribuzione di routing diretto, le chiamate di emergenza con una posizione acquisita in modo dinamico verranno indirizzate automaticamente al punto di PSAP (Public Safety Answering Point) che serve tale posizione.

-  Le chiamate di emergenza senza una posizione acquisita in modo dinamico vengono prima visualizzate per determinare la posizione corrente dell'utente prima di connettere la chiamata al centro di distribuzione appropriato in base al percorso aggiornato.

Per altre informazioni, vedere [controlli bordo sessione certificati per il routing diretto](direct-routing-border-controllers.md).


#### <a name="emergency-location-identification-number-elin-applications"></a>Applicazioni ELIN (Emergency Location Identification Number)

I controller di bordo della sessione (SBCs) possono includere le applicazioni ELIN (Emergency Location Identification Number). Se un'applicazione ELIN SBC è integrata in una distribuzione di routing diretta, è necessario configurare gli indirizzi di emergenza e i numeri di telefono associati nell'applicazione ELIN e quindi caricare i record ELIN nel database delle chiamate di emergenza nella rispettiva rete PSTN.  Le posizioni di emergenza teams con un identificatore ELIN devono corrispondere a quelle dell'applicazione ELIN.

Quando una chiamata di emergenza con una posizione acquisita in modo dinamico viene instradata all'SBC appropriato, l'applicazione ELIN:

- Analizza la posizione di emergenza del chiamante.
- Corrisponde alla posizione di un record ELIN.
- Sostituisce il numero del chiamante di emergenza con il numero di telefono ELIN.
- Instrada la chiamata al PSAP che serve tale posizione e quindi i dispatcher ottengono la posizione dal record ELIN caricato.

Dopo una chiamata di nuovo al numero di emergenza, l'applicazione ELIN eseguirà la sostituzione del numero chiamata a quella del chiamante di emergenza originale. 

Per altre informazioni, vedere [controlli bordo sessione certificati per il routing diretto](direct-routing-border-controllers.md).


## <a name="security-desk-notification"></a>Notifica di Security desk

La notifica di Security desk è disponibile sia con i piani di chiamata Microsoft che con il routing diretto del sistema telefonico.

Si usa TeamsEmergencyCallingPolicy per configurare gli utenti che devono ricevere una notifica durante una chiamata di emergenza e il modo in cui vengono notificati: solo chat, conferenze in e disattivato o conferenze in e disattivato, ma con la possibilità di riattivare l'audio.  È anche possibile specificare un numero PSTN esterno di un utente o di un gruppo per chiamare e partecipare alla chiamata di emergenza. 

Un TeamsEmergencyCallingPolicy può essere concesso a un account utente di teams, assegnato a un sito di rete o a entrambi.  Quando un client teams avvia o modifica una connessione di rete, teams esegue una ricerca del sito di rete in cui si trova il client:

- Se un TeamsEmergencyCallingPolicy è associato a un sito di rete, il criterio del sito viene usato per configurare la notifica di Security desk.

- Se non è presente alcun TeamsEmergencyCallingPolicy associato al sito o se il client è connesso a un sito non definito, il TeamsEmergencyCallingPolicy associato all'account utente viene usato per configurare la notifica di Security desk.  

- Se il client teams non è in grado di ottenere un TeamsEmergencyCallingPolicy, l'utente non è abilitato per la notifica di Security desk.

Durante una chiamata di emergenza, un desk di sicurezza viene convocato nella chiamata e l'esperienza dell'utente del Security desk viene controllata in base al TeamsEmergencyCallingPolicy. Viene avviata una chat di gruppo con ogni membro del servizio di sicurezza e la posizione del chiamante di emergenza viene condivisa tramite una notifica di messaggio importante.  Se un'opzione per la conferenza è configurata come parte del criterio, ogni utente del servizio di sicurezza viene inoltre chiamato come parte della conferenza.

    
## <a name="related-topics"></a>Argomenti correlati

- [Gestire i criteri delle chiamate di emergenza](manage-emergency-calling-policies.md)
- [Gestire i criteri di routing delle chiamate di emergenza](manage-emergency-call-routing-policies.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Assegnare o modificare una posizione di emergenza per l'utente](assign-change-emergency-location-user.md)
- [Pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md)
