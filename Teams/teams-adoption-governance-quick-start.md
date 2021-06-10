---
title: Guida introduttiva alla governance per Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
localization_priority: Normal
search.appverid: MET150
description: Guida introduttiva che illustra le decisioni chiave da prendere per la fase 2 del piano Microsoft Teams di adozione.
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd54902e00e984de740b7bbf6d0fd96e37e88aa9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424556"
---
# <a name="governance-quick-start-for-microsoft-teams"></a>Guida introduttiva alla governance per Microsoft Teams

Le attività seguenti si verificano contemporaneamente e possono coinvolgere tutto o parte del team chiave. Come procedura consigliata, posticipare le conversazioni di governance e sicurezza su larga scala dopo aver completato la sperimentazione iniziale con Teams. È importante comprendere in che modo le decisioni di governance possono influire sull'esperienza dell'utente finale e semplificare le decisioni da prendere in quella data successiva. Per questa fase è necessario prendere alcune decisioni. Per crearli correttamente, è prima necessario rispondere alle domande seguenti:

- Quale stakeholder della valutazione precedente è un buon candidato per partecipare a questo onboarding aziendale limitato?
- Questo individuo (o gruppo di persone) ha suggerito casi d'uso che potrebbero essere buoni candidati per questa fase?  
- Hanno abbastanza interesse da parte dei dipendenti dell'organizzazione per essere presto adottatori e fornire feedback significativi e regolari? 

Per altre informazioni, vedere [Pianificare la governance in Teams](plan-teams-governance.md) e Pianificare la gestione del ciclo di vita in [Teams](plan-teams-lifecycle.md).

## <a name="an-icon-representing-a-decision-pointdecisions"></a>![Icona che rappresenta un punto decisionale](media/teams-adoption-decision-icon.png)Decisioni

Prendere le decisioni seguenti (a questo punto queste decisioni si applicano solo alla fase 2):

### <a name="decision-1-who-can-create-teams"></a>Decisione 1: Who creare team 

Ai fini di questa fase è possibile limitare chi è in grado di creare team alla popolazione di utenti che adottano in anticipo oltre al team di progetto principale. In questo modo i primi utenti potranno creare altri team, se necessario. Il monitoraggio di questo comportamento consente di ottenere informazioni chiave per la distribuzione generale.

### <a name="decision-2-teams-naming-conventions"></a>Decisione 2: Teams di denominazione 

È probabile che si voglia implementare alcune convenzioni di denominazione per l'ampia distribuzione di Teams e verificare la presenza di nomi duplicati. Nella fase 2 è consigliabile implementare una convenzione di denominazione manuale solo per i progetti iniziali. La procedura consigliata consiste nell'eseguire un onboarding interattivo con il team di progetto che lo ha adottato in anticipo e consentire loro di selezionare il proprio nome. In questo modo si avranno informazioni approfondite sul modo in cui i dipendenti pensano al loro lavoro e saranno essenziali per creare una convenzione di denominazione su scala più ampia in un secondo momento. Altre informazioni sugli elementi di un onboarding interattivo verranno visualizzate più avanti in questa guida.

### <a name="decision-3-guest-access"></a>Decisione 3: Accesso guest

A seconda dell'ambito e del tipo di progetto e della natura del settore, l'abilitazione di una collaborazione sicura con partner o fornitori può essere una funzionalità essenziale da testare. È possibile limitare gli utenti che possono aggiungere guest ai team usando i controlli tenant appropriati e limitare i team aperti agli utenti guest usando le etichette di riservatezza. È inoltre possibile assicurarsi che i guest rispettino i requisiti di sicurezza dell'organizzazione, ad esempio l'uso di Multi-Factor Authentication (MFA).

### <a name="decision-4-approved-apps"></a>Decisione 4: App approvate

L'uso ottimale dei Teams include l'integrazione di altre app nell'esperienza. Come minimo, il team tecnico dovrebbe abilitare le app di prima parte e in primo piano nell'esperienza Teams lavoro. A seconda del caso d'uso e di altre app usate nell'organizzazione, è possibile scegliere di includere altre app nell'ambito dell'esperimento controllato. Assicurarsi di controllare eventuali app di terze parti per assicurarsi che rispettino i requisiti di sicurezza e conformità dell'organizzazione.

### <a name="decision-5-are-meetings-included-in-your-test"></a>Decisione 5: Le riunioni sono incluse nel test? 

L Teams di riunione è di alta qualità, supporta la video chat e riunisce i dipendenti per essere più efficaci. Consultare il team tecnico per assicurarsi che l'ambiente sia pronto per includere riunioni VoIP semplici. L'abilitazione di servizi di audioconferenza o voce verrebbe in genere esclusa da questa fase della sperimentazione. Tuttavia, dipende dal team di progetto principale, dalla conformità tecnica e dallo stato di altri servizi vocali/riunioni dell'organizzazione. La preparazione tecnica deve includere elementi come l'attrezzatura della sala riunioni, i dispositivi e gli accessori per l'utente finale e la rete. Ti consigliamo di includere video chat e riunioni VoIP nella tua sperimentazione per ottenere più valore dalla tua Teams implementazione. 

### <a name="decision-6-content-management-and-structure"></a>Decisione 6: Gestione e struttura dei contenuti
Teams funziona al meglio quando gli utenti lavorano end-to-end all'interno della piattaforma, invece di richiedere loro di tornare continuamente ai sistemi e ai servizi legacy, e offre nuovi modi di lavorare diversi da come sono abituati gli utenti. Nell'ambito dell'esperimento, collaborare con i partecipanti per prendere in considerazione le strutture del team e i canali che adottano le modalità multimodali di collaborazione all'interno di Teams ed evitare semplicemente di replicare le strutture di cartelle e di archiviazione esistenti. Considerare inoltre eventuali requisiti di conformità per il contenuto archiviato all'esterno dei sistemi supportati esistenti, ad esempio i sistemi di gestione dei record o di backup.

### <a name="decision-7--data-security"></a>Decisione 7: Sicurezza dei dati

In preparazione per l'ampia distribuzione, è possibile scegliere di usare etichette di sicurezza per classificare i tipi di team nell'ambiente. Ai fini di questo esperimento, è consigliabile fare riferimento a Pianificare la governance [in Teams](plan-teams-governance.md) e verificare che siano stati impostati criteri di conservazione di base sui dati Teams nel Microsoft 365. Potrebbe essere necessario coordinare il lavoro con il team tecnico perché Microsoft 365 diritti di amministratore per completare il lavoro.

### <a name="decision-8-length-of-your-experiment"></a>Decisione 8: Durata dell'esperimento

Una riuscita Teams'implementazione procede a un ritmo sano per garantire un'adeguata quantità di energia, concentrazione e apprendimento. È consigliabile che questa fase del progetto sia lunga 60 giorni per assicurarsi che i primi adottivi completino cicli aziendali sufficienti. L'estensione della sperimentazione per un periodo di tempo troppo lungo aumenta il rischio di un programma di modifica non riuscito. tuttavia, questa volta varia per ogni organizzazione.  

![Icona che rappresenta il passaggio successivo ](media/teams-adoption-next-icon.png) Successivo: [Definire gli scenari di utilizzo](teams-adoption-define-usage-scenarios.md)
