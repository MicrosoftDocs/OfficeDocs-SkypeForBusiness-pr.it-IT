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
description: Altre informazioni sulle opzioni di Teams chiamate (connettività PSTN) e sulle decisioni che verranno prese per l'organizzazione.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f37265a445a4b7361cdda8e6729944bb5250b029
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675808"
---
# <a name="pstn-connectivity-options"></a>Opzioni di connettività PSTN

Microsoft offre funzionalità PBX (Private Branch Exchange) complete per l'organizzazione tramite Sistema telefonico. Tuttavia, per consentire agli utenti di effettuare chiamate all'esterno dell'organizzazione, è necessario connettersi Sistema telefonico alla rete PSTN (Public Switched Telephone Network).

Questo articolo è incentrato sulle opzioni di connettività PSTN. Per altre informazioni sulle soluzioni vocali Microsoft, inclusi i dettagli sulle funzionalità di Sistema telefonico, vedi [Pianificare la soluzione Teams voce](cloud-voice-landing-page.md).

Per connettere Sistema telefonico a PSTN, è possibile scegliere una delle opzioni seguenti:

- [**Piano per chiamate**](#phone-system-with-calling-plan). Una soluzione all-in-the-cloud con Microsoft come gestore PSTN.

- [**Connessione con operatore**](#phone-system-with-operator-connect). Con Connessione con operatore, se il gestore esistente partecipa al programma Microsoft Connessione con operatore, potrà gestire le chiamate PSTN e i controller dei confini della sessione.

- [**Routing diretto**](#phone-system-with-direct-routing), che consente di usare il proprio gestore PSTN connettendo i controller SBC (Session Border Controller) a Sistema telefonico.

È anche possibile scegliere una combinazione di opzioni che consente di progettare una soluzione per un ambiente complesso o di gestire una migrazione in più passaggi.

L'opzione o le opzioni scelte influiscono sulla configurazione di alcune caratteristiche Sistema telefonico. Per altre informazioni, vedere [Considerazioni sulla configurazione](#configuration-considerations) più avanti in questo articolo.

## <a name="phone-system-with-calling-plan"></a>Sistema telefonico con piano per chiamate

Sistema telefonico con Piano per chiamate è la soluzione vocale all-in-the-cloud di Microsoft per gli utenti Teams. Questa soluzione è l'opzione più semplice che connette Sistema telefonico alla rete PSTN. Con questa opzione, Microsoft funge da gestore PSTN, come illustrato nel diagramma seguente:

![Il diagramma 1 mostra Sistema telefonico con Il piano per chiamate.](media/voice-solutions-simple.png)

Se rispondi sì a quanto segue, Sistema telefonico con Piano per chiamate è la soluzione giusta per te:

- Il piano per chiamate è disponibile nella tua area geografica.
- Non è necessario conservare l'attuale gestore PSTN.
- Si vuole usare l'accesso gestito da Microsoft alla rete PSTN.

Con questa opzione:

- Ottieni Sistema telefonico con piani per chiamate nazionali o internazionali aggiunti che consentono di chiamare i telefoni di tutto il mondo (a seconda del livello di servizio concesso in licenza).

- Non è necessaria la distribuzione o la manutenzione di una distribuzione&mdash;locale perché il piano per chiamate funziona fuori Microsoft 365.

- Nota: puoi connettere un session border controller (SBC) supportato tramite Direct Routing per l'interoperabilità con PBX di terze parti, dispositivi analogici e altri dispositivi di telefonia supportati da SBC.

Questa opzione richiede una connessione senza interruzioni a Microsoft 365.

Per ulteriori informazioni sul Piano per chiamate, vedi gli articoli seguenti:

- [Qual è il piano di chiamata adatto alle proprie esigenze?](calling-plan-landing-page.md)
- [Come acquistare un piano di chiamata](calling-plans-for-office-365.md)
- [Disponibilità di Piano di chiamata in Paesi e aree geografiche](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Configurare il piano per chiamate](set-up-calling-plans.md)

## <a name="phone-system-with-operator-connect"></a>Sistema telefonico con Connessione con operatore

Con Connessione con operatore, se il gestore telefonico esistente partecipa al programma Microsoft Connessione con operatore, potrà gestire il servizio per portare le chiamate PSTN a Teams. Il gestore gestisce i servizi di chiamata PSTN e i controller dei confini della sessione, consentendoti di risparmiare sull'acquisto e la gestione dell'hardware.

Connessione con operatore potrebbe essere la soluzione giusta per l'organizzazione se:

- Il piano per chiamate Microsoft non è disponibile nella tua posizione geografica.
- Il gestore preferito è un partecipante al programma Microsoft Connessione con operatore.
- Vuoi trovare un nuovo gestore telefonico per abilitare le chiamate in Teams.

Per informazioni sui vantaggi e i requisiti di Connessione con operatore e per un elenco dei vettori che partecipano a questo programma, vedi [Plan Connessione con operatore](operator-connect-plan.md). Per informazioni su come configurare Connessione con operatore, vedere [Configurare Connessione con operatore](operator-connect-configure.md).

## <a name="phone-system-with-direct-routing"></a>Sistema telefonico con routing diretto

Questa opzione consente di connettere Sistema telefonico alla rete telefonica tramite direct routing, come illustrato nel diagramma seguente: 

![Il diagramma 5 mostra Sistema telefonico con routing diretto.](media/voice-solution-with-direct-routing.png)

Se rispondi sì alle domande seguenti, Sistema telefonico con Direct Routing è la soluzione giusta per te:

- Si vuole usare Teams con Sistema telefonico.
- È necessario mantenere l'attuale gestore PSTN.
- Vuoi combinare il routing, con alcune chiamate che passano attraverso il Piano per chiamate, alcune attraverso il tuo operatore.
- È necessario interagire con PBX e/o apparecchiature di terze parti, ad esempio pager overhead, dispositivi analogici e così via.

Con questa opzione:

- È possibile connettere il proprio session border controller (SBC) supportato a Sistema telefonico senza la necessità di software locale aggiuntivo.

- È possibile utilizzare praticamente qualsiasi operatore di telefonia con Sistema telefonico.

- Puoi configurare e gestire questa opzione oppure può essere configurata e gestita dal gestore o dal partner (chiedi se il gestore o il partner fornisce questa opzione).

- È possibile configurare l'interoperabilità tra dispositivi&mdash;di telefonia quali PBX di terze parti e dispositivi&mdash;analogici e Sistema telefonico.

Questa opzione richiede quanto segue:

- Connessione senza interruzioni a Microsoft 365.

- Distribuzione e gestione di una scheda SBC supportata.

- Contratto con un vettore di terze parti.
  A meno che non sia stato distribuito come opzione per fornire la connessione a PBX di terze parti, dispositivi analogici o altri dispositivi di telefonia per gli utenti che hanno Sistema telefonico con il piano per chiamate.

Per altre informazioni sull'instradamento diretto, vedere gli articoli seguenti:

- [Pianificare Instradamento diretto](direct-routing-plan.md)
- [Configurare Instradamento diretto](direct-routing-configure.md)
- [Gestire i criteri di routing vocale da usare con l'instradamento diretto](manage-voice-routing-policies.md)
- [Pianificare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-plan.md)
- [Elenco di Session Border Controller certificati per Instradamento diretto](direct-routing-border-controllers.md)

## <a name="configuration-considerations"></a>Considerazioni sulla configurazione

La maggior parte delle caratteristiche Sistema telefonico sono uguali indipendentemente dall'opzione di connettività PSTN scelta. Ad esempio, sono disponibili impostazioni di chiamata senza risposta e inoltro, trasferimento di chiamata, musica personalizzata in attesa, parcheggio di chiamata, linea condivisa e app vocali. Per un elenco completo delle funzionalità di Sistema telefonico, vedi [Ecco cosa ottieni con Sistema telefonico](here-s-what-you-get-with-phone-system.md).

Esistono tuttavia alcune differenze nelle funzionalità che influiscono sulla configurazione di determinate caratteristiche di Sistema telefonico. Ad esempio, il routing diretto richiede passaggi aggiuntivi per configurare il routing delle chiamate. Come altro esempio, direct routing provides Location-Based-Routing (LBR). LBR consente di limitare il bypass a pedaggio in determinate aree geografiche in cui non è consentito. 

La tabella seguente evidenzia le differenze di configurazione principali. Le sezioni che seguono la tabella forniscono collegamenti ad altre informazioni e dettagli.

| Opzione | Descrizione | gestione dei numeri di Telefono | Routing delle chiamate | Disponibilità per le chiamate di emergenza |
| :------------| :-------| :-------| :-------| :-------| 
| Piani di chiamata | -Microsoft funge da gestore PSTN.<br>-Non è necessario acquistare o gestire le schede SBC.| Ottenuto tramite Microsoft.| -Gestito da Microsoft. <br> -Amministrazione configura i piani di chiamata utente per la traduzione dei numeri. | -Abilitato da Microsoft. <br> -Amministrazione registra gli indirizzi. <br> -Chiamate dinamiche supportate. |
| Connessione con operatore | -Carrier gestisce la connettività PSTN e gli SBC. <br> -Non è necessario acquistare o gestire le schede SBC. | -Ottenuto tramite vettore. <br> - Numeri associati agli indirizzi di emergenza gestiti dal gestore telefonico. | -Gestito dal vettore. <br>-Amministrazione configura i piani di chiamata utente per la traduzione dei numeri. | -Abilitato dal vettore. <br> -Amministrazione registra gli indirizzi. <br> -Chiamate dinamiche supportate. |
| Routing diretto | -Richiede la certificazione SBC acquistata da fornitori di terze parti.<br>-Connessione il tuo SBC a Sistema telefonico.<br> -Usare il gestore PSTN esistente. | Ottenuti tramite vettore. | -Richiede una configurazione aggiuntiva da parte dell'amministratore.<br>-Amministrazione configura i piani di chiamata trunk per la traduzione dei numeri. <br>-LBR disponibile per limitare il bypass a pagamento. | -Richiede una configurazione aggiuntiva da parte dell'amministratore. <br>-Indirizzi registrati non supportati. <br>-Chiamate dinamiche supportate ma richiede una configurazione aggiuntiva. |

### <a name="phone-number-management"></a>gestione dei numeri di Telefono

Microsoft dispone di due tipi di numeri di telefono disponibili: numeri abbonati (utente), che possono essere assegnati agli utenti dell'organizzazione, e numeri di servizio, disponibili come numeri di servizio a pagamento e gratuiti. I numeri di servizio hanno una capacità di chiamata simultanea superiore rispetto ai numeri degli abbonati e possono essere assegnati a servizi come Audioconferenza, operatori automatici o code di chiamata.

Dovrai decidere:

- Quali posizioni degli utenti richiedono nuovi numeri di telefono da Microsoft?
- Quale tipo di numero di telefono (abbonato o servizio) mi serve?
- Ricerca per categorie trasferire i numeri di telefono esistenti in Teams?

La modalità di acquisizione e gestione dei numeri di telefono varia in base all'opzione di connettività PSTN.

- Per informazioni sulla gestione dei numeri di telefono per il Piano per chiamate, vedi [Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Per informazioni sulla gestione dei numeri di telefono con Connessione con operatore, vedi [Configurare i numeri di telefono con Connessione con operatore](operator-connect-configure.md#set-up-phone-numbers).

- Per informazioni sulla gestione dei numeri di telefono per il routing diretto, vedi [Configurare il numero di telefono e abilitare la voce aziendale](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).

### <a name="call-routing-and-dial-plans"></a>Routing delle chiamate e piani di chiamata

La configurazione del routing delle chiamate varia in base all'opzione di connettività PSTN.  

- Per i Piani per chiamate, la maggior parte del routing delle chiamate viene gestita dall'infrastruttura del piano per chiamate Microsoft. È possibile configurare piani di chiamata utente ai fini della traduzione del numero per l'autorizzazione delle chiamate e il routing delle chiamate. Per altre informazioni, vedere [Che cosa sono i piani di chiamata?](what-are-dial-plans.md).

- Per Connessione con operatore, la maggior parte del routing delle chiamate viene gestita dal gestore telefonico.  È possibile configurare piani di chiamata utente ai fini della traduzione del numero per l'autorizzazione delle chiamate e il routing delle chiamate. Per altre informazioni, vedere [Che cosa sono i piani di chiamata?](what-are-dial-plans.md).

- Per l'instradamento diretto, è necessario configurare il routing delle chiamate specificando le route vocali e assegnando criteri di routing vocale agli utenti. È possibile configurare piani di chiamata per la traduzione dei numeri a livello di trunk per garantire l'interoperabilità con i controller di session border (SBC). Per altre informazioni, vedere [Configurare il routing vocale per il routing diretto](direct-routing-voice-routing.md), [Gestire i criteri di routing vocale](manage-voice-routing-policies.md) e [Tradurre numeri di telefono](direct-routing-translate-numbers.md). 

### <a name="location-based-routing-for-direct-routing"></a>routing Location-Based per routing diretto

In alcuni paesi e aree geografiche, è illegale bypassare il vettore PSTN per ridurre i costi delle chiamate interurbane. Location-Based Routing (LBR) per direct routing consente di limitare il bypass a pagamento per Teams utenti in base alla loro posizione geografica. Per ulteriori informazioni su come pianificare e configurare l'LBR, vedere gli articoli seguenti:

- [Pianificare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-plan.md)
- [Configurare le impostazioni di rete per l'instradamento basato sulla posizione](location-based-routing-configure-network-settings.md)
- [Abilitare l'instradamento basato sulla posizione per Instradamento diretto](location-based-routing-enable.md)
- [Case study contoso: routing Location-Based](voice-case-study-location-based-routing.md)<br>
  Descrive in che modo una società multinazionale fittizia, Contoso, ha implementato Location-Based Routing per l'organizzazione.

### <a name="emergency-calling"></a>Chiamate di emergenza

La configurazione delle chiamate di emergenza varia in base all'opzione di connettività PSTN.

- Per il Piano per chiamate, ogni utente viene abilitato automaticamente per le chiamate di emergenza. L'utente deve avere un indirizzo di emergenza registrato associato al numero di telefono assegnato. Sono supportate le chiamate di emergenza dinamiche (in base alla posizione del client Teams).  

- Per Connessione con operatore, ogni utente viene abilitato automaticamente per le chiamate di emergenza. All'utente è richiesto di avere un indirizzo di emergenza registrato associato al numero di telefono assegnato,r, ma l'indirizzo può essere impostato solo dal partner del vettore. Sono supportate le chiamate di emergenza dinamiche (in base alla posizione del client Teams).

- Per il routing diretto, è necessario definire criteri per le chiamate di emergenza per gli utenti utilizzando un criterio di routing delle chiamate di emergenza Teams (TeamsEmergencyCallRoutingPolicy). I criteri definiranno i numeri di emergenza e la destinazione di routing associata. Le posizioni registrate per gli interventi di emergenza non sono supportate per gli utenti di Direct Routing. Per le chiamate di emergenza dinamiche, è necessaria una configurazione aggiuntiva per l'instradamento delle chiamate di emergenza ed eventualmente per la connettività dei partner.

Per ulteriori informazioni sui concetti e la terminologia relativi alle chiamate di emergenza e su come configurare le chiamate di emergenza e le chiamate di emergenza dinamiche, vedi gli articoli seguenti:

- [Gestire le chiamate di emergenza](what-are-emergency-locations-addresses-and-call-routing.md)
- [Pianificare e configurare chiamate di emergenza dinamiche](configure-dynamic-emergency-calling.md)
- [Gestire i criteri delle chiamate di emergenza](manage-emergency-calling-policies.md)
- [Gestire i criteri di routing delle chiamate di emergenza per il routing diretto](manage-emergency-call-routing-policies.md)
- [Case study contoso: chiamate di emergenza](voice-case-study-emergency-calling.md)<br>
  Descrive in che modo una società multinazionale fittizia, Contoso, ha implementato chiamate di emergenza per l'organizzazione.

### <a name="network-topology-for-voice-features"></a>Topologia di rete per le funzionalità vocali

Se stai distribuendo chiamate di emergenza dinamiche o Location-Based Routing per il routing diretto, devi configurare le impostazioni di rete per queste funzionalità in Microsoft Teams. Per informazioni su come configurare le impostazioni di rete per aree di rete, siti di rete, subnet di rete e indirizzi IP attendibili, vedere gli articoli seguenti:

- [Impostazioni di rete per le funzionalità vocali cloud in Microsoft Teams - Concetti e terminologia](cloud-voice-network-settings.md)
- [Gestire la topologia di rete per le funzionalità di voce cloud in Microsoft Teams](manage-your-network-topology.md)
