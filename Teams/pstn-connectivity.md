---
title: Opzioni di connettività PSTN
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Ulteriori informazioni sulle Teams (connettività PSTN) e sulle decisioni che verranno prese per l'organizzazione.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c53b553a83349c3d4fd20a926f29b4c727175c73aba5ba0f5e352cf19a53f9e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285942"
---
# <a name="pstn-connectivity-options"></a>Opzioni di connettività PSTN

Microsoft fornisce funzionalità COMPLETE PRIVATE Branch Exchange (PBX) per l'organizzazione tramite Sistema telefonico. Tuttavia, per consentire agli utenti di effettuare chiamate esterne all'organizzazione, è necessario connettersi Sistema telefonico alla rete PSTN (Public Switched Telephone Network).

In questo articolo vengono trattate le opzioni di connettività PSTN. Per ulteriori informazioni sulle soluzioni vocali Microsoft, per informazioni dettagliate sulle funzionalità Sistema telefonico, vedere [Plan your Teams voice solution](cloud-voice-landing-page.md).

Per connettersi Sistema telefonico alla rete PSTN, è possibile scegliere tra le opzioni seguenti:

- [**Piano di chiamata**](#phone-system-with-calling-plan). Una soluzione all-in-the-cloud con Microsoft come gestore PSTN.

- [**Connessione con operatore**](#phone-system-with-operator-connect), attualmente disponibile solo in **anteprima pubblica.**  Con Connessione con operatore, se l'operatore esistente è un partecipante al programma Microsoft Connessione con operatore, può gestire le chiamate PSTN e session border controller (SBC). 

- [**Routing diretto**](#phone-system-with-direct-routing), che consente di utilizzare il proprio gestore PSTN connettendo i session border controller (SBC) a Sistema telefonico.


È inoltre possibile scegliere una combinazione di opzioni, che consente di progettare una soluzione per un ambiente complesso o di gestire una migrazione in più passaggi.

Tenere presente che l'opzione o le opzioni selezionate influiscono sulla configurazione di Sistema telefonico funzionalità. Per ulteriori informazioni, vedere [Considerazioni sulla configurazione](#configuration-considerations) più avanti in questo articolo.


## <a name="phone-system-with-calling-plan"></a>Sistema telefonico con Piano per chiamate 

Sistema telefonico piano di chiamata è la soluzione vocale all-in-the-cloud di Microsoft per Teams utenti. Questa è l'opzione più semplice che consente di Sistema telefonico alla rete PSTN. Con questa opzione, Microsoft funge da gestore PSTN, come illustrato nel diagramma seguente:

![Il diagramma 1 mostra Sistema telefonico piano di chiamata](media/voice-solutions-simple.png)

Se rispondi sì a quanto segue, Sistema telefonico piano di chiamata è la soluzione giusta per te:

- Piano di chiamata è disponibile nella tua area geografica.
- Non è necessario conservare l'operatore PSTN corrente.
- Si desidera utilizzare l'accesso gestito da Microsoft alla rete PSTN.

Con questa opzione: 

- Si ottiene Sistema telefonico Microsoft con piani per chiamate nazionali o internazionali aggiunti che consentono di chiamare verso telefoni di tutto il mondo (a seconda del livello di servizio concesso in licenza).

- Non è necessario eseguire la distribuzione o la manutenzione di una distribuzione locale perché il piano di chiamata funziona &mdash; Microsoft 365.

- Nota: se necessario, è possibile scegliere di connettere un session border controller (SBC) supportato tramite il routing diretto per l'interoperabilità con SISTEMI IP di terze parti, dispositivi analogici e altre apparecchiature telefoniche di terze parti supportate da SBC.

Questa opzione richiede una connessione senza interruzioni a Microsoft 365.

Per ulteriori informazioni sul Piano di chiamata, vedere gli articoli seguenti:

- [Qual è il piano di chiamata adatto alle proprie esigenze?](calling-plan-landing-page.md)
- [Come acquistare un piano di chiamata](calling-plans-for-office-365.md)
- [Disponibilità del paese e dell'area geografica per il piano di chiamata](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Configurare il piano di chiamata](set-up-calling-plans.md)


## <a name="phone-system-with-operator-connect"></a>Sistema telefonico con Connessione con operatore

Con Connessione con operatore, attualmente in anteprima pubblica, se l'operatore esistente è un partecipante al programma Microsoft Connessione con operatore, può gestire il servizio per portare le chiamate PSTN a Teams. L'operatore gestisce i servizi di chiamata PSTN e gli SBC (Session Border Controller), consentendo di risparmiare sull'acquisto e sulla gestione dell'hardware.

Connessione con operatore potrebbe essere la soluzione giusta per l'organizzazione se:

- Microsoft Calling Plan non è disponibile nella posizione geografica dell'utente.
- L'operatore preferito è un partecipante al programma Microsoft Connessione con operatore.
- Si desidera trovare un nuovo operatore per abilitare le chiamate in Teams.

Per informazioni sui vantaggi e i requisiti di Connessione con operatore e per un elenco dei vettori che partecipano a questo programma, vedere [Plan Connessione con operatore](operator-connect-plan.md). Per informazioni su come configurare Connessione con operatore, vedere [Configure Connessione con operatore](operator-connect-configure.md).


## <a name="phone-system-with-direct-routing"></a>Sistema telefonico con instradamento diretto

Questa opzione consente di Sistema telefonico alla rete telefonica utilizzando il routing diretto, come illustrato nel diagramma seguente: 

![Il diagramma 5 mostra Sistema telefonico routing diretto](media/voice-solution-with-direct-routing.png)

Sistema telefonico con instradamento diretto potrebbe essere la soluzione ideale se si può rispondere sì alle domande seguenti:

- Si vuole usare Teams con il Sistema telefonico.
- È necessario conservare l'attuale gestore telefonico PSTN.
- Si vuole combinare il routing misto, con alcune chiamate che passano per il Piano per chiamate e altre che passano per il proprio gestore telefonico.
- È necessario interagire con sistemi PBX e/o attrezzature di terze parti, ad esempio tester di sovraccarico, dispositivi analogici e così via.

Con questa opzione:

- Il session border controller (SBC) supportato viene connesso a Sistema telefonico senza la necessità di software locale aggiuntivo.

- È possibile utilizzare praticamente qualsiasi operatore di telefonia con Sistema telefonico.

- È possibile scegliere di configurare e gestire questa opzione oppure farla configurare e gestire dal gestore telefonico o dal partner (chiedere se il gestore o il partner fornisce questa opzione).

- È possibile configurare l'interoperabilità tra le apparecchiature telefoniche, ad esempio un PBX di terze parti e dispositivi &mdash; analogici &mdash; e Sistema telefonico.

Questa opzione richiede quanto segue:

- Connessione senza interruzioni a Microsoft 365.

- Distribuzione e gestione di un SBC supportato.

- Un contratto con un gestore telefonico di terze parte, a meno che non venga distribuita come opzione per fornire la connessione a PBX di terze parti, dispositivi analogici o altre apparecchiature di telefonia per utenti che usano il Sistema telefonico con Piano per chiamate.

Per ulteriori informazioni sul routing diretto, vedere gli articoli seguenti:

- [Pianificare Instradamento diretto](direct-routing-plan.md)
- [Configurare Instradamento diretto](direct-routing-configure.md)
- [Gestire i criteri di routing vocale da utilizzare con il routing diretto](manage-voice-routing-policies.md)
- [Pianificare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-plan.md)
- [Elenco di Session Border Controller certificati per Instradamento diretto](direct-routing-border-controllers.md)



## <a name="configuration-considerations"></a>Considerazioni sulla configurazione

La Sistema telefonico funzionalità sono le stesse indipendentemente dall'opzione di connettività PSTN scelta. Ad esempio, le impostazioni di chiamata senza risposta e inoltro, il trasferimento di chiamata, la musica personalizzata in attesa, il parcheggio di chiamata, la linea condivisa e le app vocali sono tutte disponibili. Per un elenco completo delle Sistema telefonico, vedere Ecco cosa si ottiene [con Sistema telefonico](here-s-what-you-get-with-phone-system.md).

Esistono tuttavia alcune differenze di funzionalità che influiscono sulla modalità di configurazione di determinate Sistema telefonico funzionalità. Ad esempio, l'instradamento diretto richiede passaggi aggiuntivi per configurare il routing delle chiamate. Come altro esempio, il routing diretto fornisce il routing in base alla posizione (LBR, Location-Based-Routing), in modo che sia possibile limitare il bypass a pedaggio in determinate posizioni geografiche in cui non è consentito. 

Nella tabella seguente vengono evidenziate le differenze di configurazione principali. Le sezioni che seguono la tabella forniscono collegamenti a ulteriori informazioni e dettagli.

| Opzione | Descrizione | Telefono gestione dei numeri | Routing chiamate | Disponibilità delle chiamate di emergenza |
| :------------| :-------| :-------| :-------| :-------| 
| Piani di chiamata | -Microsoft agisce come gestore PSTN.<br>-Non è necessario acquistare o gestire SBC.| Ottenuto tramite Microsoft.| -Gestito da Microsoft. <br> -Admin configura i dial plan utente per la conversione dei numeri. | -Enabled da Microsoft. <br> -Admin registra gli indirizzi. <br> -Dynamic calling supported. |
| Connessione con operatore | -Carrier gestisce la connettività PSTN e gli SBC. <br> -Non è necessario acquistare o gestire SBC. | -Ottenuto tramite vettore. <br> - Numeri associati agli indirizzi di emergenza gestiti dal vettore.  | -Gestito dal vettore. <br>-Admin configura i dial plan utente per la conversione dei numeri. | -Enabled by carrier. <br> -Admin registra gli indirizzi. <br> -Dynamic calling supported. |
| Instradamento diretto | -Richiede SBC certificato acquistato da un fornitore di terze parti.<br>-Connessione il tuo SBC per Sistema telefonico.<br> -Utilizzare l'operatore PSTN esistente. | Ottenuta tramite vettore. | -Richiede una configurazione aggiuntiva da parte dell'amministratore.<br>-Admin configura i dial plan trunk per la conversione dei numeri. <br>-LBR disponibile per limitare il bypass a pedaggio. | -Richiede una configurazione aggiuntiva da parte dell'amministratore. <br>-Indirizzi registrati non supportati. <br>-Dynamic calling supported but requires additional configuration. |
|||||


### <a name="phone-number-management"></a>Telefono gestione dei numeri

Microsoft ha a disposizione due tipi di numeri di telefono: numeri di sottoscrittore (utente), che possono essere assegnati agli utenti dell'organizzazione, e numeri di servizio, disponibili come numeri di servizio a numero verde e a numero verde. I numeri di servizio hanno una capacità di chiamata simultanea superiore rispetto ai numeri dei sottoscrittori e possono essere assegnati a servizi quali Audioconferenza, Operatori automatici o Code di chiamata.

Dovrai decidere:

- Quali posizioni utente necessitano di nuovi numeri di telefono da Microsoft?
- Quale tipo di numero di telefono (sottoscrittore o servizio) è necessario?
- Come è possibile eseguire la portabilità dei numeri di telefono Teams?

La modalità di acquisizione e gestione dei numeri di telefono varia a seconda dell'opzione di connettività PSTN.

- Per informazioni sulla gestione dei numeri di telefono per piano di chiamata, vedere [Gestire i numeri di telefono per l'organizzazione.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Per informazioni sulla gestione dei numeri di telefono Connessione con operatore, vedere [Set up phone numbers with Connessione con operatore](operator-connect-configure.md#set-up-phone-numbers).

- Per informazioni sulla gestione dei numeri di telefono per il routing diretto, vedere [Configure the phone number and enable enterprise voice and voicemail](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online).


### <a name="call-routing-and-dial-plans"></a>Routing delle chiamate e dial plan

La modalità di configurazione del routing delle chiamate varia a seconda dell'opzione di connettività PSTN.  

- Per i piani di chiamata, la maggior parte del routing delle chiamate viene gestita dall'infrastruttura microsoft Calling Plan. È possibile configurare i dial plan degli utenti per la conversione dei numeri per l'autorizzazione delle chiamate e il routing delle chiamate. Per ulteriori informazioni, vedere [Che cos'è il dial plan?](what-are-dial-plans.md).

- Ad Connessione con operatore, la maggior parte del routing delle chiamate è gestita dal gestore telefonico.  È possibile configurare i dial plan degli utenti per la conversione dei numeri per l'autorizzazione delle chiamate e il routing delle chiamate. Per ulteriori informazioni, vedere [Che cos'è il dial plan?](what-are-dial-plans.md).

- Per il routing diretto, è necessario configurare il routing delle chiamate specificando le route vocali e assegnando criteri di routing vocale agli utenti. È possibile configurare i dial plan per la conversione dei numeri a livello di trunk per garantire l'interoperabilità con session border controller (SBC). Per ulteriori informazioni, vedere [Configure voice routing for Direct Routing](direct-routing-voice-routing.md), Manage voice routing [policies](manage-voice-routing-policies.md) e Translate [phone numbers](direct-routing-translate-numbers.md). 


### <a name="location-based-routing-for-direct-routing"></a>Instradamento basato sulla località per l'instradamento diretto

In alcuni paesi e aree geografiche, è illegale ignorare il vettore PSTN per ridurre i costi delle chiamate interurbane. Location-Based routing (LBR) per il routing diretto consente di limitare il bypass a pedaggio per Teams utenti in base alla loro posizione geografica. Per ulteriori informazioni su come pianificare e configurare LBR, vedere gli articoli seguenti:

- [Pianificare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-plan.md)
- [Configurare le impostazioni di rete per l'instradamento basato sulla posizione](location-based-routing-configure-network-settings.md)
- [Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)
- [Case study contoso: Location-Based Routing](voice-case-study-location-based-routing.md)<br>
  Descrive come un'azienda multinazionale fittizia, Contoso, ha implementato Location-Based routing per l'organizzazione.


### <a name="emergency-calling"></a>Chiamate di emergenza

La modalità di configurazione delle chiamate di emergenza varia a seconda dell'opzione di connettività PSTN.

- Per piano di chiamata, ogni utente viene automaticamente abilitato per le chiamate di emergenza ed è necessario che al numero di telefono assegnato sia associato un indirizzo di emergenza registrato. Le chiamate di emergenza dinamiche (in base alla posizione del client Teams) sono supportate.  

- Ad Connessione con operatore, ogni utente viene automaticamente abilitato per le chiamate di emergenza ed è necessario avere un indirizzo di emergenza registrato associato al numero di telefono assegnato, ma può essere impostato solo dal partner operatore. Le chiamate di emergenza dinamiche (in base alla posizione del client Teams) sono supportate.

- Per il routing diretto, è necessario definire i criteri di chiamata di emergenza per gli utenti utilizzando un criterio di routing delle chiamate di emergenza di Teams (TeamsEmergencyCallRoutingPolicy) per definire i numeri di emergenza e la destinazione di routing associata. Le posizioni di emergenza registrate non sono supportate per gli utenti di routing diretto. Per le chiamate di emergenza dinamiche, è necessaria una configurazione aggiuntiva per il routing delle chiamate di emergenza ed eventualmente per la connettività dei partner.

Per ulteriori informazioni sui concetti e sulla terminologia relativi alle chiamate di emergenza e su come configurare le chiamate di emergenza e le chiamate di emergenza dinamiche, vedere gli articoli seguenti:

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md)
- [Gestire i criteri delle chiamate di emergenza](manage-emergency-calling-policies.md)
- [Gestire i criteri del routing delle chiamate di emergenza per l’instradamento diretto](manage-emergency-call-routing-policies.md)
- [Case study di Contoso: Chiamate di emergenza](voice-case-study-emergency-calling.md)<br>
  Descrive come un'azienda multinazionale fittizia, Contoso, ha implementato le chiamate di emergenza per l'organizzazione.


### <a name="network-topology-for-voice-features"></a>Topologia di rete per le funzionalità vocali

Se si distribuiscono chiamate di emergenza dinamiche o Location-Based routing diretto, è necessario configurare le impostazioni di rete per l'utilizzo con queste funzionalità in Microsoft Teams. Per informazioni su come configurare le impostazioni di rete per aree di rete, siti di rete, subnet di rete e indirizzi IP attendibili, vedere gli articoli seguenti:

- [Impostazioni di rete per le funzionalità vocali cloud in Microsoft Teams - Concetti e terminologia](cloud-voice-network-settings.md)
- [Gestire la topologia di rete per le funzionalità vocali del cloud in Microsoft Teams](manage-your-network-topology.md)



