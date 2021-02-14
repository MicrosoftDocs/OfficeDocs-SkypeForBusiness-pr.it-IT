---
title: Documentare il piano di successo di Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/13/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Scegliere un modello di distribuzione, sviluppare una matrice RACI (Responsible-accountable-consulted-informed), creare piani di esecuzione e governance.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40f88c93e20fde89eb9791cc90760d554e52a004
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "44512813"
---
# <a name="document-my-success-plan"></a>Documentare il piano di successo

Questo articolo offre una panoramica dei requisiti per documentare correttamente la distribuzione vocale nel cloud. Definendo e documentando tutti i punti di decisione e i passaggi successivi durante la pianificazione della distribuzione vocale nel cloud, è possibile assicurarsi che tutti gli stakeholder e i membri del team di progetto siano allineati alla riuscita dei risultati. 

## <a name="execution-planning"></a>Pianificazione esecuzione 

Dopo aver definito come implementare la soluzione Audioconferenza o Sistema telefonico con piano per chiamate nella tua organizzazione, devi pianificare l'esecuzione del progetto di implementazione.

Se l'organizzazione ha solo uno o due siti, potrebbe non essere necessario completare tutti i dettagli forniti in questo articolo, ma è consigliabile leggerlo per guidare l'approccio.

<!--ENDOFSECTION-->

## <a name="deployment-model"></a>Modello di distribuzione 

Come con qualsiasi implementazione della tecnologia che trasforma il modo di lavorare delle persone nell'organizzazione, la scelta del modo giusto per intraprendere la distribuzione influisce in modo notevole sul successo dell'implementazione vocale nel cloud.

I possibili modelli di distribuzione includono:

-   **Per sito:** Questo modello è adatto per i casi in cui l'organizzazione si disloca geograficamente e le filiali hanno un numero significativo di dipendenti. Tuttavia, questo modello di distribuzione può interrompere la comunicazione all'interno dei reparti in cui i dipendenti del reparto sono distribuiti in diverse posizioni.

-   **Per divisione:** questo modello è in genere l'opzione migliore per le aziende di medie dimensioni e assicura che i reparti coinvolti hanno la stessa esperienza.

-   **Intera società contemporaneamente:** Questo modello è in genere l'opzione migliore per le piccole aziende, in cui tutti i dipendenti ottengono la stessa esperienza dal primo giorno della distribuzione.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere il modello di esecuzione della distribuzione di Teams applicabile all'organizzazione.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Documentare il modello di esecuzione della distribuzione di Teams scelto e includere le motivazioni aziendali e tecniche.</li></ul></td></tr></table>

## <a name="raci-modeling"></a>Modellazione RACI

Per assicurarsi di avere chiarezza su chi è responsabile di ciò che è stato fatto nel progetto, usare una matrice di assegnazione di responsabilità (nota anche come MATRICE RACI, responsabile, responsabile, consultata e informata). Elencare la persona o il gruppo responsabile di ogni attività, insieme agli stakeholder che devono essere consultati nel processo decisionale e gli stakeholder in modo che siano informati sulle decisioni e sulle azioni che devono eseguire durante l'esecuzione del progetto.

Di seguito è riportato un esempio di matrice RACI per un'implementazione vocale nel cloud.

| Attività/ruolo                                         | Cliente potenziale del progetto | Lead/Architect per la collaborazione | Consulente | Esperto nella gestione delle modifiche e nell'adozione | Rappresentanti dell'unità commerciale |
|-------------------------------------------------------|--------------|------------------------------|------------|---------------------------------------|-------------------------------|
| Chiamata di avvio presentazione del programma                     | R, A         | C                            |            |                                       |                               |
| Configurare Call Quality Dashboard                         | I            | C                            | R, A       |                                       |                               |
| Condividere il questionario di individuazione durante la chiamata di avvio | I            | C                            | R, A       |                                       |                               |
| Avvio della fase divisione                                | R, A         | C                            |            |                                       |                               |
| Laboratori per casi d'uso aziendali                           | A            |                              |            | R                                     | C                             |
| Esaminare il questionario di individuazione                    |              | R, A                         | C          |                                       |                               |
| Laboratori di architettura                                 | I            | R, A                         | C          |                                       |                               |
| Scenari per l'adozione- Pianificazione di un workshop della fase di adozione       | C            | I                            | A          | R                                     |                               |
| Workshop di successo dell'adozione                             |              |                              | R, A       | C                                     |                               |
| Laboratori di preparazione per clienti e dispositivi                  | I            |                              | R, A       | C                                     |                               |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere le attività/ruoli rilevanti per il progetto di implementazione vocale nel cloud.</li><li>Decidere i team o le persone da assegnare alla matrice DI ASSEGNAZIONE DI RESPONSABILITÀ del progetto di implementazione vocale cloud.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Documentare la matrice RACI.</li></ul></td></tr></table>

