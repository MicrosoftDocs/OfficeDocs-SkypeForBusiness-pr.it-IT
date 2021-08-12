---
title: Preparare la distribuzione del servizio vocale cloud
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Usare gli elenchi di controllo di onboarding per preparare Microsoft 365 o Office 365 per Teams e configurare Teams funzionalità di base, rete e carichi di lavoro vocali cloud.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a8aa2818cb2b4be85054f8804fa6a11112c4e8a68cc171e9b9f7191e3f3a5bfd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322918"
---
# <a name="prepare-my-service"></a>Preparare il servizio

Questo articolo offre una panoramica dei requisiti per la preparazione dei servizi vocali cloud per l'organizzazione. La preparazione corretta consente di essere certi di essere pronti a fornire funzionalità vocali cloud all'organizzazione.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Elenchi di controllo per l'onboarding Microsoft Teams dei carichi di lavoro vocali

Gli elenchi di controllo seguenti illustrano i passaggi per l'implementazione delle funzionalità di audioconferenza, Sistema telefonico con piani per chiamate ("Piani per chiamate") e funzionalità di Sistema telefonico Direct Routing ("Instradamento diretto") in Microsoft Teams.

*  [Preparare Microsoft 365 o Office 365 per Teams](onboarding-checklist-enable-office-365.md)

*  [Configurare le Teams principali](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Preparare la rete](prepare-network.md)

