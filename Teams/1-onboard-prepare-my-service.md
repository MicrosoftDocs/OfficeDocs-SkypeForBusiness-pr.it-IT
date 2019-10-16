---
title: Preparare la distribuzione del servizio vocale cloud di Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Usare gli elenchi di controllo onboarding per preparare Office 365 per i team e configurare le funzionalità di base di teams, le reti e i workload vocali cloud.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 653b5cf46e0b079af47c282b4110b181e76be915
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "37517065"
---
# <a name="prepare-my-service"></a>Preparare il servizio

Questo articolo offre una panoramica dei requisiti per preparare i servizi cloud Voice per l'organizzazione. Preparando in modo corretto, puoi essere sicuro di essere pronto per garantire funzionalità di cloud Voice alla tua organizzazione.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Elenchi di controllo onboarding per i carichi di lavoro vocali di Microsoft Teams

Gli elenchi di controllo seguenti illustrano la procedura per l'implementazione di servizi di audioconferenza, sistema telefonico con piani di chiamata ("piani di chiamata") e funzionalità di routing diretto del sistema telefonico ("Direct routing") in Microsoft teams.

*  [Preparare Office 365 per Teams](onboarding-checklist-enable-office-365.md)

*  [Configurare le funzionalità di base di Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Configurare la rete](onboarding-checklist-configure-networking.md)