## <a name="quarterly-execution-plan"></a>Piano di esecuzione trimestrale

Per eseguire la distribuzione vocale nel cloud in blocchi di lavoro gestibili, è consigliabile creare un piano di esecuzione trimestrale basato sui risultati chiave obiettivo, sul modello di distribuzione scelto e sulla funzionalità di esecuzione del progetto dell'organizzazione.

In questo modo è possibile tenere traccia dello stato di avanzamento su base trimestrale, rivedere il piano se necessario e distribuire le funzionalità vocali nel cloud in base alla capacità di esecuzione dell'organizzazione.

Se l'organizzazione ha solo uno o due siti, potrebbe non essere necessario un piano di esecuzione trimestrale perché si prevede di essere completamente distribuiti in un breve periodo di tempo.

Di seguito è riportato un esempio di piano di esecuzione trimestrale per la fase di sviluppo di un'implementazione vocale cloud.

| Sito/reparto                            | Numero di dipendenti | Audioconferenza | Phone System                    | Trimestre da eseguire |
|------------------------------------------|---------------------|--------------------|---------------------------------|--------------------|
| Stati Uniti: New York                             | 2000                | Sì                | Phone System e Piani di Chiamata | T1 CY2018          |
| Irlanda: Dublino                          | 300                 | Sì                | Phone System e Piani di Chiamata | T1 CY2018          |
| Austria: Austria: Austria                          | 500                 | Sì                | Instradamento diretto di Sistema telefonico     | T2 CY2018          |
| Italia: Milano                             | 200                 | Sì                | N/D                             | T2 CY2018          |
| America del Sud: Brasile                    | 1500                | Sì                | Instradamento diretto di Sistema telefonico     | T2 CY2018          |
| India: Delhi                             | 7000                | Sì                | N/D                             | T3 CY2018          |


<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Stabilire il piano di esecuzione trimestrale per ottenere i risultati chiave obiettivi (OKRs).</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Documentare il piano di esecuzione trimestrale.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="communications-and-governance-plan"></a>Piano di governance e comunicazioni

Per mantenere gli stakeholder del progetto aggiornati con lo stato del progetto, è necessario definire un piano per la modalità di comunicazione tra i principali membri del team di progetto e con le parti interessate per discutere di questioni relative allo stato del progetto, alle principali attività cardine, ai blocchi e alle varie revisioni del progetto rispetto agli indicatori KPI stabiliti, alle metriche operative e agli obiettivi strategici.

Di seguito è riportato un esempio di piano di comunicazione e governance che è possibile sfruttare nel progetto di implementazione vocale nel cloud.

| Tipo                                        | Obiettivi                                                                                                                                                      | Partecipanti | Giorni/ora                                     | Posizione             | Proprietario della riunione |
|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|-----------------------------------------------|----------------------|---------------|
| Chiamate standup di Project                       | Sincronizzare lo stato del progetto, tenere traccia delle principali attività cardine e blocchi                                                                                           | TBA          | Lunedì, martedì, mercoledì, giovedì 17:00 PST | Virtuale              | TBA           |
| Comitato settimanale che ruota                   | Rivedere lo stato del progetto vocale nel cloud, 2016 per i dirigenti, sollevare problemi che richiedono l'aiuto dei dirigenti per la risoluzione                                        | TBA          | Ogni venerdì 11.00 PST                        | Virtuale              | TBA           |
| Revisione aziendale/operativa del progetto mensile | Verificare lo stato del progetto con gli stakeholder estesi, i punti di contatto principali e gli sponsor della direzione; esaminare il piano di distribuzione, gli indicatori KPI e le metriche operative | TBA          | Secondo martedì del mese                       | Virtuale o di persona | TBA           |
| Revisione commerciale trimestrale (QBR)             | Controllare lo stato del progetto ed esaminare i progressi rispetto a obiettivi strategici, indicatori KPI e metriche operative; rivedere i piani, se necessario                                 | TBA          | Ultimo giovedì di ogni trimestre                | In persona            | TBA           |


