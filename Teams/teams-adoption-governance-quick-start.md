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
description: Guida introduttiva che illustra le decisioni chiave da prendere per la fase 2 del piano di adozione di Microsoft Teams.
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

Le attività seguenti si verificano contemporaneamente e possono coinvolgere tutto o parte del team principale. Come procedura consigliata, rimandare le conversazioni di governance e sicurezza su larga scala per una volta completata la sperimentazione iniziale con Teams. È importante comprendere in che modo le decisioni di governance possono influire sull'esperienza degli utenti finali e semplificare le decisioni che sarà necessario prendere successivamente. Per questa fase è necessario prendere alcune decisioni. Per completare correttamente questa operazione, è necessario prima di tutto rispondere alle domande seguenti:

- Quale stakeholder della valutazione precedente può essere un buon candidato per partecipare a questo onboarding aziendale limitato?
- Questo singolo o gruppo di singoli utenti ha suggerito casi d'uso che potrebbero essere ottimi candidati per questa fase?  
- Hanno un interesse sufficiente da parte dei dipendenti dell'organizzazione per essere early adopter e fornire un feedback significativo e regolare? 

Per altre informazioni, vedere [Pianificare la governance in Teams](plan-teams-governance.md) e Pianificare la gestione del ciclo di vita in [Teams.](plan-teams-lifecycle.md)

## <a name="an-icon-representing-a-decision-pointdecisions"></a>![Icona che rappresenta un punto decisionale](media/teams-adoption-decision-icon.png)Decisioni

Prendere le decisioni seguenti (a questo punto queste decisioni si applicano solo alla fase 2):

### <a name="decision-1-who-can-create-teams"></a>Decisione 1: Chi può creare team 

Ai fini di questa fase è possibile limitare gli utenti che possono creare team alla popolazione early adopter oltre al team di progetto principale. In questo modo i primi utenti potranno creare altri team, se necessario. Il monitoraggio di questo comportamento offrirà informazioni chiave per l'ampia distribuzione.

### <a name="decision-2-teams-naming-conventions"></a>Decisione 2: Convenzioni di denominazione dei team 

È probabile che sia necessario implementare alcune convenzioni di denominazione per l'ampia distribuzione di Teams e verificare la presenza di nomi duplicati. Nella fase 2 è consigliabile implementare una convenzione di denominazione manuale solo per i progetti iniziali. La procedura consigliata consiste nel condurre un onboarding interattivo con il team di progetto early adopter e consentire loro di selezionare il proprio nome. In questo modo si avranno informazioni approfondite sul modo in cui i dipendenti pensano al loro lavoro e sarà essenziale per creare una convenzione di denominazione su più vasta scala in un secondo momento. Altre informazioni sugli elementi di un onboarding interattivo verranno visualizzate più avanti in questa guida.

### <a name="decision-3-guest-access"></a>Decisione 3: Accesso guest

A seconda dell'ambito e del tipo di progetto e della natura del settore, consentire una collaborazione sicura con partner o fornitori può essere una funzionalità essenziale da testare. È possibile limitare gli utenti che possono aggiungere guest ai team usando i controlli tenant appropriati e limitare i team aperti ai guest usando etichette di riservatezza. È inoltre possibile assicurarsi che i guest rispettino i requisiti di sicurezza dell'organizzazione, ad esempio l'uso di Autenticazione a più fattori (MFA).

### <a name="decision-4-approved-apps"></a>Decisione 4: App approvate

Il caso migliore di utilizzo di Teams include l'integrazione di altre app nell'esperienza. È necessario che il team tecnico abiliti almeno le app della prima parte e in primo piano nell'esperienza di Teams. A seconda del caso di utilizzo e di altre app usate nell'organizzazione, è possibile scegliere di includere altre app nell'ambito di un esperimento controllato. Controllare eventuali app di terze parti per assicurarsi che rispettino i requisiti di sicurezza e conformità dell'organizzazione.

### <a name="decision-5-are-meetings-included-in-your-test"></a>Decisione 5: Le riunioni sono incluse nel test? 

L'esperienza della riunione di Teams è di alta qualità, supporta la video chat e riunisce i dipendenti per essere più efficaci. Rivolgersi al team tecnico per verificare che l'ambiente sia pronto per includere semplici riunioni VoIP. In genere, l'abilitazione dei servizi vocali o delle audioconferenze viene esclusa da questa fase della sperimentazione; dipende tuttavia dal team di progetto di base, dalla conformità tecnica e dallo stato di altri servizi vocali/riunioni dell'organizzazione. I requisiti tecnici devono includere elementi come le apparecchiature della sala riunioni, i dispositivi e gli accessori per l'utente finale e la rete. È consigliabile includere video chat e riunioni VoIP nella sperimentazione per ottenere più valore dall'implementazione di Teams. 

### <a name="decision-6-content-management-and-structure"></a>Decisione 6: Gestione e struttura del contenuto
Teams funziona al meglio quando gli utenti lavorano end-to-end all'interno della piattaforma, invece di richiedere loro di tornare continuamente ai sistemi e servizi legacy e offre nuovi modi di lavoro diversi da come gli utenti sono abituati. Nell'ambito dell'esperimento, collaborare con i partecipanti per valutare le strutture del team e i canali che hanno dato vita a metodi multimodali di collaborazione all'interno di Teams ed evitare semplicemente di replicare cartelle e strutture di archiviazione esistenti. Considerare inoltre eventuali requisiti di conformità per il contenuto archiviato all'esterno dei sistemi supportati esistenti, ad esempio i sistemi di gestione dei record o di backup.

### <a name="decision-7--data-security"></a>Decisione 7: Sicurezza dei dati

Durante la preparazione di un'ampia distribuzione, è possibile scegliere di usare le etichette di sicurezza per classificare i tipi di team nel proprio ambiente. Ai fini di questo esperimento, è consigliabile fare riferimento a Piano per la [governance in Teams](plan-teams-governance.md) e verificare che siano stati impostati criteri di conservazione di base sui dati di Teams in Microsoft 365. Per completare il lavoro potrebbe essere necessario coordinare il lavoro con il team tecnico, perché per completare il lavoro sono necessari diritti di amministratore di Microsoft 365.

### <a name="decision-8-length-of-your-experiment"></a>Decisione 8: Durata dell'esperimento

Un'implementazione di Teams riuscita procede a un ritmo sano per garantire un interesse, una concentrazione e un apprendimento appropriati. È consigliabile che questa fase del progetto sia lunga 60 giorni per garantire che i primi adottanti completino cicli aziendali sufficienti. L'estensione della sperimentazione per un tempo troppo lungo aumenta il rischio di un programma di modifica non riuscito; tuttavia, questo periodo varia a seconda dell'organizzazione.  

![Icona che rappresenta il passaggio ](media/teams-adoption-next-icon.png) successivo: Definire [gli scenari di utilizzo](teams-adoption-define-usage-scenarios.md)
