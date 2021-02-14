---
title: Prepararsi a distribuire il servizio Cloud Voice
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Usare elenchi di controllo di onboarding per preparare Microsoft 365 o Office 365 per Teams e configurare le funzionalità principali, la rete e i carichi di lavoro vocali cloud di Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3c805e8ff14ddb1c46f83db819c5dd8a2c305914
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610068"
---
# <a name="prepare-my-service"></a>Preparare il servizio

Questo articolo fornisce una panoramica dei requisiti per la preparazione dei servizi vocali cloud per l'organizzazione. Una corretta preparazione consente di essere certi di essere pronti a fornire funzionalità vocali sul cloud all'organizzazione.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Elenchi di controllo di onboarding per i carichi di lavoro vocali di Microsoft Teams

I seguenti elenchi di controllo illustrano i passaggi per l'implementazione delle funzionalità Audioconferenza, Sistema telefonico con Piani per chiamate ("Piani per chiamate" e Routing diretto del sistema telefonico ("Routing diretto") in Microsoft Teams.

*  [Preparare Microsoft 365 o Office 365 per Teams](onboarding-checklist-enable-office-365.md)

*  [Configurare le funzionalità principali di Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Preparare la rete](prepare-network.md)

*  [Configurare i carichi di lavoro vocali cloud in Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Configurare il routing diretto in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Le attività e le attività in questi elenchi di controllo sono le principali "attività" che si applicano a tutte le distribuzioni di funzionalità vocali cloud con Teams. È possibile personalizzare gli elenchi di controllo per includere le attività e le attività specifiche per il proprio percorso in Teams.

>[!NOTE]
>Questa guida è incentrata esclusivamente sui piani per chiamate, le audioconferenze e l'instradamento diretto. Se non si ha di nuovo Teams, vedere [Panoramica di Microsoft Teams.](teams-overview.md) Per indicazioni generali sulla pianificazione della distribuzione di Teams, inizia [con Distribuisci chat, team, canali e app in Microsoft Teams.](deploy-chat-teams-channels-microsoft-teams-landing-page.md)

Usare gli elenchi di controllo disponibili per tenere traccia dello stato di ogni singola attività e attività e per essere certi di non aver ignorato i passaggi critici. Ogni attività include una descrizione dettagliata delle azioni obbligatorie e riferimenti a informazioni aggiuntive che è possibile usare per completare l'attività.

Anche se è consigliabile seguire gli elenchi di controllo in ordine, la sequenza esatta dipenderà dall'ambito della distribuzione e dalla configurazione e dalla complessità dell'ambiente. Sono organizzati per supportare una distribuzione di Teams "greenfield" (una senza presenza precedente in Skype for Business Online) o per la migrazione da Skype for Business Online a Teams. Se stai eseguendo la migrazione da Skype for Business online, alcune di queste attività potrebbero essere già state completate e ignorarle ora.

Quando si esegue l'onboarding di utenti per sito, è consigliabile usare Playbook per l'abilitazione del sito per voce [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) come guida supplementare a questi elenchi di controllo.

>[!NOTE]
>La maggior parte delle impostazioni di configurazione sono comuni tra Teams e Skype for Business online. Usare l'interfaccia di amministrazione di Microsoft 365 e l'interfaccia di amministrazione di Microsoft Teams per configurare queste impostazioni.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Chi sarà responsabile della supervisione del completamento degli elenchi di controllo di onboarding?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Scaricare gli elenchi di controllo per l'onboarding.</li><li>Eseguire i passaggi dettagliati delle voci dell'elenco di controllo di onboarding in base al piano di distribuzione dell'organizzazione.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Continuare l'onboarding

Dopo aver completato questi elenchi di controllo, le funzionalità vocali saranno state aggiunte correttamente alla distribuzione di Teams.

Come passaggio successivo, usare Playbook per l'abilitazione del sito per voce [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) per eseguire l'onboarding degli utenti su ogni sito e assicurarsi di pianificare ed eseguire importanti attività specifiche del sito.

-   Ready Site by Site Rollout Plan

-   Definizione del processo di gestione dei servizi

-   Eseguire test e correzioni

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Testare i carichi di lavoro vocali cloud in Teams

Dopo aver definito e documentato i piani di successo e implementazione tecnica del cloud voice business di Teams nell'ambito della fase di sviluppo e aver intrapreso la configurazione desiderata nell'interfaccia di amministrazione, il passaggio successivo consiste nel verificare che le aspettative e i requisiti dell'organizzazione siano soddisfatti attraverso funzionalità, funzionalità e usabilità. Questo passaggio di convalida deve essere eseguito prima di distribuire una distribuzione pilota o finale nell'ambiente di produzione.

È possibile sfruttare il piano di successo aziendale definito durante la fase di previsione come base per determinare le attività, le aspettative, i test case di caratteristiche/funzionalità e l'ambito complessivo da valutare durante la fase di test.

## <a name="define-your-testing-approach"></a>Definire l'approccio di test

Nella sua forma più semplice, l'approccio di test si basa sul riesame delle funzionalità del servizio Audioconferenza, Piani per chiamate o Instradamento diretto e sullo sviluppo di un piano di test per verificare che i requisiti di funzionalità siano soddisfatti per gli utenti con ambito di validità. Di seguito è riportato un esempio di piano di test per la fase di onboardmento di un'implementazione di audioconferenza.


| Funzionalità di audioconferenza da testare | Riepilogo risultati | Note aggiuntive |
|------------|-----------------|------------------|
| Pianificare una riunione di Teams ad-hoc contenente informazioni per l'accesso esterno per i servizi di audioconferenza | Superato/Non superato   | TBD |
| Usare un telefono per l'audio della riunione componendo il numero di telefono di una riunione dalla rete PSTN, con le informazioni di accesso fornite | Superato/Non superato | TBD |
| Partecipare ad altre persone a una riunione esistente tramite chiamata in uscita tramite PSTN | Superato/Non superato | TBD |



| Funzionalità Piani per chiamate o Instradamento diretto da testare | Riepilogo risultati | Note aggiuntive |
|----------------------------------------------------|-----------------|------------------|
| Effettuare una chiamata PSTN componendo un numero PSTN       | Superato/Non superato       | TBD |
| Ricevere una chiamata PSTN componendo il numero PSTN da una linea esterna (cellulare, telefono fisso) | Superato/Non superato | TBD|
| Trasferire una chiamata PSTN da un utente di Teams a un altro | Superato/Non superato | TBD |


>[!TIP]
>Per agevolare la creazione di casi di test come punto di partenza, vedere l'elenco delle indicazioni utente disponibili in Riunioni [e chiamate di Teams.](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Configurare i carichi di lavoro vocali cloud per Teams

Una volta definito l'approccio di test, il passaggio successivo consiste nel configurare l'ambiente del servizio e gli utenti nell'ambito per le funzionalità vocali cloud di Teams.

Per altre informazioni, vedere:

- [Pianificazione tecnica per le audioconferenze](cloud-voice-deployment.md)

- [Configurare Audioconferenza per Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Pianificazione tecnica per sistema telefonico con piani per chiamate](calling-plan-landing-page.md)

- [Configurare piani per chiamate per Skype for Business e Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Pianificare Instradamento diretto](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [Configurare Instradamento diretto](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>Eseguire il piano di test

[//]: # (Modificare l'opzione? "Utente" sembrava un po' ambiguo per me.)
Dopo aver configurato l'ambiente utente e il servizio, l'ultimo passaggio di test include l'esecuzione del piano di test, con lo stato attivo sulla convalida di caratteristiche e funzionalità. 

**Prerequisiti e presupposti per il test delle audioconferenze per gli utenti e i siti nell'ambito:**

-   La definizione del caso di utilizzo aziendale per il servizio di audioconferenza è stata completata.

-   Le licenze necessarie per i servizi di audioconferenza sono disponibili e sono state assegnate.

-   È stato identificato l'elenco di siti e gruppi di utenti dell'organizzazione.

-   È stato identificato e configurato l'elenco dei numeri telefonici di accesso esterno per i servizi di audioconferenza dedicati e condivisi con preferenze di lingua.

-   [I Crediti comunicazioni](what-are-communications-credits.md) (se necessario) sono stati impostati per la tua organizzazione.

-   Le impostazioni bridge di conferenza audioconferenza sono state identificate e configurate (lunghezza DEL PIN, notifiche di accesso/uscita, preferenza di notifica di abilitazione).

-   I criteri di conferenza tenant e le impostazioni del piano di chiamata che supportano gli scenari di chiamata in uscita per i servizi di audioconferenza sono stati identificati, configurati e applicati.

-   I requisiti di conformità delle audioconferenze sono stati identificati e configurati.

**Prerequisiti e presupposti per gli utenti e i siti nell'ambito dei Piani per chiamate:**

-   La definizione del caso d'uso aziendale per il servizio Piani per chiamate è stata completata.

-   Le licenze necessarie per i Piani per chiamate sono disponibili e sono state assegnate.

-   È stato identificato l'elenco di siti e gruppi di utenti dell'organizzazione.

-   I numeri di telefono da assegnare agli utenti sono stati acquisiti o esportati su Microsoft e sono disponibili nel portale tenant.

-   [I Crediti comunicazioni](what-are-communications-credits.md) (se necessario) sono stati impostati per la tua organizzazione.

-   I criteri utente tenant e le impostazioni del piano di chiamata che supportano gli scenari di piani di chiamata sono stati identificati, configurati e applicati.

-   I requisiti di conformità dei Piani per chiamate sono stati identificati e configurati.

**Prerequisiti e presupposti per il test del routing diretto per gli utenti e i siti nell'ambito:**

-   La definizione del caso di utilizzo aziendale per il servizio di instradamento diretto è stata completata.

-   Le licenze necessarie per l'instradamento diretto sono disponibili e sono state assegnate.

-   È stato identificato l'elenco di siti e gruppi di utenti dell'organizzazione.

-   Un [controller di bordo della sessione certificato (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) è stato distribuito, configurato e associato al Sistema telefonico.

-   Il VoIP aziendale è stato abilitato e i numeri di telefono sono stati assegnati.

-   I criteri di routing vocale sono stati identificati, configurati e assegnati.

-   Microsoft Teams è stato impostato come client di chiamata preferito per gli utenti nell'ambito.
 
-   I requisiti di conformità per il routing diretto sono stati identificati e configurati.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere quali funzionalità di audioconferenza verranno distribuite (decisione sul servizio).</li><li>Identificare i requisiti di funzionalità utente per le audioconferenze.</li><li>Identificare i requisiti di configurazione del servizio per le audioconferenze.</li><br><li>Decidere se verrà distribuito e configurato l'instradamento diretto o i piani per chiamate.<li>Decidere quali funzionalità del Sistema telefonico verranno distribuite (decisione sul servizio).</li><li>Identificare i requisiti di funzionalità utente per i Piani per chiamate o l'instradamento diretto.</li><li>Identificare i requisiti di configurazione del servizio per piani per chiamate o instradamento diretto.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Sviluppare e documentare l'approccio del piano di test.</li><li>Preparare l'ambiente del servizio e gli utenti nell'ambito per le caratteristiche di audioconferenza.</li><li>Preparare l'ambiente del servizio e gli utenti nell'ambito per le funzionalità Piani per chiamate o Instradamento diretto.</li><li>Eseguire la convalida del test per le funzionalità di audioconferenza da abilitare.</li><li>Eseguire la convalida del test per le funzionalità Piani per chiamate o Instradamento diretto da abilitare.</li><li>Per gli eventuali errori di test, verificare che la configurazione sia corretta, leggere gli articoli della community e, se necessario, sollevare un caso di supporto.</li></ul></td></tr>
</table>


Per ulteriori istruzioni dettagliate su come eseguire i test per le audioconferenze in Teams, consulta la guida [di test dettagliata per i servizi di audioconferenza.](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)

Per ulteriori istruzioni dettagliate su come eseguire i test per i Piani per chiamate in Teams, consulta la guida [dettagliata di test per sistema telefonico.](onboarding-test-plan-for-enterprises-Phone-System.md)

<!--ENDOFSECTION-->
