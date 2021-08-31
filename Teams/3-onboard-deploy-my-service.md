---
title: Distribuire Microsoft Teams cloud voice
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
description: Scarica il Playbook di abilitazione del sito per pianificare l'implementazione Teams e accelerare e ottimizzare l'adozione degli utenti, la percezione della qualità e la soddisfazione.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b5c027da20c6c305fd5924cd6483c5cbd63b8ddd
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733541"
---
# <a name="deploy-my-service"></a>Implementare il servizio

Questo articolo fornisce una panoramica dei requisiti per distribuire correttamente i servizi vocali cloud. Seguendo indicazioni prescrittive per la distribuzione di servizi vocali cloud, è possibile verificare di aver eseguito correttamente l'account per tutti i requisiti e di fornire risultati ripetibili.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Playbook di abilitazione del sito per Microsoft Teams di lavoro vocali

Usare questo playbook per aiutare l'organizzazione a pianificare ed eseguire correttamente l'implementazione delle Microsoft Teams vocali su base sito per sito.

Includendo tutte le attività necessarie, le sequenze temporali consigliate e i collegamenti alle indicazioni corrispondenti per ogni attività, questo playbook illustra le linee guida end-to-end per garantire una distribuzione vocale Teams riuscita per un determinato sito, concentrandosi sui fattori importanti per l'utente.

Completando le attività in questo playbook, l'organizzazione può:

-   Pianificare e pianificare in modo efficace l Teams'implementazione.

-   Accelerare e ottimizzare l'adozione degli utenti.

-   Ridurre le esigenze di supporto e aumentare la soddisfazione degli utenti.

> [!NOTE]
> Questo articolo e il playbook associato non sono destinati a descrivere ogni passaggio di configurazione tecnica necessario per l'abilitazione del servizio o per fornire il segnale di chiamata a un sito specifico. Si concentrano invece sulle attività e sulle attività consigliate agli utenti con facilità e li fanno iniziare Teams consumare carichi di lavoro vocali Teams attraverso una transizione veloce e fluida con un tasso di adozione elevato, riducendo al minimo i requisiti di supporto. Per indicazioni tecniche su come configurare al meglio l'ambiente per la voce di [Teams,](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)vedere gli elenchi di controllo di onboarding per la configurazione dei carichi di lavoro vocali di [Teams,](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)la configurazione del routing diretto [in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), le funzionalità di base di Teams , la rete per [Teams](prepare-network.md)e l'abilitazione di [Microsoft 365 o Office 365](onboarding-checklist-enable-office-365.md).

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Aree di stato attivo del playbook

Lo stato attivo del playbook è quello di affrontare i fattori che influenzano la percezione dell'utente di una distribuzione Teams vocale. Le attività e le attività sono raggruppate nelle aree di interesse seguenti:

-   Convalida della conformità del servizio
    - Audioconferenza
    - Piani di chiamata
    - Routing diretto

-   Abilitazione dell'utente

-   Endpoint

-   Utilizzo e qualità

-   Adozione

Il Playbook di abilitazione del sito per la voce [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) è una Microsoft Excel cartella di lavoro. Ognuna di queste cinque aree dello stato attivo è un foglio separato nella cartella di lavoro e ogni attività e attività di distribuzione è raggruppata in uno di questi fogli.

![Screenshot del playbook di abilitazione del sito.](media/deploy-my-service-image1.png "Screenshot del playbook")

> [!NOTE]
> Si creerà un'istanza separata del playbook per ogni sito nell'ambito dell'Teams dell'applicazione.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Come usare il playbook

Indipendentemente dalle dimensioni e dalla complessità della posizione, l'abilitazione di ogni sito richiede di pianificare le attività e le attività in anticipo e di eseguirle in ordine ottimale, prima, durante e dopo l'implementazione effettiva del servizio. È consigliabile seguire questa procedura durante la pianificazione e l'esecuzione del proprio percorso verso Microsoft Teams vocale.

1. Scarica il Playbook di abilitazione del sito per la voce [(Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) per Microsoft Teams Voce.

2. Creare una copia separata del playbook per ogni sito.

3. Nella scheda del foglio denominato **Playbook per {SiteName-Code}** sostituire **{SiteName-Code}** con il nome del sito e/o il codice del sito pertinente.

4. Immettere il **nome del sito, il codice del** sito e la data di avvio **pianificata,** come illustrato di seguito. Si tratta di un passaggio fondamentale, perché modifica le scadenze consigliate per ogni attività nel playbook.

   ![Esempio con il nome del sito, il codice del sito e la data di avvio pianificata.](media/deploy-my-service-image2.png "Esempio con il nome del sito di New York, il codice del sito NY01 e la data di lancio pianificata del 20 marzo 18")

5. Esaminare ogni attività, eseguire le azioni necessarie e aggiornare lo stato mentre si attraversa la sequenza temporale. Lo stato è rappresentato graficamente, come descritto di seguito:
  
   - ![Illustrazione di un segno di spunta verde.](media/deploy-my-service-image3.png) **Sì o non applicabile (verde):** L'attività è stata completata o non è applicabile per questo sito e non sono necessarie altre azioni.</li>
   - ![Illustrazione di un punto esclamativo giallo.](media/deploy-my-service-image4.png) <strong>L'attività non è ancora completata (giallo):</strong> L'attività non è ancora stata completata e deve essere aggiornata a Sì o No nella pianificazione.</li>
   - ![Illustrazione di una X rossa che indica no.](media/deploy-my-service-image5.png) <strong>No (rosso):</strong> L'attività non può essere completata a causa di un problema e deve essere portata alla riunione sullo stato del progetto.</li></ul>

6. Lo stato viene visualizzato all'interno di ogni sezione e l'intestazione della sezione è formattata con uno di questi indicatori di stato. **Anche lo stato settimanale** viene aggiornato automaticamente.

![Screenshot dei roll-up settimanali dello stato nel playbook.](media/deploy-my-service-image6.png "Screenshot dei roll-up settimanali dello stato nel playbook")

> [!TIP]
> Ripetere i passaggi precedenti per tutte le posizioni disponibili.

> [!IMPORTANT]
> Alcuni passaggi potrebbero non essere applicabili a tutti i percorsi e i siti. Se un'attività specifica non è pertinente per un sito, è necessario selezionare **Non applicabile** per questa attività. **DO NOT DELETE** any rows in the playbook; in questo caso, le formule di rollup dello stato non funzionano.<br/><br/>
Prestare attenzione alle attività che potrebbero richiedere più tempo del previsto, ad esempio le attività di porting dei numeri e di approvvigionamento. Queste attività possono influire negativamente sulla sequenza temporale di distribuzione del sito. Assicurarsi di rivedere e aggiornare l'elenco attività e la [](./envision-steering-committee-complete-guide.md) sequenza temporale associata settimanalmente e presentarli alle riunioni del comitato direttivo per assicurarsi che gli stakeholder siano a conoscenza dello stato di ogni sito e di eventuali deviazioni dalla pianificazione della distribuzione.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere se il Playbook di abilitazione del sito è necessario per la distribuzione.</li><li>Decidere chi sarà responsabile della personalizzazione del Playbook di abilitazione del sito per Microsoft Teams per ogni sito da distribuire.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Scaricare il Playbook di abilitazione del sito</a>.</li><li>Personalizzare il Playbook di abilitazione del sito per il primo sito.</li><li>Ripetere l'operazione in base alle esigenze per altri siti.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->