---
title: Documentare il piano Microsoft Teams successo
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/13/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Scegliere un modello di distribuzione, sviluppare una matrice RACI (responsible-accountable-consulted-informed), creare piani di esecuzione e governance.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b891db54d7202eb24df969e3d510a4cc5d7c8be3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624818"
---
# <a name="document-my-success-plan"></a>Documentare il piano di successo

Questo articolo offre una panoramica dei requisiti per documentare correttamente la distribuzione vocale nel cloud. Definendo e documentando tutti i punti di decisione e i passaggi successivi durante la pianificazione della distribuzione vocale nel cloud, è possibile assicurarsi che tutti gli stakeholder e i membri del team di progetto siano allineati al successo dei risultati. 

## <a name="execution-planning"></a>Pianificazione dell'esecuzione 

Dopo aver definito la modalità di implementazione della soluzione audioconferenza o Sistema telefonico con piano chiamate nell'organizzazione, è necessario pianificare l'esecuzione del progetto di implementazione.

Se l'organizzazione ha solo uno o due siti, potrebbe non essere necessario completare tutti i dettagli forniti in questo articolo, ma è consigliabile leggerlo per guidare l'approccio.

<!--ENDOFSECTION-->

## <a name="deployment-model"></a>Modello di distribuzione 

Come per qualsiasi implementazione della tecnologia che trasformi il modo in cui le persone lavorano nell'organizzazione, la scelta del modo giusto per intraprendere la distribuzione influirà notevolmente sul successo dell'implementazione vocale nel cloud.

I modelli di distribuzione potenziali includono quanto segue:

-   **Per sito:** Questo modello è adatto per i casi in cui l'organizzazione è geograficamente dispersa e le filiali hanno un numero significativo di dipendenti. Tuttavia, questo modello di distribuzione può potenzialmente interrompere le comunicazioni all'interno dei reparti in cui i dipendenti del reparto sono distribuiti in diverse posizioni.

-   **Per divisione:** questo modello è in genere l'opzione migliore per le aziende di medie dimensioni e assicura che i reparti coinvolti hanno la stessa esperienza.

-   **Intera società contemporaneamente:** Questo modello è in genere l'opzione migliore per le piccole aziende, in cui tutti i dipendenti ottengono la stessa esperienza dal primo giorno della distribuzione.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere il Teams di esecuzione della distribuzione applicabile all'organizzazione.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Documentare Teams modello di esecuzione della distribuzione scelto e includere le motivazioni aziendali e tecniche.</li></ul></td></tr></table>

## <a name="raci-modeling"></a>Modellazione RACI

Per avere chiarezza su chi è responsabile del progetto, usare una matrice di assegnazione delle responsabilità (nota anche come matrice RACI, responsabile, responsabile, consultata e informata). Elencare la persona o il gruppo responsabile e responsabile di ogni attività, insieme agli stakeholder da consultare nel processo decisionale e agli stakeholder per essere informati di ogni decisione e azione durante l'esecuzione del progetto.

Di seguito è riportato un esempio di matrice RACI per un'implementazione cloud voice.

| Attività/ruolo                                         | Project Cliente potenziale | Cliente potenziale/architetto della collaborazione | Consulente | Change Management/Adoption Specialist | Rappresentanti delle business unit |
|-------------------------------------------------------|--------------|------------------------------|------------|---------------------------------------|-------------------------------|
| Chiamata di avvio della presentazione del programma                     | R, A         | C                            |            |                                       |                               |
| Configurare il dashboard della qualità delle chiamate                         | I            | C                            | R, A       |                                       |                               |
| Condividere il questionario di individuazione durante la chiamata di avvio | I            | C                            | R, A       |                                       |                               |
| Avvio fase di envision                                | R, A         | C                            |            |                                       |                               |
| Workshop casi d'uso aziendali                           | A            |                              |            | R                                     | C                             |
| Esaminare il questionario di individuazione                    |              | R, A                         | C          |                                       |                               |
| Workshop sull'architettura                                 | I            | R, A                         | C          |                                       |                               |
| Scenari utente di adozione Workshop sulla fase di Envision       | C            | I                            | A          | R                                     |                               |
| Workshop di successo sull'adozione                             |              |                              | R, A       | C                                     |                               |
| Workshop sulla conformità di client e dispositivi                  | I            |                              | R, A       | C                                     |                               |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere le attività/ruoli rilevanti per il progetto di implementazione vocale nel cloud.</li><li>Decidere i team o le persone da assegnare alla matrice di assegnazione delle responsabilità (matrice RACI) del progetto di implementazione cloud voice.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Documentare la matrice RACI.</li></ul></td></tr></table>

