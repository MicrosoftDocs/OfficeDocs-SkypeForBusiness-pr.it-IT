---
title: Preparare la distribuzione del servizio voce cloud
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Usare gli elenchi di controllo onboarding per preparare Microsoft 365 o Office 365 per Teams e configurare funzionalità di base Teams, funzionalità di rete e carichi di lavoro voce cloud.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a91a57a077db38675a62238289ad2c204040a9cd
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675438"
---
# <a name="prepare-my-service"></a>Preparare il servizio

Questo articolo offre una panoramica dei requisiti per la preparazione dei servizi vocali cloud per l'organizzazione. Preparandosi correttamente, è possibile essere certi di essere pronti a fornire funzionalità di voce cloud all'organizzazione.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Elenchi di controllo onboarding per carichi di lavoro vocali Microsoft Teams

Gli elenchi di controllo seguenti forniscono istruzioni dettagliate per implementare Audioconferenza, Sistema telefonico con piani per chiamate ("Piani per chiamate") e Sistema telefonico funzionalità Routing diretto (Direct Routing) in Microsoft Teams.

*  [Preparare Microsoft 365 o Office 365 per Teams](onboarding-checklist-enable-office-365.md)

*  [Configurare Teams funzionalità di base](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Preparare la rete](prepare-network.md)

*  [Configurare i carichi di lavoro vocali nel cloud in Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurare il routing diretto in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Le attività e le attività in questi elenchi di controllo sono gli elementi di base delle attività che si applicano a ogni distribuzione di funzionalità vocali nel cloud con Teams. È possibile personalizzare gli elenchi di controllo per includere le attività e le attività specifiche del proprio percorso Teams.

>[!NOTE]
>Queste linee guida sono incentrate esclusivamente su Piani per chiamate, Audioconferenza e Routing diretto. Se non si ha familiarità con Teams, vedere [Panoramica di Microsoft Teams](teams-overview.md). Per indicazioni generali su come pianificare la distribuzione di Teams, iniziare con [Distribuire chat, team, canali e app in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).

Usare gli elenchi di controllo forniti per tenere traccia dello stato di ogni singola attività e attività e per assicurarsi di non aver ignorato i passaggi critici. Ogni attività include una descrizione dettagliata delle azioni richieste e riferimenti a informazioni aggiuntive che è possibile usare per completare l'attività.

Anche se è consigliabile seguire gli elenchi di controllo in ordine, la sequenza esatta dipenderà dall'ambito della distribuzione e dalla configurazione e dalla complessità dell'ambiente. Sono organizzati per supportare una distribuzione "greenfield" Teams (senza presenza Skype for Business online precedente) o la migrazione da Skype for Business Online a Teams. Se si esegue la migrazione da Skype for Business Online, alcune di queste attività potrebbero essere già state completate e possono essere ignorate.

Durante l'onboarding degli utenti per sito, ti consigliamo vivamente di utilizzare il [Playbook for Voice (Playbook) per l'abilitazione del sito](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) come guida supplementare per questi elenchi di controllo.

>[!NOTE]
>La maggior parte delle impostazioni di configurazione sono comuni tra Teams e Skype for Business Online. Per configurare queste impostazioni, è possibile usare il Centro Amministrazione Microsoft 365 e l'interfaccia di amministrazione di Microsoft Teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Who sarà responsabile della supervisione del completamento degli elenchi di controllo di onboarding?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Scarica gli elenchi di controllo per l'onboarding.</li><li>Esaminare le voci dell'elenco di controllo di onboarding passo dopo passo in base al piano di distribuzione dell'organizzazione.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continua l'onboarding

Dopo aver completato questi elenchi di controllo, le funzionalità vocali saranno state aggiunte correttamente alla distribuzione di Teams.

Come passaggio successivo, usare il [Playbook di abilitazione del sito per la voce (Playbook) per](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) aggiungere gli utenti in ogni sito e garantire la pianificazione e l'esecuzione di attività importanti specifiche del sito.

-   Pronto sito per piano di implementazione del sito

-   Stabilire il processo di gestione dei servizi

