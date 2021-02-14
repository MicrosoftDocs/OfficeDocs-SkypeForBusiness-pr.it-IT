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
- m365initiative-voice
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
description: Informazioni sulle chiamate di emergenza, incluse le informazioni sugli indirizzi di emergenza, il routing delle chiamate di emergenza e le chiamate di emergenza dinamiche.
ms.openlocfilehash: 4f2ef86d05537a147a459fd6bc121f0680b534bd
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031602"
---
# <a name="manage-emergency-calling"></a>Gestire le chiamate di emergenza

Questo articolo descrive i concetti che è necessario conoscere per gestire le chiamate di emergenza, tra cui informazioni sugli indirizzi di emergenza, gli indirizzi di emergenza dinamici e il &mdash; routing delle chiamate di emergenza. Questo articolo usa la terminologia seguente:

- **Indirizzo per gli** interventi di emergenza: indirizzo civico dell'indirizzo fisico o stradale di un luogo &mdash; di lavoro per l'organizzazione.

  Ad esempio, l'indirizzo  *12345 North Main Street, Redmond, WA 98052* viene usato per instradare le chiamate di emergenza alle autorità appropriate e per agevolare l'individuazione del chiamante di emergenza.

- **Posizione:** in genere un piano, un edificio, un'ala o un numero di ufficio. La posizione è associata a un indirizzo per gli interventi di emergenza per fornire una posizione più precisa all'interno di un edificio. Puoi avere un numero illimitato di posizioni associate a un indirizzo per gli interventi di emergenza. Ad esempio, se l'organizzazione ha più edifici, è consigliabile includere le informazioni sulla posizione per ogni edificio e per ogni piano di ogni edificio.  

- **Posizione per gli interventi** di emergenza: la posizione è un indirizzo &mdash; civico con un luogo facoltativo. Se la tua azienda ha più di una posizione fisica, probabilmente ti saranno necessarie più di una posizione per gli interventi di emergenza. 

  Quando crei un indirizzo per gli interventi di emergenza, viene creato automaticamente un ID posizione univoco per tale indirizzo.  Se si aggiunge una posizione a un indirizzo per gli interventi di emergenza, ad esempio se si aggiunge un piano all'indirizzo di un edificio, viene creato un ID posizione per la combinazione dell'indirizzo per gli interventi di emergenza e &mdash; &mdash; del luogo.  In questo esempio ci saranno due ID posizione: uno per l'indirizzo civico; uno per l'indirizzo civico unito e la posizione associata.

  Quando assegni una posizione per gli interventi di emergenza a un utente o un sito, questo ID posizione univoco è associato all'utente o al sito.

- **Indirizzo registrato:** indirizzo per gli interventi di emergenza assegnato a ogni utente del Piano per chiamate; a volte viene definito indirizzo di emergenza statico o indirizzo di registrazione.  Gli indirizzi registrati non si applicano agli utenti di routing diretto.

È possibile creare indirizzi di emergenza per gli utenti di Piani per chiamate utilizzando l'interfaccia di amministrazione di Teams.  

>[!Note]
>Esistono alcune differenze nel modo in cui si gestiscono le chiamate di emergenza a seconda che si utilizzino i Piani per chiamate di sistema telefonico o l'instradamento diretto del sistema telefonico per la connettività PSTN. Queste considerazioni sono descritte in questo articolo.

## <a name="emergency-address-validation"></a>Convalida dell'indirizzo per gli interventi di emergenza

Per assegnare un indirizzo per gli interventi di emergenza a un utente o a un identificatore di rete, devi assicurarti che l'indirizzo per gli interventi di emergenza sia contrassegnato come "convalidato".  La convalida dell'indirizzo garantisce che l'indirizzo sia legittimo e non possa essere modificato dopo l'assegnazione. 

Se si definisce un indirizzo per gli interventi di emergenza utilizzando la funzione di ricerca della mappa degli indirizzi nell'interfaccia di amministrazione di Teams, l'indirizzo viene automaticamente contrassegnato come convalidato. Non puoi modificare un indirizzo per gli interventi di emergenza convalidato. Pertanto, se il formato o la rappresentazione dell'indirizzo cambia, è necessario creare un nuovo indirizzo con il formato aggiornato.


## <a name="emergency-address-geo-codes"></a>Codici geografici per gli indirizzi di emergenza

A ogni indirizzo di emergenza può essere associato un codice geografico (latitudine e longitudine). Questi codici geografici vengono utilizzati in alcuni paesi per agevolare l'instradamento delle chiamate di emergenza con posizioni dinamiche. 