## <a name="quarterly-execution-plan"></a>Piano di esecuzione trimestrale

Per eseguire la distribuzione vocale nel cloud in blocchi di lavoro gestibili, è consigliabile creare un piano di esecuzione trimestrale in base ai risultati obiettivi, al modello di distribuzione scelto e alla capacità di esecuzione del progetto dell'organizzazione.

In questo modo è possibile tenere traccia dello stato di avanzamento su base trimestrale, rivedere il piano se necessario e distribuire funzionalità vocali cloud in base alla capacità di esecuzione dell'organizzazione.

Se l'organizzazione ha solo uno o due siti, potrebbe non essere necessario un piano di esecuzione trimestrale perché si prevede di essere completamente distribuiti in un breve periodo di tempo.

Di seguito è riportato un esempio di piano di esecuzione trimestrale per la fase Divisione di un'implementazione vocale cloud.

| Sito/divisione                            | Numero di dipendenti | Audioconferenza | Sistema telefonico                    | Trimestre da eseguire |
|------------------------------------------|---------------------|--------------------|---------------------------------|--------------------|
| Stati Uniti: New York                             | 2000                | Sì                | Phone System e Piani di Chiamata | Q1 CY2018          |
| Irlanda: Dublino                          | 300                 | Sì                | Phone System e Piani di Chiamata | Q1 CY2018          |
| Austria: Vienna                          | 500                 | Sì                | Instradamento diretto di Sistema telefonico     | Q2 CY2018          |
| Italia: Milano                             | 200                 | Sì                | N/D                             | Q2 CY2018          |
| Sud America: Brasile                    | 1500                | Sì                | Instradamento diretto di Sistema telefonico     | Q2 CY2018          |
| India: Delhi                             | 7000                | Sì                | N/D                             | Q3 CY2018          |


<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere il piano di esecuzione trimestrale per ottenere i risultati chiave obiettivi (OKR).</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Documentare il piano di esecuzione trimestrale.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="communications-and-governance-plan"></a>Piano di comunicazione e governance

Per mantenere aggiornati gli stakeholder del progetto con lo stato di avanzamento della distribuzione, è necessario definire un piano per le comunicazioni tra i membri principali del team di progetto e con gli stakeholder per discutere di questioni relative allo stato del progetto, ai cardine chiave, ai blocchi e alle varie revisioni del progetto rispetto agli indicatori KPI stabiliti,  metriche operative e obiettivi strategici.

Di seguito è riportato un esempio di piano di comunicazione e governance che è possibile sfruttare nel progetto di implementazione vocale nel cloud.

| Tipo                                        | Obiettivi                                                                                                                                                      | Partecipanti | Giorni/ora                                     | Posizione             | Proprietario della riunione |
|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|-----------------------------------------------|----------------------|---------------|
| Project chiamate in piedi                       | Sincronizzare lo stato del progetto, tenere traccia delle attività cardine chiave e dei blocchi                                                                                           | TBA          | Lunedì, martedì, mercoledì, giovedì 17.00 PST | Virtuale              | TBA           |
| Comitato direttivo settimanale                   | Rivedere lo stato del progetto cloud voice, segnalare ai dirigenti, sollevare problemi che richiedono l'aiuto dei dirigenti per risolvere                                        | TBA          | Ogni venerdì 11:00 PST                        | Virtuale              | TBA           |
| Revisione aziendale/operativa mensile del progetto | Controllare lo stato del progetto con gli stakeholder estesi, i punti di contatto principali e gli sponsor dirigenti; esaminare il piano di distribuzione, gli indicatori KPI e le metriche operative | TBA          | Secondo martedì del mese                       | Virtuale o di persona | TBA           |
| Revisione commerciale trimestrale (QBR)             | Controllare lo stato del progetto ed esaminare lo stato di avanzamento rispetto a obiettivi strategici, indicatori KPI e metriche operative; Rivedere i piani, se necessario                                 | TBA          | Ultimo giovedì di ogni trimestre                | In persona            | TBA           |