-   Eseguire test e correzioni

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Testare i carichi di lavoro vocali nel cloud in Teams

Dopo aver definito e documentato i piani di successo e implementazione tecnica del business cloud voice Teams nell'ambito della fase Divisione e aver intrapreso la configurazione desiderata nell'interfaccia di amministrazione, il passaggio successivo consiste nel verificare che le aspettative e i requisiti dell'organizzazione siano soddisfatti tramite caratteristiche, funzionalità e usabilità. Eseguire questo passaggio di convalida prima di distribuire una distribuzione pilota o finale nell'ambiente di produzione.

È possibile sfruttare il piano di successo aziendale definito durante la fase Division per fungere da base per determinare le attività, le aspettative, i test case di caratteristiche/funzionalità e l'ambito generale da valutare durante la fase di test.

## <a name="define-your-testing-approach"></a>Definire l'approccio di test

Nella sua forma più semplice, l'approccio di test si basa sulla verifica delle funzionalità del servizio Audioconferenza, Piani per chiamate o Routing diretto e sullo sviluppo di un piano di test per verificare che i requisiti di funzionalità siano soddisfatti per gli utenti nell'ambito. Di seguito è riportato un esempio di piano di test per la fase onboard di un'implementazione dei servizi di audioconferenza.


| Audioconferenza funzionalità da testare | Riepilogo dei risultati | Note aggiuntive |
|------------|-----------------|------------------|
| Pianificare una riunione Teams ad-hoc contenente informazioni di accesso esterno per i servizi di audioconferenza | Pass/Fail   | TBD |
| Usare un telefono per l'audio della riunione eseguendo l'accesso a una riunione dal pstn con le informazioni per l'accesso esterno fornite | Pass/Fail | TBD |
| Partecipare ad altre persone a una riunione esistente tramite chiamata in uscita tramite PSTN | Pass/Fail | TBD |



| Piani per chiamate o funzione Routing diretto da testare | Riepilogo dei risultati | Note aggiuntive |
|----------------------------------------------------|-----------------|------------------|
| Effettuare una chiamata PSTN componendo un numero PSTN       | Pass/Fail       | TBD |
| Ricevere una chiamata PSTN componendo il numero PSTN da una linea esterna (cellulare, rete fissa) | Pass/Fail | TBD|
| Trasferire una chiamata PSTN da un utente Teams a un altro | Pass/Fail | TBD |


>[!TIP]
>Per facilitare la creazione di test case come punto di partenza, vedere l'elenco delle indicazioni utente disponibili in [riunioni e chiamate Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurare i carichi di lavoro vocali cloud per Teams

Dopo aver definito l'approccio di test, il passaggio successivo consiste nel configurare l'ambiente del servizio e gli utenti nell'ambito per Teams funzionalità di voce cloud.

Per ulteriori informazioni, vedere:

- [Pianificazione tecnica per Audioconferenza](./cloud-voice-landing-page.md)

- [Configurare Audioconferenza per Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Pianificazione tecnica per Sistema telefonico con piani per chiamate](calling-plan-landing-page.md)

- [Configurare i piani per chiamate per Skype for Business e Microsoft Teams](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Pianificare Instradamento diretto](./direct-routing-plan.md)