Se si definisce un indirizzo per gli interventi di emergenza utilizzando la funzione di ricerca della mappa degli indirizzi nell'interfaccia di amministrazione di Teams, il codice geografico viene associato automaticamente a un indirizzo per gli interventi di emergenza. Se si definisce l'indirizzo con PowerShell, è anche possibile associare codici geografici a un indirizzo. Tuttavia, Microsoft consiglia di creare indirizzi di emergenza per il Piano per chiamate utilizzando la funzione di ricerca mappa nell'interfaccia di amministrazione di Teams, che garantisce che gli indirizzi siano formattati, convalidati e di avere i codici geografici appropriati.  

>[!Important]
>Per assegnare una posizione per gli interventi di emergenza a un identificatore di rete per le chiamate di emergenza dinamiche, l'indirizzo di emergenza deve contenere un codice geografico appropriato.


## <a name="considerations-for-calling-plans"></a>Considerazioni per i piani per chiamate

Per sapere se i Piani per chiamate sono disponibili nella propria area, consulta La disponibilità di Paesi [e aree per i Piani per chiamate.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)


### <a name="emergency-call-enablement"></a>Abilitazione delle chiamate di emergenza

Ogni utente del Piano per chiamate viene abilitato automaticamente per le chiamate di emergenza ed è necessario avere un indirizzo di emergenza registrato associato al proprio numero di telefono assegnato. 

Quando la località deve essere associata al numero di telefono dipende dal paese/area geografica:

- Negli Stati Uniti e in Canada, ad esempio, è richiesta una posizione per gli interventi di emergenza quando viene assegnato un numero a un utente.

- Per altri paesi, come in Europa, Medio Oriente e Africa (EMEA), è richiesta una posizione per gli interventi di emergenza quando si ottiene il numero di telefono da Microsoft 365 o Office 365 o quando viene trasferito da un altro provider di servizi o gestore.

### <a name="dynamic-emergency-calling"></a>Chiamate di emergenza dinamiche

Le chiamate di emergenza dinamiche per i Piani per chiamate Microsoft sono in grado di configurare e instradare le chiamate di emergenza in base alla posizione corrente del client Teams. La possibilità di eseguire il routing automatico al punto di risposta per la sicurezza pubblica appropriato (PSAP) o di inviare una notifica al personale addetto alla sicurezza varia a seconda del paese di utilizzo dell'utente di Teams.  