*  [Configurare i carichi di lavoro vocali cloud in Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurare il routing diretto in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Le attività e le attività in questi elenchi di controllo sono le attività principali che si applicano a ogni distribuzione di funzionalità vocali cloud con Teams. È possibile personalizzare gli elenchi di controllo in modo da includere le attività e le attività specifiche per il proprio Teams viaggio.

>[!NOTE]
>Queste indicazioni sono incentrate esclusivamente su Piani per chiamate, audioconferenze e routing diretto. Se non si ha la Teams, vedere Panoramica [di Microsoft Teams](teams-overview.md). Per indicazioni generali sulla pianificazione della distribuzione Teams, iniziare con Distribuire [chat, team,](deploy-chat-teams-channels-microsoft-teams-landing-page.md)canali e app in Microsoft Teams.

Usare gli elenchi di controllo forniti per tenere traccia dello stato di ogni singola attività e attività e per assicurarsi di non aver ignorato i passaggi critici. Ogni attività include una descrizione dettagliata delle azioni richieste e riferimenti a informazioni aggiuntive che è possibile usare per completare l'attività.

Anche se è consigliabile seguire gli elenchi di controllo nell'ordine indicato, la sequenza esatta dipenderà dall'ambito della distribuzione e dalla configurazione e dalla complessità dell'ambiente. Sono organizzate per supportare una distribuzione Teams "greenfield" (una senza presenza Skype for Business Online precedente) o per eseguire la migrazione da Skype for Business Online a Teams. Se si esegue la migrazione da Skype for Business Online, è possibile che alcune di queste attività sono già state completate e che ora sia possibile ignorarle.

Quando si esegue l'onboarding degli utenti in base al sito, è consigliabile usare il Playbook di abilitazione del sito per la voce [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) come guida supplementare a questi elenchi di controllo.

>[!NOTE]
>La maggior parte delle impostazioni di configurazione sono comuni tra Teams e Skype for Business Online. Usare l'interfaccia Amministrazione Microsoft 365 e Microsoft Teams di amministrazione per configurare queste impostazioni.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Who sarà responsabile della supervisione del completamento degli elenchi di controllo per l'onboarding?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Scaricare gli elenchi di controllo per l'onboarding.</li><li>Usare gli elementi dell'elenco di controllo per l'onboarding in modo dettagliato in base al piano di distribuzione dell'organizzazione.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuare l'onboarding

Dopo aver completato questi elenchi di controllo, le funzionalità vocali sono state aggiunte correttamente alla Teams distribuzione.

Come passaggio successivo, usare il Playbook di abilitazione del sito per la voce [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) per facilitare l'onboarding degli utenti in ogni sito e garantire la pianificazione e l'esecuzione di importanti attività specifiche del sito.

-   Ready Site by Site Rollout Plan

-   Definizione del processo di gestione dei servizi

-   Eseguire test e correzioni

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Testare i carichi di lavoro vocali nel cloud in Teams

Dopo aver definito e documentato i piani di successo e implementazione tecnica di Teams cloud voice nell'ambito della fase Envision e aver intrapreso la configurazione desiderata nell'interfaccia di amministrazione, il passaggio successivo consiste nel verificare che le aspettative e i requisiti dell'organizzazione siano soddisfatti tramite funzionalità, funzionalità e usabilità. È consigliabile eseguire questo passaggio di convalida prima di distribuire una distribuzione pilota o finale nell'ambiente di produzione.

È possibile sfruttare il piano di successo aziendale definito durante la fase di Envision per fungere da base per determinare le attività, le aspettative, i test case di funzionalità/funzionalità e l'ambito generale da valutare durante la fase di test.

## <a name="define-your-testing-approach"></a>Definire l'approccio di test

Nella sua forma più semplice, l'approccio di test si basa sulla revisione delle funzionalità del servizio audioconferenza, piani per chiamate o routing diretto e sullo sviluppo di un piano di test per verificare che i requisiti di funzionalità siano soddisfatti per gli utenti nell'ambito. Di seguito è riportato un piano di test di esempio per la fase onboard di un'implementazione di audioconferenza.


| Funzionalità di audioconferenza da testare | Riepilogo dei risultati | Note aggiuntive |
|------------|-----------------|------------------|
| Pianificare una riunione ad hoc Teams conferenza telefonica con accesso esterno | Pass/Fail   | TBD |
| Usare un telefono per l'audio della riunione componendo una riunione dalla RETE PSTN con le informazioni di accesso fornite | Pass/Fail | TBD |
| Partecipare ad altre persone a una riunione esistente tramite chiamata in uscita tramite PSTN | Pass/Fail | TBD |



| Piani per chiamate o funzionalità di instradamento diretto da testare | Riepilogo dei risultati | Note aggiuntive |
|----------------------------------------------------|-----------------|------------------|
| Effettuare una chiamata PSTN componendo un numero PSTN       | Pass/Fail       | TBD |
| Ricevere una chiamata PSTN componendo il numero PSTN da una linea esterna (cellulare, rete fissa) | Pass/Fail | TBD|
| Trasferire una chiamata PSTN da un Teams utente a un altro | Pass/Fail | TBD |


>[!TIP]
>Per agevolare la creazione di test case come punto di partenza, vedere l'elenco delle indicazioni per l'utente disponibili in [Riunioni e chiamate di Teams.](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurare i carichi di lavoro vocali cloud per Teams

Dopo aver definito l'approccio di test, il passaggio successivo consiste nella configurazione dell'ambiente del servizio e degli utenti nell'ambito Teams cloud voice.

Per altre informazioni, vedere:

- [Pianificazione tecnica per le audioconferenze](./cloud-voice-landing-page.md)

- [Configurare Audioconferenza per Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Pianificazione tecnica per Sistema telefonico piani per chiamate](calling-plan-landing-page.md)

- [Configurare piani per chiamate per Skype for Business e Microsoft Teams](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Pianificare Instradamento diretto](./direct-routing-plan.md)

- [Configurare Instradamento diretto](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>Eseguire il piano di test

[//]: # (Modificare ok? "Utente" mi sembrava un po' ambiguo.)
Dopo aver configurato l'ambiente utente e il servizio, l'ultimo passaggio di test include l'esecuzione del piano di test con lo stato attivo sulla convalida delle funzionalità e delle funzionalità. 

**Prerequisiti e presupposti per il test delle audioconferenze per utenti e siti nell'ambito:**

-   La definizione del caso di utilizzo aziendale per il servizio di audioconferenza è stata completata.

-   Le licenze necessarie per le audioconferenze sono disponibili e sono state assegnate.

-   L'elenco dei siti dell'organizzazione e dei gruppi di utenti è stato identificato.

-   L'elenco dei numeri dedicati e condivisi per i servizi di audioconferenza è stato identificato e configurato.

-   [I Crediti comunicazioni](what-are-communications-credits.md) (se necessario) sono stati impostati per l'organizzazione.

-   Le impostazioni del bridge di conferenza audioconferenza sono state identificate e configurate (lunghezza PIN, notifiche di entrata/uscita, preferenza di notifica di abilitazione).

-   I criteri di conferenza tenant e le impostazioni del piano di chiamata che supportano gli scenari di chiamata in uscita per i servizi di audioconferenza sono stati identificati, configurati e applicati.

-   I requisiti di conformità delle audioconferenze sono stati identificati e configurati.

**Piani di chiamata che verificano prerequisiti e presupposti per utenti e siti nell'ambito:**

-   La definizione del caso d'uso aziendale per il servizio Piani per chiamate è stata completata.

-   La licenza necessaria per i Piani per chiamate è disponibile ed è stata assegnata.

-   L'elenco dei siti dell'organizzazione e dei gruppi di utenti è stato identificato.

-   Telefono i numeri da assegnare agli utenti sono stati acquisiti o esportati in Microsoft e sono disponibili nel portale tenant.

-   [I Crediti comunicazioni](what-are-communications-credits.md) (se necessario) sono stati impostati per l'organizzazione.

-   I criteri utente tenant e le impostazioni del piano di chiamata che supportano gli scenari di piani di chiamata sono stati identificati, configurati e applicati.

-   I requisiti di conformità dei piani di chiamata sono stati identificati e configurati.

**Prerequisiti e presupposti per il test del routing diretto per utenti e siti nell'ambito:**

-   La definizione del caso di utilizzo aziendale per il servizio di routing diretto è stata completata.

-   Le licenze necessarie per l'instradamento diretto sono disponibili e sono state assegnate.

-   L'elenco dei siti dell'organizzazione e dei gruppi di utenti è stato identificato.

-   Un [controller SBC (Certified Session Border Controller)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) è stato distribuito, configurato e associato a Sistema telefonico.

-   Enterprise voce è stata abilitata e i numeri di telefono sono stati assegnati.

-   I criteri di routing vocale sono stati identificati, configurati e assegnati.

-   Microsoft Teams è stato impostato come client di chiamata preferito per gli utenti nell'ambito.
 
-   I requisiti di conformità del routing diretto sono stati identificati e configurati.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere quali funzionalità di audioconferenza verranno distribuite (decisione del servizio).</li><li>Identificare i requisiti di funzionalità utente per le audioconferenze.</li><li>Identificare i requisiti di configurazione del servizio per le audioconferenze.</li><br><li>Decidere se il routing diretto o i piani per chiamate verranno distribuiti e configurati.<li>Decidere quali funzionalità Sistema telefonico verranno distribuite (decisione del servizio).</li><li>Identificare i requisiti di funzionalità utente per i piani per chiamate o il routing diretto.</li><li>Identificare i requisiti di configurazione del servizio per i piani per chiamate o il routing diretto.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Sviluppare e documentare l'approccio del piano di test.</li><li>Preparare l'ambiente del servizio e gli utenti nell'ambito per le funzionalità di audioconferenza.</li><li>Preparare l'ambiente del servizio e gli utenti nell'ambito per le funzionalità Piani per chiamate o Instradamento diretto.</li><li>Eseguire la convalida di test per le funzionalità di audioconferenza da abilitare.</li><li>Eseguire la convalida dei test per le funzionalità Piani per chiamate o Routing diretto che si vuole abilitare.</li><li>Per eventuali errori di test, verificare che la configurazione sia corretta, esaminare gli articoli della community e, se necessario, sollevare un caso di supporto.</li></ul></td></tr>
</table>


Per altre istruzioni dettagliate su come eseguire i test per le audioconferenze in Teams, vedere la guida dettagliata ai [test per le audioconferenze.](./deploy-audio-conferencing-teams-landing-page.md)

Per altre indicazioni dettagliate su come eseguire i test per i piani per chiamate in Teams, vedere la guida dettagliata ai [test per Sistema telefonico](./cloud-voice-landing-page.md).

<!--ENDOFSECTION-->