<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere il piano di comunicazione e governance, tra cui la frequenza degli aggiornamenti di stato regolari (giornalieri, settimanali, mensili o trimestrali), i metodi per condurre le riunioni di aggiornamento dello stato e il proprietario di ogni riunione.</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Documentare il piano di comunicazione e governance.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="finalize-my-success-plan"></a>Finalizzare il piano di successo

Un piano di successo è il riepilogo della documentazione creata nella fase di Envision.

Il piano di successo fornisce al team di progetto, che può includere FastTrack o un partner di distribuzione, informazioni sufficienti per realizzare gli obiettivi dell'organizzazione con l'implementazione dell'audioconferenza o del Sistema telefonico con il servizio Piano per le chiamate.

In generale, un piano di successo contiene le sezioni principali seguenti, molte delle quali saranno state lavorate durante la fase di Envision:

-   Caso aziendale

-   Prontezza del servizio

-   Decisioni relative ai servizi

-   Piano di esecuzione

-   Piano di adozione

-   Piano operativo

### <a name="business-case"></a>Caso aziendale

I casi d'uso aziendali, l'elenco di stakeholder, OKR e KPI, i registri dei rischi e le sequenze temporali dei progetti costituiscono in genere la maggior parte delle informazioni necessarie per un caso aziendale. È consigliabile documentare questi elementi come parte del piano di successo.

### <a name="service-readiness"></a>Prontezza del servizio

La valutazione dell'ambiente fornisce le informazioni iniziali necessarie per determinare la preparazione tecnica dell'organizzazione all'implementazione delle audioconferenze e/o Sistema telefonico piano per chiamate.

Qui è inclusa la valutazione della conformità del servizio e il piano per affrontare le aree che devono essere corretti individuate tramite la valutazione dell'ambiente.

### <a name="service-decisions"></a>Decisioni relative ai servizi

Documentare come è stata pianificata l'audioconferenza o Sistema telefonico con l'implementazione tecnica del servizio Piano chiamate per l'organizzazione.

### <a name="execution-plan"></a>Piano di esecuzione

Documentare come è stata pianificata l'esecuzione del progetto per implementare la soluzione in tutta l'organizzazione.

### <a name="adoption-plan"></a>Piano di adozione

Dopo aver eseguito la valutazione della conformità all'adozione, il team di progetto deve creare un set completo di piani di comunicazione, un piano di formazione e piani per le attività di adozione pre-lancio, lancio e post-lancio.

Identificare le risorse per supportare le attività di adozione, ad esempio volantini, messaggi di posta elettronica di benvenuto e materiali di formazione, oltre a tutte le personalizzazioni necessarie per soddisfare i requisiti dell'organizzazione.

Scaricare i modelli per le attività di adozione [dal Microsoft Teams Customer Success Kit](https://aka.ms/TeamsCustomerSuccess).

### <a name="operational-plan"></a>Piano operativo

L'esercizio della mappatura dei ruoli operativi stabilirà ruoli e responsabilità e i team assegnati a ogni ruolo operativo, che sarà necessario supportare l'implementazione delle audioconferenze.

È necessario completare questa operazione e includere il piano operativo come parte del piano di successo per garantire la conformità operativa della soluzione.

<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere come documentare l'intero piano di successo per la distribuzione dei carichi di lavoro vocali nel cloud.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Verificare che tutti i componenti del piano di successo siano stati documentati.</li><li>Aggregare singoli componenti del piano di successo in un unico documento di riepilogo (facoltativo).</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