Per gli utenti del Piano per chiamate, la posizione dinamica per l'instradamento delle chiamate di emergenza è supportata solo negli Stati Uniti come indicato di seguito. Per informazioni sulle chiamate di emergenza dinamiche e l'instradamento diretto, vedere [Considerazioni sull'instradamento diretto.](#considerations-for-direct-routing)

- Se un client Teams per un utente del Piano per chiamate degli Stati Uniti acquisisce dinamicamente un indirizzo per gli interventi di emergenza negli Stati Uniti, tale indirizzo viene utilizzato per il routing di emergenza invece dell'indirizzo registrato e la chiamata viene automaticamente instradata al protocollo PSAP nell'area di servizio dell'indirizzo.

- Se un client Teams per un utente del Piano per chiamate negli Stati Uniti non acquisisce dinamicamente un indirizzo per gli interventi di emergenza negli Stati Uniti, l'indirizzo di emergenza registrato viene utilizzato per facilitare la schermata e l'instradazione della chiamata. Tuttavia, la chiamata verrà visualizzata per determinare se è necessario un indirizzo aggiornato prima di connettere il chiamante al psap appropriato.

Negli Stati Uniti è necessario configurare l'indirizzo civico che fa parte delle posizioni per gli interventi di emergenza assegnate agli identificatori di rete e includere &mdash; i codici geografici associati. Per ulteriori informazioni, consulta Pianificare [e configurare le chiamate di emergenza dinamiche.](configure-dynamic-emergency-calling.md)


### <a name="emergency-call-routing"></a>Instradamento delle chiamate di emergenza

Quando un utente del Piano per chiamate di Teams compone un numero di emergenza, il modo in cui la chiamata viene instradata al sistema PSAP dipende da quanto segue:

- Se l'indirizzo per gli interventi di emergenza viene determinato dinamicamente dal client di Teams.

- Se l'indirizzo per gli interventi di emergenza è l'indirizzo registrato associato al numero di telefono dell'utente.

- La rete per le chiamate di emergenza di quel paese.

  **Negli Stati Uniti:**

  - Se un client Teams si trova in una posizione dinamica per gli interventi di emergenza definita dal tenant, le chiamate di emergenza da quel client vengono automaticamente indirizzate al client PSAP che serve tale posizione geografica. 

  - Se un client Teams non si trova in una posizione di emergenza dinamica definita dal tenant, le chiamate di emergenza da quel client vengono schermate da un call center nazionale per determinare la posizione del chiamante prima di trasferire la chiamata al PSAP che serve tale posizione geografica.

  - Se un chiamante di emergenza non è in grado di aggiornare la posizione di emergenza al centro di selezione, la chiamata verrà trasferita al PSAP che serve l'indirizzo registrato del chiamante.

  **In Canada, Irlanda** e Regno Unito, le chiamate di emergenza vengono innanzitutto schermate per determinare la posizione corrente dell'utente prima di collegarla al centro di emergenza appropriato. 

  **In Francia, Germania** e Spagna, le chiamate di emergenza vengono instradati direttamente al psAP che serve l'indirizzo di emergenza associato al numero, indipendentemente dalla posizione del chiamante.

  **Nei Paesi Bassi** le chiamate di emergenza vengono instradati direttamente al PSAP per il codice di area locale del numero, indipendentemente dalla posizione del chiamante.

  **In Australia,** gli indirizzi di emergenza sono configurati e instradati dal partner vettore.

  **In Giappone,** le chiamate di emergenza non sono supportate.


Per ulteriori informazioni, vedere:

- [Piani di chiamata](calling-plan-landing-page.md)

- [Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [Termini e condizioni per le chiamate di emergenza](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>Considerazioni sull'instradamento diretto

Se i Piani per chiamate non sono disponibili nella propria area o se si vuole mantenere il gestore esistente, prendere in considerazione [l'instradamento diretto.](direct-routing-landing-page.md) Per ulteriori informazioni, consulta Configurare [l'instradamento diretto](direct-routing-configure.md) e [gestire i criteri di instradamento delle chiamate di emergenza.](manage-emergency-call-routing-policies.md)

### <a name="emergency-call-enablement-and-configuration"></a>Abilitazione e configurazione delle chiamate di emergenza

È necessario definire criteri per le chiamate di emergenza per gli utenti instradamento diretto utilizzando un criterio teams di instradamento delle chiamate di emergenza (TeamsEmergencyCallRoutingPolicy) per definire i numeri di emergenza e la destinazione di instradamento associata. Si noti che le posizioni per gli interventi di emergenza registrati non sono supportate per gli utenti di routing diretto.

È possibile assegnare un criterio di instradamento delle chiamate di emergenza a un account utente Instradamento diretto di Teams, un sito di rete o entrambi. Quando viene avviato un client di Teams o si modifica una connessione di rete, Teams esegue una ricerca del sito di rete in cui si trova il client nel modo seguente:

- Se al sito è associato un criterio di instradamento delle chiamate di emergenza, il criterio del sito viene usato per configurare le chiamate di emergenza.

- Se al sito non sono associati criteri di instradamento delle chiamate di emergenza o se il client è connesso a un sito non definito, il criterio di instradamento delle chiamate di emergenza associato all'account utente viene usato per configurare le chiamate di emergenza. 

- Se il client Teams non è in grado di ottenere un criterio di instradamento delle chiamate di emergenza, l'utente non è abilitato per le chiamate di emergenza.

### <a name="dynamic-emergency-calling"></a>Chiamate di emergenza dinamiche

I client di Teams per gli utenti di instradamento diretto possono acquisire un indirizzo di emergenza dinamico, che può essere usato per instradare dinamicamente le chiamate in base alla posizione del chiamante. Per ulteriori informazioni, consulta [Configurare le chiamate di emergenza dinamiche.](configure-dynamic-emergency-calling.md)

### <a name="emergency-call-routing"></a>Instradamento delle chiamate di emergenza

Il criterio di instradamento delle chiamate di emergenza fa riferimento a un utilizzo PSTN online, che deve avere la configurazione di routing diretto appropriata per instradare correttamente le chiamate di emergenza al gateway o ai gateway PSTN appropriati. In particolare, è necessario assicurarsi che sia disponibile un OnlineVoiceRoute per la stringa di composizione per gli interventi di emergenza. Per altre informazioni, vedere [Configurare l'instradamento diretto.](direct-routing-configure.md) 

(Nota: i client di Teams anteponeno il segno "+" davanti ai numeri di emergenza in modo analogo al client Skype for Business, ovvero +911. Questo comportamento verrà modificato nei prossimi mesi in modo che le chiamate di emergenza di Teams non invieranno più un segno "+" prima del numero; ad esempio 911.

La possibilità di instradare dinamicamente le chiamate di emergenza per gli utenti con instradamento diretto varia a seconda della rete di chiamate di emergenza all'interno di un determinato paese. Sono disponibili due soluzioni:

- Provider di servizi di instradamento di emergenza (solo Stati Uniti) 
- Applicazioni gateway ELIN (Emergency Location Identification Number)

#### <a name="emergency-routing-service-providers"></a>Provider di servizi di instradamento di emergenza

Negli Stati Uniti sono disponibili numerosi provider di servizi di emergenza (ESP) certificati che possono instradare automaticamente le chiamate di emergenza in base alla posizione del chiamante.

- Se un provider di servizi di instradamento di emergenza è integrato in una distribuzione di routing diretto, le chiamate di emergenza con una posizione acquisita dinamicamente verranno automaticamente indirizzate al punto PSAP (Public Safety Answering Point) che serve tale posizione.

-  Le chiamate di emergenza senza una posizione acquisita dinamicamente vengono innanzitutto schermate per determinare la posizione corrente dell'utente prima di connettere la chiamata al centro di emergenza appropriato in base alla posizione aggiornata.

Per altre informazioni, vedere [i controller dei confini della sessione certificati per l'instradamento diretto.](direct-routing-border-controllers.md)


#### <a name="emergency-location-identification-number-elin-applications"></a>Applicazioni ELIN (Emergency Location Identification Number)

I controller dei confini della sessione possono includere applicazioni ELIN (Emergency Location Identification Number). Se un'applicazione SBC ELIN è integrata in una distribuzione di routing diretto, è necessario configurare gli indirizzi di emergenza e i numeri di telefono associati nell'applicazione ELIN e quindi caricare i record ELIN nel database per le chiamate di emergenza nel rispettivo pstN.  Le posizioni di emergenza di Teams con un identificatore ELIN devono corrispondere a quelle all'interno dell'applicazione ELIN.

Quando una chiamata di emergenza con una posizione acquisita dinamicamente viene instradata all'SBC appropriato, l'applicazione ELIN:

- Analizza la posizione di emergenza del chiamante.
- Abbina la località a un record ELIN.
- Sostituisce il numero del chiamante di emergenza con il numero di telefono ELIN.
- Invia la chiamata al protocollo PSAP che serve tale posizione, quindi i dispatcher ottengono la posizione dal record ELIN caricato.

Una volta richiamata al numero di emergenza, l'applicazione ELIN farà la sostituzione del numero con quella del chiamante di emergenza originale. 

Per altre informazioni, vedere [i controller dei confini della sessione certificati per l'instradamento diretto.](direct-routing-border-controllers.md)


## <a name="security-desk-notification"></a>Notifica security desk

La notifica security desk è disponibile sia con i piani per chiamate Microsoft che con l'instradamento diretto del sistema telefonico.

È possibile utilizzare un criterio teams per le chiamate di emergenza (TeamsEmergencyCallingPolicy) per configurare le persone che devono ricevere notifiche durante una chiamata di emergenza e il modo in cui vengono avvisate: solo chat, conferenza in corso, audio disattivato o conferenza attivata e disattivata, ma con la possibilità di riattivare l'audio.  È anche possibile specificare un numero PSTN esterno di un utente o gruppo da chiamare e partecipare alla chiamata di emergenza. 

Un criterio per le chiamate di emergenza può essere concesso a un account utente di Teams, a un sito di rete o a entrambi.  Quando viene avviato un client di Teams o si modifica una connessione di rete, Teams esegue una ricerca del sito di rete in cui si trova il client:

- Se un criterio per le chiamate di emergenza è associato a un sito di rete, il criterio del sito viene usato per configurare la notifica del desk sicurezza.

- Se al sito non sono associati criteri per le chiamate di emergenza o se il client è connesso a un sito non definito, il criterio per le chiamate di emergenza associato all'account utente viene usato per configurare la notifica del desk di sicurezza.  

- Se il client Teams non è in grado di ottenere un criterio per le chiamate di emergenza, l'utente non è abilitato per la notifica di security desk.

Durante una chiamata di emergenza, alla chiamata viene conferenze un desk sicurezza e l'esperienza dell'utente del desk di sicurezza è controllata in base ai criteri di chiamata di emergenza di Teams. Viene avviata una chat di gruppo con ogni membro del desk di sicurezza e la posizione del chiamante di emergenza viene condivisa tramite una notifica di messaggio importante.  Se un'opzione di conferenza è configurata come parte del criterio, ogni utente del desk sicurezza viene inoltre chiamato come parte della conferenza.

    
## <a name="related-topics"></a>Argomenti correlati

- [Gestire i criteri delle chiamate di emergenza](manage-emergency-calling-policies.md)
- [Gestire i criteri di instradamento delle chiamate di emergenza ](manage-emergency-call-routing-policies.md)
- [Aggiungere, modificare o rimuovere una posizione di emergenza per l'organizzazione](add-change-remove-emergency-location-organization.md)
- [Assegnare o modificare una posizione per gli interventi di emergenza per l'utente](assign-change-emergency-location-user.md)
- [Pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md)
