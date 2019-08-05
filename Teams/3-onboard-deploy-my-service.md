---
title: Distribuire il servizio vocale cloud di Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Scaricare il sito Web Enablement PlayBook per pianificare l'implementazione dei team e accelerare e ottimizzare l'adozione, la percezione della qualità e la soddisfazione degli utenti.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65878cc54973b67a604b08d3579553bca6ca8e4a
ms.sourcegitcommit: ff777b61573b9d90e2d49c49b41fad654eeb3af7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "36184003"
---
# <a name="deploy-my-service"></a>Distribuire il servizio personale

Questo articolo offre una panoramica dei requisiti per la distribuzione corretta di servizi Voice cloud. Seguendo le indicazioni prescrittivi per la distribuzione dei servizi cloud Voice, è possibile verificare che tutti i requisiti vengano convalidati e fornire risultati ripetibili.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>PlayBook per l'abilitazione del sito per i carichi di lavoro vocali di Microsoft Teams

Usa questo PlayBook per aiutare l'organizzazione a pianificare ed eseguire correttamente l'implementazione delle funzionalità vocali di Microsoft teams in base al sito.

Includendo tutte le attività richieste, le sequenze temporali consigliate e i collegamenti alle linee guida corrispondenti per ogni attività, questo PlayBook include le indicazioni finali per garantire una distribuzione vocale di teams di successo per un sito specifico, concentrandosi su fattori importanti per l'utente.

Completando le attività in questo PlayBook, l'organizzazione può:

-   Pianificare e pianificare efficacemente l'implementazione del team.

-   Accelerare e ottimizzare l'adozione degli utenti.

-   Ridurre le esigenze di supporto e aumentare la soddisfazione degli utenti.

> [!NOTE]
> Questo articolo e il PlayBook associato non sono progettati per descrivere ogni passaggio di configurazione tecnica necessario per l'abilitazione del servizio o per fornire un tono di chiamata a un sito specifico. Si occupano invece delle attività e delle attività consigliate per gli utenti a bordo in modo semplice e consentono di iniziare a usare i carichi di lavoro vocali di teams attraverso una transizione veloce e fluida con un tasso di adozione elevato, riducendo al minimo i requisiti di supporto. Per informazioni tecniche su come configurare al meglio l'ambiente per i team Voice, vedere gli elenchi di controllo onboarding per la [configurazione dei workload vocali](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)di teams, [configurazione del routing diretto in teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), funzionalità di base di [Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [Networking per Teams](onboarding-checklist-configure-networking.md)e [Abilitazione di Office 365](onboarding-checklist-enable-office-365.md).

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Aree di interesse di PlayBook

Lo scopo del PlayBook è quello di affrontare i fattori che influenzano la percezione dell'utente di una distribuzione vocale di teams. Le attività e le attività sono raggruppate nelle aree di interesse seguenti:

-   Convalida della disponibilità del servizio
    - Audioconferenza
    - Piani per chiamate
    - Routing diretto

-   Abilitazione dell'utente

-   Endpoint

-   Uso e qualità

-   Adozione

Il [sito Web Enablement PlayBook for Voice (PlayBook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) è una cartella di lavoro di Microsoft Excel. Ognuna di queste cinque aree di interesse è un foglio separato nella cartella di lavoro e ogni attività di distribuzione è raggruppata su uno di questi fogli.

![Screenshot del PlayBook per l'abilitazione del sito] (media/deploy-my-service-image1.png "Screenshot del PlayBook")

> [!NOTE]
> Creerai un'istanza distinta del PlayBook per ogni sito in ambito per l'implementazione del team.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Come usare il PlayBook

Indipendentemente dalle dimensioni e dalla complessità della posizione, l'abilitazione di ogni sito richiede la pianificazione di attività e attività abbastanza presto, nonché l'esecuzione in ordine ottimale, prima, durante e dopo l'implementazione effettiva del servizio. Ti consigliamo di seguire questa procedura mentre pianifichi ed Esegui il tuo viaggio a Microsoft teams Voice.

1. Scaricare il [sito Enablement PlayBook for Voice (PlayBook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) per Microsoft teams Voice.

2. Creare una copia separata del PlayBook per ogni sito.

3. Nella scheda del foglio denominato **PlayBook per {nomesito-codice}** sostituire **{nomesito-codice}** con il nome del sito e/o il codice del sito attinente.

4. Immettere il **nome del sito, il codice del sito**e la **Data di avvio pianificata**, come illustrato di seguito. Questo è un passaggio cruciale, perché regola le scadenze consigliate per ogni attività nel PlayBook.

   ![Esempio con nome sito, codice sito e data di avvio pianificata] (media/deploy-my-service-image2.png "Esempio con il nome del sito di New York, il codice del sito NY01 e la data di avvio prevista del 20-mar-18")

5. Esaminare ogni attività, eseguire le azioni necessarie e aggiornare lo stato man mano che si cammina nella sequenza temporale. Lo stato è rappresentato graficamente, come descritto di seguito:
  
   - ![Illustrazione di un segno](media/deploy-my-service-image3.png) di spunta verde **Sì o non applicabile (verde):** l'attività è stata completata oppure non è applicabile per il sito e non è necessaria alcuna ulteriore azione.</li>
   - ![Illustrazione di un punto](media/deploy-my-service-image4.png) esclamativo giallo <strong>l'attività non è ancora stata completata (giallo):</strong> l'attività non è ancora stata completata e deve essere aggiornata a Sì o no nella programmazione.</li>
   - ![Immagine di una X rossa che indica](media/deploy-my-service-image5.png) No <strong>No (rosso):</strong> l'attività non può essere completata a causa di un problema e deve essere eseguita nella riunione dello stato del progetto.</li></ul>

6. Lo stato viene arrotolato all'interno di ogni sezione e l'intestazione di sezione è formattata con uno di questi indicatori di stato. Anche **lo stato settimanale** viene aggiornato automaticamente.

![Screenshot dei rilevamenti settimanali di stato nel PlayBook] (media/deploy-my-service-image6.png "Screenshot dei rilevamenti settimanali di stato nel PlayBook")

> [!TIP]
> Ripetere i passaggi descritti sopra per tutte le posizioni presenti.

> [!IMPORTANT]
> Alcuni passaggi potrebbero non essere applicabili a tutte le posizioni e i siti. Se un'attività specifica non è pertinente per un sito, è necessario selezionare **non applicabile** per questa attività. Non **eliminare** righe nel PlayBook; in questo caso, le formule per il rollup dello stato non funzionano.<br/><br/>
Prestare attenzione alle attività che potrebbero richiedere più tempo del previsto, ad esempio la portabilità dei numeri e le attività di approvvigionamento. Queste attività possono influire negativamente sulla sequenza temporale di distribuzione del sito. Assicurarsi di rivedere e aggiornare l'elenco attività e la sequenza temporale associata ogni settimana e presentarle alle [riunioni del comitato direttivo](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) per verificare che gli stakeholder siano a conoscenza dello stato di ogni sito e delle eventuali deviazioni dalla pianificazione della distribuzione.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere se il PlayBook per l'attivazione del sito è necessario per la distribuzione.</li><li>Decidere chi sarà responsabile della personalizzazione del sito Web Enablement PlayBook per Microsoft teams per ogni sito che verrà distribuito.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Scaricare il PlayBook per l'abilitazione del sito</a>.</li><li>Personalizzare il PlayBook per l'abilitazione del sito per il primo sito.</li><li>Ripetere le richieste per altri siti.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->