- [Configurare Instradamento diretto](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>Eseguire il piano di test

[//]: # (Modificare va bene? "Utente" mi sembrava un po' ambiguo.)
Dopo aver configurato l'ambiente utente e il servizio, l'ultimo passaggio del test include l'esecuzione del piano di test con lo stato attivo sulla convalida delle caratteristiche e delle funzionalità. 

**Audioconferenza test dei prerequisiti e delle ipotesi per gli utenti e i siti nell'ambito:**

-   La definizione del caso di utilizzo aziendale per il servizio Audioconferenza è stata completata.

-   La licenza necessaria per Audioconferenza è disponibile ed è stata assegnata.

-   È stato identificato l'elenco dei siti dell'organizzazione e dei gruppi di utenti.

-   L'elenco di numeri per i servizi di audioconferenza dedicati e condivisi con preferenza di lingua è stato identificato e configurato.

-   [I Crediti comunicazioni](what-are-communications-credits.md) (se necessario) sono stati configurati per l'organizzazione.

-   Audioconferenza impostazioni del bridge conferenza sono state identificate e configurate (lunghezza PIN, notifiche di entrata/uscita, preferenza di notifica di abilitazione).

-   I criteri di conferenza tenant e le impostazioni del piano di chiamata che supportano Audioconferenza scenari di chiamata in uscita sono stati identificati, configurati e applicati.

-   Audioconferenza requisiti di conformità sono stati identificati e configurati.

**Piani per chiamate verifica i prerequisiti e le ipotesi per utenti e siti nell'ambito:**

-   La definizione del caso di utilizzo aziendale per il servizio Piani per chiamate è stata completata.

-   La licenza richiesta per i Piani per chiamate è disponibile ed è stata assegnata.

-   È stato identificato l'elenco dei siti dell'organizzazione e dei gruppi di utenti.

-   Telefono numeri da assegnare agli utenti sono stati acquisiti o trasferiti in Microsoft e sono disponibili nel portale tenant.

-   [I Crediti comunicazioni](what-are-communications-credits.md) (se necessario) sono stati configurati per l'organizzazione.

-   I criteri utente tenant e le impostazioni dei piani di chiamata che supportano gli scenari di Piani per chiamate sono stati identificati, configurati e applicati.

-   I requisiti di conformità per i Piani per chiamate sono stati identificati e configurati.

**Prerequisiti e ipotesi di test del routing diretto per utenti e siti nell'ambito:**

-   La definizione del caso di utilizzo aziendale per il servizio Direct Routing è stata completata.

-   La licenza necessaria per il routing diretto è disponibile ed è stata assegnata.

-   È stato identificato l'elenco dei siti dell'organizzazione e dei gruppi di utenti.

-   È stato distribuito, configurato e associato a Sistema telefonico un [controller di bordo di sessione certificato (SBC](./direct-routing-plan.md#supported-session-border-controllers-sbcs)).

-   Enterprise voce è stata abilitata e sono stati assegnati i numeri di telefono.

-   I criteri di routing vocale sono stati identificati, configurati e assegnati.

-   Microsoft Teams è stato impostato come client di chiamata preferito per gli utenti nell'ambito.
 
-   I requisiti di conformità per il routing diretto sono stati identificati e configurati.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere quali funzionalità di Audioconferenza verranno distribuite (decisione del servizio).</li><li>Identificare i requisiti di funzionalità utente per Audioconferenza.</li><li>Identificare i requisiti di configurazione del servizio per Audioconferenza.</li><br><li>Decidere se distribuire e configurare l'instradamento diretto o i piani per chiamate.<li>Decidere quali funzionalità di Sistema telefonico verranno distribuite (decisione del servizio).</li><li>Identificare i requisiti di funzionalità utente per Piani per chiamate o Routing diretto.</li><li>Identificare i requisiti di configurazione del servizio per Piani per chiamate o Routing diretto.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Sviluppare e documentare l'approccio del piano di test.</li><li>Preparare l'ambiente di servizio e gli utenti nell'ambito per Audioconferenza caratteristiche.</li><li>Preparare l'ambiente di servizio e gli utenti nell'ambito per i piani per chiamate o le funzionalità di routing diretto.</li><li>Eseguire la convalida di test per le caratteristiche di Audioconferenza da abilitare.</li><li>Esegui la convalida del test per i Piani per chiamate o le funzionalità di Routing diretto che vuoi abilitare.</li><li>Per eventuali errori di test, verifica che la configurazione sia corretta, leggi gli articoli della community e, se necessario, genera un caso di supporto.</li></ul></td></tr>
</table>


Per altre istruzioni dettagliate su come eseguire i test per Audioconferenza in Teams, vedere la [guida dettagliata ai test per Audioconferenza](./deploy-audio-conferencing-teams-landing-page.md).

Per ulteriori indicazioni dettagliate su come eseguire i test per i Piani per chiamate in Teams, vedi la [guida dettagliata ai test per Sistema telefonico](./cloud-voice-landing-page.md).

<!--ENDOFSECTION-->