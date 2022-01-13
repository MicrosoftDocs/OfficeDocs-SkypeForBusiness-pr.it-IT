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
description: Altre informazioni sulle opzioni Teams chiamate (connettività PSTN) e sulle decisioni da prendere per l'organizzazione.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49c836687d7652c18b5932bd662d8ee935638d8a
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2022
ms.locfileid: "62015276"
---
# <a name="pstn-connectivity-options"></a>Opzioni di connettività PSTN

Microsoft offre funzionalità COMPLETE Private Branch Exchange (PBX) per l'organizzazione tramite Teams Telefono. Tuttavia, per consentire agli utenti di effettuare chiamate all'esterno dell'organizzazione, è necessario connettersi Teams Telefono rete PSTN (Public Switched Telephone Network).

Questo articolo è in particolare sulle opzioni di connettività PSTN. Per altre informazioni sulle soluzioni vocali Microsoft, inclusi i dettagli sulle Teams Telefono, vedere Pianificare [la Teams vocale.](cloud-voice-landing-page.md)

Per connettersi Teams Telefono alla rete PSTN, è possibile scegliere tra le opzioni seguenti:

- [**Piano chiamate**](#teams-phone-with-calling-plan). Una soluzione all-in-the-cloud con Microsoft come gestore PSTN.

- [**Connessione con operatore**](#teams-phone-with-operator-connect). Con Connessione con operatore, se il gestore esistente è un partecipante al programma Microsoft Connessione con operatore, può gestire le chiamate PSTN e i session border controller (SBC). 

- [**Routing diretto**](#teams-phone-with-direct-routing), che consente di usare il proprio gestore PSTN collegando i controller di bordo della sessione (SBC) a Teams Telefono.


È anche possibile scegliere una combinazione di opzioni, che consente di progettare una soluzione per un ambiente complesso o di gestire una migrazione in più passaggi.

Tenere presente che l'opzione o le opzioni selezionate influiscono sulla configurazione di Teams Telefono caratteristiche. Per altre informazioni, vedere [Considerazioni sulla configurazione](#configuration-considerations) più avanti in questo articolo.


## <a name="teams-phone-with-calling-plan"></a>Servizi telefonici con piano per chiamate 

Teams Telefono piano chiamate è la soluzione vocale all-in-the-cloud di Microsoft per Teams utenti. Questa è l'opzione più semplice che Teams Telefono alla rete PSTN. Con questa opzione, Microsoft funge da gestore PSTN, come illustrato nel diagramma seguente:

![Il diagramma 1 mostra Sistema telefonico piano chiamate.](media/voice-solutions-simple.png)

Se si risponde sì a quanto segue, Teams Telefono piano per chiamate è la soluzione giusta per te:

- Piano chiamate è disponibile nella tua area geografica.
- Non è necessario conservare il gestore PSTN corrente.
- Si vuole usare l'accesso gestito da Microsoft alla rete PSTN.

Con questa opzione: 

- Puoi ottenere Teams Telefono piani per chiamate nazionali o internazionali aggiunti che consentono di chiamare verso telefoni di tutto il mondo (a seconda del livello di servizio concesso in licenza).

- Non è necessario eseguire la distribuzione o la manutenzione di una distribuzione locale perché il piano per chiamate funziona &mdash; Microsoft 365.

- Nota: se necessario, è possibile scegliere di connettere un controller SBC (Session Border Controller) supportato tramite Routing diretto per garantire l'interoperabilità con sistemi IPX di terze parti, dispositivi analogici e altre apparecchiature di telefonia di terze parti supportate da SBC.

Questa opzione richiede una connessione ininterrotta a Microsoft 365.

Per altre informazioni sul Piano chiamate, vedere gli articoli seguenti:

- [Qual è il piano di chiamata adatto alle proprie esigenze?](calling-plan-landing-page.md)
- [Come acquistare un piano di chiamata](calling-plans-for-office-365.md)
- [Disponibilità di Piano di chiamata in Paesi e aree geografiche](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Configurare il piano per le chiamate](set-up-calling-plans.md)


## <a name="teams-phone-with-operator-connect"></a>Teams Telefono con Connessione con operatore

Con Connessione con operatore, attualmente in anteprima pubblica, se il gestore esistente è un partecipante al programma Microsoft Connessione con operatore, può gestire il servizio per portare le chiamate PSTN in Teams. Il gestore gestisce i servizi di chiamata PSTN e i session border controller (SBC), consentendo di risparmiare sull'acquisto e la gestione dell'hardware.

Connessione con operatore potrebbe essere la soluzione giusta per l'organizzazione se:

- Microsoft Calling Plan non è disponibile nella tua posizione geografica.
- Il gestore preferito è un partecipante al programma Microsoft Connessione con operatore microsoft.
- Si vuole trovare un nuovo gestore per abilitare le chiamate in Teams.

Per informazioni sui vantaggi e i requisiti di Connessione con operatore e per un elenco dei corrieri che partecipano a questo programma, vedere Pianificare Connessione con operatore [.](operator-connect-plan.md) Per informazioni su come configurare i Connessione con operatore, vedere [Configurare Connessione con operatore](operator-connect-configure.md).


## <a name="teams-phone-with-direct-routing"></a>Teams Telefono routing diretto

Questa opzione consente Teams Telefono alla rete di telefonia tramite Routing diretto, come illustrato nel diagramma seguente: 

![Il diagramma 5 mostra Sistema telefonico routing diretto.](media/voice-solution-with-direct-routing.png)

Se si risponde sì alle domande seguenti, Teams Telefono il routing diretto è la soluzione giusta:

- Si vuole usare le Teams con Teams Telefono.
- È necessario conservare il gestore PSTN corrente.
- Vuoi combinare l'instradamento, con alcune chiamate che attraversano il Piano chiamate, altre tramite il tuo gestore.
- È necessario interagire con sistemi PBX e/o apparecchiature di terze parti, ad esempio test di paginazione, dispositivi analogici e così via.

Con questa opzione:

- È possibile connettere il proprio session border controller (SBC) supportato a Teams Telefono senza la necessità di software locale aggiuntivo.

- È possibile usare praticamente qualsiasi gestore di telefonia con Teams Telefono.

- È possibile scegliere di configurare e gestire questa opzione oppure può essere configurata e gestita dal gestore o dal partner (chiedere se il gestore o il partner fornisce questa opzione).

- È possibile configurare l'interoperabilità tra le apparecchiature di telefonia, ad esempio un PBX di terze parti e dispositivi &mdash; analogici &mdash; e Teams Telefono.

Questa opzione richiede quanto segue:

- Connessione ininterrotta a Microsoft 365.

- Distribuzione e gestione di un SBC supportato.

- Contratto con un gestore di terze parti.
  (A meno che non venga distribuita come opzione per fornire la connessione a PBX di terze parti, dispositivi analogici o altre apparecchiature di telefonia per gli utenti che si Teams Telefono piano chiamate.

Per altre informazioni sul routing diretto, vedere gli articoli seguenti:

- [Pianificare Instradamento diretto](direct-routing-plan.md)
- [Configurare Instradamento diretto](direct-routing-configure.md)
- [Gestire i criteri di routing vocale per l'uso con Routing diretto](manage-voice-routing-policies.md)
- [Pianificare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-plan.md)
- [Elenco di Session Border Controller certificati per Instradamento diretto](direct-routing-border-controllers.md)



## <a name="configuration-considerations"></a>Considerazioni sulla configurazione

La Teams Telefono caratteristiche sono le stesse indipendentemente dall'opzione di connettività PSTN scelta. Ad esempio, le impostazioni di chiamata senza risposta e inoltro, trasferimento di chiamata, musica personalizzata in attesa, parcheggio di chiamata, linea condivisa e app vocali sono tutte disponibili. Per un elenco completo delle Teams Telefono, vedere Ecco cosa si ottiene con [Teams Telefono.](here-s-what-you-get-with-phone-system.md)

Esistono tuttavia alcune differenze di funzionalità che influiscono sulla modalità di configurazione di alcune Teams Telefono funzionalità. Ad esempio, Il routing diretto richiede altri passaggi per configurare il routing delle chiamate. Come altro esempio, Il routing diretto fornisce il routing in base alla posizione (LBR, Location-Based-Routing), in modo che sia possibile limitare il bypass a pedaggio in determinate posizioni geografiche in cui non è consentito. 

La tabella seguente evidenzia le differenze di configurazione principali. Le sezioni che seguono la tabella forniscono collegamenti ad altre informazioni e dettagli.

| Opzione | Descrizione | Telefono gestione dei numeri | Routing delle chiamate | Disponibilità di chiamate di emergenza |
| :------------| :-------| :-------| :-------| :-------| 
| Piani di chiamata | -Microsoft funge da gestore PSTN.<br>-Non è necessario acquistare o gestire SBC.| Ottenuto tramite Microsoft.| -Gestito da Microsoft. <br> -Admin configura i piani di chiamata degli utenti per la traduzione dei numeri. | -Abilitato da Microsoft. <br> -Admin registra gli indirizzi. <br> -Chiamate dinamiche supportate. |
| Connessione con operatore | -Carrier gestisce la connettività PSTN e gli SBC. <br> -Non è necessario acquistare o gestire SBC. | -Ottenuto tramite corriere. <br> - Numeri associati agli indirizzi di emergenza gestiti dal gestore.  | -Gestito dal gestore. <br>-Admin configura i piani di chiamata degli utenti per la traduzione dei numeri. | -Abilitato dal gestore. <br> -Admin registra gli indirizzi. <br> -Chiamate dinamiche supportate. |
| Routing diretto | -Richiede SBC certificato acquistato da un fornitore di terze parti.<br>-Connessione SBC per Teams Telefono.<br> -Usare il gestore PSTN esistente. | Ottenuto tramite corriere. | -Richiede una configurazione aggiuntiva da parte dell'amministratore.<br>-Admin configura i dial plan trunk per la traduzione dei numeri. <br>-LBR disponibile per limitare il bypass a pedaggio. | -Richiede una configurazione aggiuntiva da parte dell'amministratore. <br>-Indirizzi registrati non supportati. <br>-Chiamate dinamiche supportate ma richiedono una configurazione aggiuntiva. |
|||||


### <a name="phone-number-management"></a>Telefono gestione dei numeri

Microsoft ha a disposizione due tipi di numeri di telefono: numeri abbonati (utente), che possono essere assegnati agli utenti dell'organizzazione, e numeri di servizio, disponibili come numeri di servizio a numero verde e a numero verde. I numeri di servizio hanno una capacità di chiamata simultanea superiore rispetto ai numeri degli abbonati e possono essere assegnati a servizi come audioconferenze, operatori automatici o code di chiamata.

Dovrai decidere:

- Quali posizioni degli utenti hanno bisogno di nuovi numeri di telefono da Microsoft?
- Quale tipo di numero di telefono (abbonato o servizio) è necessario?
- Come faccio a eseguire il port di numeri di telefono esistenti Teams?

La modalità di acquisizione e gestione dei numeri di telefono varia a seconda dell'opzione di connettività PSTN.

- Per informazioni sulla gestione dei numeri di telefono per il piano chiamate, vedere [Gestire i numeri di telefono per l'organizzazione.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Per informazioni sulla gestione dei numeri di telefono con Connessione con operatore, vedere Configurare i numeri [di telefono con Connessione con operatore](operator-connect-configure.md#set-up-phone-numbers).

- Per informazioni sulla gestione dei numeri di telefono per Il routing diretto, vedere Configurare il numero di telefono [e abilitare la segreteria telefonica e la segreteria telefonica aziendale.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)


### <a name="call-routing-and-dial-plans"></a>Routing delle chiamate e dial plan

La modalità di configurazione del routing delle chiamate varia a seconda dell'opzione di connettività PSTN.  

- Per i piani per chiamate, la maggior parte del routing delle chiamate è gestita dall'infrastruttura del piano per chiamate Microsoft. È possibile configurare i piani di chiamata degli utenti ai fini della traduzione dei numeri per l'autorizzazione delle chiamate e il routing delle chiamate. Per altre informazioni, vedere [Che cosa sono i dial plan?](what-are-dial-plans.md).

- Ad Connessione con operatore, la maggior parte del routing delle chiamate è gestita dal gestore.  È possibile configurare i piani di chiamata degli utenti ai fini della traduzione dei numeri per l'autorizzazione delle chiamate e il routing delle chiamate. Per altre informazioni, vedere [Che cosa sono i dial plan?](what-are-dial-plans.md).

- Per il routing diretto, è necessario configurare il routing delle chiamate specificando le route vocali e assegnando criteri di routing vocale agli utenti. È possibile configurare i dial plan per la traduzione dei numeri a livello di trunk per garantire l'interoperabilità con i session border controller (SBC). Per altre informazioni, vedere [Configurare il routing vocale per Il routing diretto,](direct-routing-voice-routing.md)Gestire i criteri di routing [vocale](manage-voice-routing-policies.md) e Tradurre i numeri [di telefono.](direct-routing-translate-numbers.md) 


### <a name="location-based-routing-for-direct-routing"></a>Location-Based routing diretto

In alcuni paesi e aree geografiche, è illegale ignorare il gestore PSTN per ridurre i costi delle chiamate interurbane. Location-Based routing (LBR) per il routing diretto consente di limitare il bypass a pedaggio per Teams utenti in base alla loro posizione geografica. Per altre informazioni su come pianificare e configurare LBR, vedere gli articoli seguenti:

- [Pianificare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-plan.md)
- [Configurare le impostazioni di rete per l'instradamento basato sulla posizione](location-based-routing-configure-network-settings.md)
- [Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)
- [Case study contoso: Location-Based Routing](voice-case-study-location-based-routing.md)<br>
  Descrive come una multinazionale fittizia, Contoso, ha implementato Location-Based routing per l'organizzazione.


### <a name="emergency-calling"></a>Chiamate di emergenza

La modalità di configurazione delle chiamate di emergenza varia a seconda dell'opzione di connettività PSTN.

- Per il Piano chiamate, ogni utente è abilitato automaticamente per le chiamate di emergenza ed è necessario avere un indirizzo di emergenza registrato associato al numero di telefono assegnato. Le chiamate di emergenza dinamiche (in base alla posizione Teams client) sono supportate.  

- Per Connessione con operatore, ogni utente è abilitato automaticamente per le chiamate di emergenza ed è necessario avere un indirizzo di emergenza registrato associato al numero di telefono assegnato, ma può essere impostato solo dal partner gestore. Le chiamate di emergenza dinamiche (in base alla posizione Teams client) sono supportate.

- Per il routing diretto, è necessario definire i criteri per le chiamate di emergenza per gli utenti usando un criterio di routing delle chiamate di emergenza Teams (TeamsEmergencyCallRoutingPolicy) per definire i numeri di emergenza e la destinazione di routing associata. Le posizioni di emergenza registrate non sono supportate per gli utenti di Routing diretto. Per le chiamate di emergenza dinamiche, è necessaria una configurazione aggiuntiva per l'instradamento delle chiamate di emergenza e, eventualmente, per la connettività dei partner.

Per altre informazioni sui concetti e la terminologia delle chiamate di emergenza e su come configurare le chiamate di emergenza e le chiamate di emergenza dinamiche, vedere gli articoli seguenti:

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md)
- [Gestire i criteri delle chiamate di emergenza](manage-emergency-calling-policies.md)
- [Gestire i criteri di routing delle chiamate di emergenza per il routing diretto](manage-emergency-call-routing-policies.md)
- [Caso di studio Contoso: Chiamate di emergenza](voice-case-study-emergency-calling.md)<br>
  Descrive come una multinazionale fittizia, Contoso, ha implementato le chiamate di emergenza per l'organizzazione.


### <a name="network-topology-for-voice-features"></a>Topologia di rete per le funzionalità vocali

Se si distribuiscono chiamate di emergenza dinamiche o Location-Based routing per il routing diretto, è necessario configurare le impostazioni di rete per l'uso con queste funzionalità in Microsoft Teams. Per informazioni su come configurare le impostazioni di rete per aree di rete, siti di rete, subnet di rete e indirizzi IP attendibili, vedere gli articoli seguenti:

- [Impostazioni di rete per le funzionalità vocali cloud in Microsoft Teams - Concetti e terminologia](cloud-voice-network-settings.md)
- [Gestire la topologia di rete per le funzionalità vocali cloud in Microsoft Teams](manage-your-network-topology.md)