<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere il piano di comunicazione e governance, tra cui la frequenza dei regolari aggiornamenti di stato (giornaliera, settimanale, mensile o trimestrale), i metodi per condurre le riunioni di aggiornamento dello stato e il proprietario di ogni riunione.</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Documentare il piano di comunicazione e governance.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="finalize-my-success-plan"></a>Finalizzare il piano di successo

Un piano di successo è il riepilogo della documentazione creata nella fase di sviluppo.

Il piano di successo offre al team di progetto, che può includere FastTrack o un partner di distribuzione, informazioni sufficienti per realizzare gli obiettivi dell'organizzazione implementando il servizio Audioconferenza o Sistema telefonico con piano per chiamate.

In generale, un piano di successo contiene le sezioni principali seguenti, molte delle quali saranno state descritte nella fase di sviluppo:

-   Caso aziendale

-   Prontezza del servizio

-   Decisioni relative al servizio

-   Piano di esecuzione

-   Piano di adozione

-   Piano operativo

### <a name="business-case"></a>Caso aziendale

Casi d'uso aziendali, l'elenco di stakeholder, OKRs e indicatori KPI, i registri dei rischi e le tempistiche del progetto in genere costituiscono la massa di informazioni necessarie per un caso aziendale. È consigliabile documenta queste informazioni nell'ambito del piano di successo.

### <a name="service-readiness"></a>Prontezza del servizio

La valutazione ambientale fornisce le informazioni iniziali necessarie per determinare la conformità tecnica dell'organizzazione all'implementazione di Audioconferenze e/o Sistema telefonico con Piano per chiamate.

Di seguito è inclusa la valutazione di conformità del servizio e il piano per affrontare le aree che devono essere corretti individuate tramite la valutazione dell'ambiente.

### <a name="service-decisions"></a>Decisioni relative al servizio

Documentare il modo in cui è stata pianificata l'audioconferenza o il sistema telefonico con l'implementazione tecnica del servizio Piano per chiamate per l'organizzazione.

### <a name="execution-plan"></a>Piano di esecuzione

Documentare come è stata pianificata l'esecuzione del progetto per implementare la soluzione nell'intera organizzazione.

### <a name="adoption-plan"></a>Piano di adozione

Dopo aver eseguito la valutazione di conformità all'adozione, il team di progetto deve creare un set completo di piani di comunicazione, un piano di formazione e piani per le attività di adozione prima del lancio, del lancio e post-lancio.

Identificare le risorse per supportare le attività di adozione, ad esempio volantini, messaggi di posta elettronica di benvenuto e materiali di formazione, oltre a tutte le personalizzazioni necessarie per soddisfare i requisiti dell'organizzazione.

Scaricare i modelli per le attività di adozione dal [Microsoft Teams Customer Success Kit.](https://aka.ms/TeamsCustomerSuccess)

### <a name="operational-plan"></a>Piano operativo

L'esercizio della mappatura dei ruoli operativi stabilirà ruoli e responsabilità e i team assegnati a ogni ruolo operativo, che sarà necessario supportare l'implementazione delle audioconferenze.

È necessario completare questa operazione e includere il piano operativo nell'ambito del piano di successo per garantire la preparazione operativa della soluzione.

<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Punti decisionali</td><td><ul><li>Decidere come documentare l'intero piano di successo per la distribuzione dei carichi di lavoro vocali nel cloud.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Passaggi successivi</td><td><ul><li>Verificare che tutti i componenti del piano di successo siano stati documentati.</li><li>Aggregare i singoli componenti del piano di successo in un unico documento di riepilogo (facoltativo).</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