*  [Configurare i carichi di lavoro cloud Voice in teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurare il routing diretto in teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Attività e attività in questi elenchi di controllo sono gli elementi principali "da fare" che si applicano a ogni distribuzione di funzionalità di cloud Voice con teams. È possibile personalizzare gli elenchi di controllo per includere le attività e le attività specifiche per il proprio viaggio in teams.

>[!NOTE]
>Questa guida si basa esclusivamente su piani di chiamata, servizi di audioconferenza e routing diretto. Per i nuovi team, vedere [Panoramica di Microsoft teams](teams-overview.md). Per indicazioni generali per la pianificazione della distribuzione dei team, iniziare con l' [implementazione di chat, team, canali e app in Microsoft teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).

Usare gli elenchi di controllo forniti per tenere traccia dello stato di ogni singola attività e attività e per assicurarsi che non siano stati ignorati i passaggi critici. Ogni attività include una descrizione dettagliata delle azioni necessarie e dei riferimenti ad altre informazioni che è possibile usare per completare l'attività.

Anche se ti consigliamo di seguire gli elenchi di controllo in ordine, la sequenza esatta dipenderà dall'ambito della distribuzione e dalla configurazione e dalla complessità dell'ambiente. Sono organizzati per supportare la distribuzione di Team "Greenfield" (uno senza la presenza di Skype for business online precedente) o la migrazione da Skype for business online a teams. Se si sta eseguendo la migrazione da Skype for business online, è possibile che siano già state completate alcune di queste attività e che ora possano ignorarle.

Quando si è a bordo degli utenti in base al sito, è consigliabile usare il [sito di Enablement PlayBook per Voice (PlayBook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) come guida complementare a questi elenchi di controllo.

>[!NOTE]
>La maggior parte delle impostazioni di configurazione è comune tra teams e Skype for business online. Puoi usare l'interfaccia di amministrazione di Microsoft 365 e l'interfaccia di amministrazione di Microsoft teams per configurare queste impostazioni.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Chi avrà il compito di sorvegliare il completamento degli elenchi di controllo onboarding?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Scaricare gli elenchi di controllo onboarding.</li><li>È possibile usare le voci di elenco di controllo onboarding in base al piano di distribuzione dell'organizzazione.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuare a bordo

Dopo aver completato questi elenchi di controllo, le funzionalità vocali verranno aggiunte correttamente alla distribuzione dei team.

Come passaggio successivo, usa il [sito Web Enablement PlayBook per Voice (PlayBook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) per aiutarti a bordo degli utenti in ogni sito e per assicurarti di pianificare ed eseguire importanti attività specifiche del sito.

-   Piano di implementazione sito pronto per sito

-   Creare un processo di gestione dei servizi

-   Eseguire test e correzione

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Testare i carichi di lavoro Voice cloud in teams

Dopo aver definito e documentato i piani per il successo e l'implementazione tecnica del team cloud Voice in fase di previdenza e aver effettuato la configurazione desiderata nell'interfaccia di amministrazione, il passaggio successivo consiste nel verificare che l'organizzazione sia le aspettative e i requisiti vengono soddisfatti tramite funzionalità, funzionalità e usabilità. È consigliabile eseguire questo passaggio di convalida prima di distribuire una distribuzione pilota o finale nell'ambiente di produzione.

È possibile sfruttare il piano di successo aziendale definito durante la fase di previsione per fungere da base per determinare le attività, le aspettative, i casi di prova di funzionalità/funzionalità e l'ambito generale da valutare durante la fase di test.

## <a name="define-your-testing-approach"></a>Definire l'approccio di testing

Nella sua forma più semplice, l'approccio di testing si basa sulla revisione delle funzionalità delle funzionalità di audioconferenza, piani di chiamata o servizio di routing diretto e sviluppo di un piano di test per verificare che i requisiti di funzionalità vengano soddisfatti per gli utenti nell'ambito. Di seguito è riportato un esempio di piano di test per la fase di bordo di un'implementazione di audioconferenza.


| Funzionalità di conferenza audio da testare | Riepilogo dei risultati | Note aggiuntive |
|------------|-----------------|------------------|
| Pianificare una riunione ad hoc per i team che contiene informazioni di accesso esterno per i servizi di audioconferenza | Superato/non superato   | DA definire |
| Usare un telefono per l'audio della riunione componendo una riunione dalla rete PSTN con le informazioni di accesso esterno fornite | Superato/non superato | DA definire |
| Partecipare ad altre persone a una riunione esistente effettuando la chiamata tramite PSTN | Superato/non superato | DA definire |



| Piani di chiamata o funzionalità di routing diretto da testare | Riepilogo dei risultati | Note aggiuntive |
|----------------------------------------------------|-----------------|------------------|
| Effettuare una chiamata PSTN componendo un numero PSTN       | Superato/non superato       | DA definire |
| Ricevere una chiamata PSTN componendo il numero PSTN da una linea esterna (mobile, rete fissa) | Superato/non superato | DA definire|
| Trasferire una chiamata PSTN da un utente di team a un altro | Superato/non superato | DA definire |


>[!TIP]
>Per facilitare la creazione di test case come punto di partenza, vedere l'elenco delle indicazioni per gli utenti disponibili in [riunioni e chiamate di teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurare i carichi di lavoro cloud Voice per i team

Ora che hai definito l'approccio di testing, il passaggio successivo consiste nel configurare l'ambiente di servizio e gli utenti nell'ambito delle funzionalità vocali del cloud teams.

Per altre informazioni, vedere:

- [Pianificazione tecnica per i servizi di audioconferenza](cloud-voice-deployment.md)

- [Configurare servizi di audioconferenza per Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Pianificazione tecnica per il sistema telefonico con piani di chiamata](calling-plan-landing-page.md)

- [Configurare piani per chiamate per Skype for business e Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Pianificare il routing diretto](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [Configurare il routing diretto](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>Eseguire il piano di test

[//]: # (Modifica OK? "Utente" Mi è sembrato un po' ambiguo.)
Dopo aver configurato l'ambiente utente e il servizio, l'ultimo passaggio del test include l'esecuzione del piano di test con lo stato attivo sulla convalida delle caratteristiche e delle funzionalità. 

**Servizi di audioconferenza che testano prerequisiti e presupposti per gli utenti e i siti nell'ambito:**

-   La definizione dei casi di utilizzo aziendale per il servizio di audioconferenza è stata completata.

-   Le licenze necessarie per i servizi di audioconferenza sono disponibili e sono state assegnate.

-   L'elenco dei siti dell'organizzazione e i gruppi di utenti sono stati identificati.

-   L'elenco dei servizi di audioconferenza dedicati e condivisi in numeri con preferenza lingua sono stati identificati e configurati.

-   I crediti per le [comunicazioni](what-are-communications-credits.md) (se necessario) sono stati configurati per l'organizzazione.

-   Sono state identificate e configurate le impostazioni del Bridge conferenza di audioconferenza (lunghezza del PIN, notifiche di entrata/uscita, preferenza di notifica di abilitazione).

-   Sono stati identificati, configurati e applicati i criteri di conferenza tenant e le impostazioni di dial plan che supportano scenari di accesso esterno per i servizi di audioconferenza.

-   I requisiti di conformità dei servizi di audioconferenza sono stati identificati e configurati.

**Piani di chiamata per testare i prerequisiti e i presupposti per gli utenti e i siti nell'ambito:**

-   È stata completata la definizione dei casi di utilizzo aziendale per il servizio piani di chiamata.

-   Le licenze necessarie per i piani di chiamata sono disponibili e sono state assegnate.

-   L'elenco dei siti dell'organizzazione e i gruppi di utenti sono stati identificati.

-   I numeri di telefono da assegnare agli utenti sono stati acquisiti o trasferiti a Microsoft e sono disponibili nel portale del tenant.

-   I crediti per le [comunicazioni](what-are-communications-credits.md) (se necessario) sono stati configurati per l'organizzazione.

-   Criteri per gli utenti del tenant e le impostazioni di dial plan che supportano scenari di piani di chiamata sono stati identificati, configurati e applicati.

-   I requisiti di conformità dei piani di chiamata sono stati identificati e configurati.

**Direct routing testing prerequisiti e presupposti per gli utenti e i siti nell'ambito:**

-   La definizione dei casi di utilizzo aziendale per il servizio di routing diretto è stata completata.

-   Le licenze necessarie per il routing diretto sono disponibili e sono state assegnate.

-   L'elenco dei siti dell'organizzazione e i gruppi di utenti sono stati identificati.

-   Un [SBC (Session Border Controller) certificato](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) è stato distribuito, configurato e associato al sistema telefonico.

-   Enterprise Voice è stata abilitata e i numeri di telefono sono stati assegnati.

-   I criteri di routing vocale sono stati identificati, configurati e assegnati.

-   Microsoft teams è stato impostato come client chiamante preferito per gli utenti nell'ambito.
 
-   I requisiti di conformità del routing diretto sono stati identificati e configurati.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere quali funzionalità di conferenza audio verranno distribuite (decisione del servizio).</li><li>Identificare i requisiti di funzionalità utente per i servizi di audioconferenza.</li><li>Identificare i requisiti di configurazione del servizio per i servizi di audioconferenza.</li><br><li>Decidere se distribuire e configurare piani di routing o chiamate dirette.<li>Decidere quali funzionalità del sistema telefonico verranno distribuite (decisione del servizio).</li><li>Identificare i requisiti di funzionalità utente per i piani di chiamata o il routing diretto.</li><li>Identificare i requisiti di configurazione del servizio per le chiamate o il routing diretto.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Sviluppare e documentare l'approccio del piano di test.</li><li>Preparare l'ambiente di servizio e gli utenti nell'ambito delle funzionalità di conferenza audio.</li><li>Preparare l'ambiente e gli utenti del servizio in ambito per la chiamata di piani o funzionalità di routing diretto.</li><li>Eseguire la convalida dei test per le funzionalità di audioconferenza che si desidera abilitare.</li><li>Eseguire la convalida dei test per i piani di chiamata o le caratteristiche di routing diretto che si desidera abilitare.</li><li>Per qualsiasi errore di test, verificare che la configurazione sia corretta, rivedere gli articoli della community e, se necessario, generare un caso di supporto.</li></ul></td></tr>
</table>


Per altre informazioni dettagliate su come eseguire test per la conferenza audio in teams, vedere la [Guida ai test dettagliati per i servizi di audioconferenza](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).

Per altre indicazioni dettagliate su come eseguire test per la chiamata di piani in teams, vedere la [Guida ai test dettagliati per il sistema telefonico](onboarding-test-plan-for-enterprises-Phone-System.md).

<!--ENDOFSECTION-->
