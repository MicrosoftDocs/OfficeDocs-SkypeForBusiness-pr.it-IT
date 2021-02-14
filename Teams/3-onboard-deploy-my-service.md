---
title: Distribuire il servizio vocale cloud di Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Scarica Playbook per l'abilitazione del sito per pianificare l'implementazione di Teams e accelerare e ottimizzare l'adozione da parte degli utenti, la soddisfazione e la qualità.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae9a1e6abf7dbf97e625be4eb69a0ef95b1910da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532573"
---
# <a name="deploy-my-service"></a>Implementare il servizio

Questo articolo offre una panoramica dei requisiti per la corretta distribuzione dei servizi vocali cloud. Seguendo le indicazioni prescriptive per la distribuzione dei servizi vocali cloud, è possibile assicurarsi di soddisfare tutti i requisiti e fornire risultati ripetibili.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Playbook di abilitazione del sito per i carichi di lavoro vocali di Microsoft Teams

Usare questo playbook per aiutare l'organizzazione a pianificare ed eseguire correttamente l'implementazione delle funzionalità vocali di Microsoft Teams su base sito.

Incluse tutte le attività richieste, le sequenze temporali consigliate e i collegamenti alle indicazioni corrispondenti per ogni attività, questo playbook illustra le linee guida end-to-end per assicurare una distribuzione vocale di Teams corretta per un determinato sito, concentrandosi sui fattori importanti per l'utente.

Completando le attività in questo playbook, l'organizzazione può:

-   Pianificare e pianificare in modo efficace l'implementazione di Teams.

-   Accelerare e ottimizzare l'adozione da parte degli utenti.

-   Ridurre le esigenze di supporto e aumentare la soddisfazione degli utenti.

> [!NOTE]
> Questo articolo e il playbook associato non hanno lo scopo di descrivere ogni passaggio di configurazione tecnica necessario per l'abilitazione del servizio o l'impostazione del tono di chiamata a un sito specifico. Si focalizzano invece sulle attività e sulle attività consigliate agli utenti di onboarding con facilità e devono iniziare a consumare i carichi di lavoro vocali di Teams attraverso una transizione veloce e fluida con un tasso di adozione elevato, riducendo al minimo i requisiti di supporto. Per indicazioni tecniche su come configurare al meglio l'ambiente per la voce di Teams, vedere gli elenchi di controllo di onboarding per la configurazione dei carichi di lavoro vocali di [Teams,](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)la configurazione del routing diretto [in Teams,](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)le funzionalità principali di [Teams,](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)la rete per [Teams](prepare-network.md)e l'abilitazione di [Microsoft 365 o Office 365.](onboarding-checklist-enable-office-365.md)

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Aree di interesse di Playbook

L'obiettivo del playbook è risolvere i fattori che influenzano la distribuzione vocale di Teams da parte dell'utente. Le attività e le attività sono raggruppate nelle aree di interesse seguenti:

-   Convalida della conformità dei servizi
    - Audioconferenza
    - Piani di chiamata
    - Routing diretto

-   Abilitazione degli utenti

-   Endpoint

-   Utilizzo e qualità

-   Adozione

Playbook [for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) per l'abilitazione del sito è una cartella di lavoro di Microsoft Excel. Ognuna di queste cinque aree di interesse è un foglio distinto nella cartella di lavoro e ogni attività e attività di distribuzione è raggruppata in uno di questi fogli.

![Screenshot del playbook di abilitazione del sito](media/deploy-my-service-image1.png "Screenshot del playbook")

> [!NOTE]
> Verrà creata un'istanza distinta del playbook per ogni sito nell'ambito per l'implementazione di Teams.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Come usare il playbook

Indipendentemente dalle dimensioni e dalla complessità della posizione, l'abilitazione di ogni sito richiede di pianificare le attività e le attività in anticipo, ed eseguirle in ordine ottimale, prima, durante e dopo l'implementazione effettiva del servizio. È consigliabile seguire questi passaggi durante la pianificazione e l'esecuzione del percorso verso la voce di Microsoft Teams.

1. Scaricare [playbook di abilitazione del sito per la voce (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) per Microsoft Teams Voice.

2. Creare una copia separata del playbook per ogni sito.

3. Nella scheda del foglio denominato Playbook per **{SiteName-Code}** sostituire **{SiteName-Code}** con il nome del sito e/o il codice del sito pertinente.

4. Immettere il **nome del sito, il codice del sito** e la data di lancio **pianificata,** come illustrato di seguito. Si tratta di un passaggio fondamentale, perché modifica le scadenze consigliate per ogni attività nel playbook.

   ![Esempio con il nome del sito, il codice del sito e la data di lancio pianificata](media/deploy-my-service-image2.png "Esempio con il nome del sito di New York, il codice del sito NY01 e la data di lancio pianificata del 20 marzo 18")

5. Esaminare le attività, eseguire le azioni necessarie e aggiornare lo stato mentre si esamina la sequenza temporale. Lo stato viene rappresentato graficamente, come descritto di seguito:
  
   - ![Illustrazione di un segno di spunta verde Sì o non applicabile ](media/deploy-my-service-image3.png) **(verde):** l'attività è stata completata o non è applicabile per questo sito e non sono necessarie altre azioni.</li>
   - ![Illustrazione di un punto esclamativo giallo L'attività non è stata ancora completata ](media/deploy-my-service-image4.png) <strong>(gialla): l'attività</strong> non è stata ancora completata e deve essere aggiornata in Sì o No nella relativa pianificazione.</li>
   - ![Illustrazione di una X rossa che indica no ](media/deploy-my-service-image5.png) <strong>(rosso):</strong> l'attività non può essere completata a causa di un problema e deve essere riportata nella riunione sullo stato del progetto.</li></ul>

6. Lo stato viene visualizzato all'interno di ogni sezione e l'intestazione della sezione è formattata con uno di questi indicatori di stato. **Anche lo stato** settimanale viene aggiornato automaticamente.

![Screenshot dei rieliminazioni settimanali dello stato nel playbook](media/deploy-my-service-image6.png "Screenshot dei rieliminazioni settimanali dello stato nel playbook")

> [!TIP]
> Ripetere i passaggi precedenti per tutte le posizioni disponibili.

> [!IMPORTANT]
> Alcuni passaggi potrebbero non essere applicabili a tutti i siti e posizioni. Se un'attività specifica non è pertinente per un sito, è necessario selezionare **Non applicabile** per questa attività. **NON ELIMINARE righe** nel playbook; in caso contrario, le formule di rollup dello stato non funzionano.<br/><br/>
Prestare attenzione alle attività che potrebbero richiedere più tempo di quanto previsto, ad esempio le attività di portabilità e approvvigionamento del numero. Queste attività possono influire negativamente sulla sequenza temporale della distribuzione del sito. Rivedere e aggiornare l'elenco attività e la sequenza temporale [](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) associata ogni settimana e presentarli durante le riunioni del comitato per assicurarsi che gli stakeholder siano a conoscenza dello stato di ogni sito e di eventuali deviazioni dalla pianificazione della distribuzione.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere se è necessario playbook per l'abilitazione del sito per la distribuzione.</li><li>Decidere chi sarà responsabile della personalizzazione del playbook di abilitazione del sito per Microsoft Teams per ogni sito da distribuire.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Scaricare playbook per l'abilitazione del sito.</a></li><li>Personalizzare il playbook di abilitazione del sito per il primo sito.</li><li>Ripetere l'operazione in base alle esigenze per altri siti.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->