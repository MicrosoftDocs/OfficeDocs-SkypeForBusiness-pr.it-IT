---
title: Definire il successo in servizi di audioconferenza, sistema telefonico con piani di chiamata o routing diretto del sistema telefonico-Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/07/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Misurare i risultati dei servizi di audioconferenza, del sistema telefonico con i piani di chiamata o del sistema telefonico Direct routing Deployment e verificare che siano stati raggiunti gli esiti desiderati.
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: a84f0d38afbac74b296ccdfed626d6f8830d46a9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244167"
---
# <a name="define-my-success"></a>Definire il successo

Questo articolo offre una panoramica dei requisiti per la definizione del successo per la distribuzione di servizi di audioconferenza, sistema telefonico con piani di chiamata o routing diretto del sistema telefonico per l'organizzazione. Definendo correttamente l'aspetto del successo, è possibile misurare i risultati man mano che si procede alla distribuzione e verificare che gli esiti raggiunti siano quelli desiderati.

<!--ENDOFSECTION-->

I servizi di **audioconferenza** includono le organizzazioni con punti di ingresso aggiuntivi per le riunioni (ad hoc o pianificate) consentendo ai partecipanti alla riunione di partecipare tramite PSTN (Public Switched Telephone Network) tramite la chiamata tramite telefono fisso tradizionale, privato PBX (Branch Exchange) o telefoni cellulari. Ciò è utile quando l'organizzatore o i partecipanti non si trovano davanti a un computer o quando le connessioni dati non sono disponibili o troppo inaffidabili per supportare le comunicazioni vocali, ad esempio in un'area remota con una copertura dati mobile spotty o connessa a una rete Wi-Fi pubblica gratuita. servizio con larghezza di banda limitata o quando i partecipanti alla riunione preferiscono connettersi alla riunione usando un endpoint di telefonia facilmente accessibile.

Il **sistema telefonico con piani di chiamata ("piani di chiamata")** offre alle organizzazioni un modo per modernizzare il proprio ambiente di lavoro, consentendo agli utenti di effettuare chiamate telefoniche aziendali da computer e dispositivi mobili. L'ammodernamento del luogo di lavoro può essere incluso in un numero qualsiasi di scenari, ovvero un'implementazione di lavoro basata su attività, uno dei principali movimenti di Office, un aggiornamento di Office fit-out, un ritiro di una soluzione PBX legacy, la conclusione di un contratto di provider di servizi PSTN e così via. Con i piani per le chiamate, Microsoft semplifica la connettività alla rete PSTN.

**Sistema telefonico Direct routing ("Direct routing")** offre agli organismi gli stessi vantaggi elencati sopra per i piani di chiamata, ad eccezione del fatto che la connettività PSTN è facilitata da un provider di terze parti anziché da Microsoft. Ciò consente la distribuzione in paesi in cui i piani di chiamata non sono disponibili o nelle distribuzioni in cui deve essere mantenuto un contratto di provider di servizi PSTN esistente o è necessaria l'interoperabilità con determinati sistemi locali. Uno scenario aggiuntivo per considerare il routing diretto è l'interoperabilità del sistema telefonico. Mentre gli utenti vengono trasferiti alla chiamata in teams, alcuni utenti potrebbero rimanere in PBX legacy. Il routing diretto consente a entrambi i casi di utilizzo di coesistere. Il traffico delle chiamate tra gli utenti nei sistemi legacy e gli utenti di teams restano all'interno dell'organizzazione.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Definire i casi di utilizzo aziendale per i servizi di audioconferenza, i piani di chiamata o il routing diretto

Per iniziare, gli stakeholder del progetto principale devono definire i casi di utilizzo aziendale che supportano l'implementazione di servizi di audioconferenza, piani di chiamata o routing diretto.

I casi di utilizzo aziendale hanno lo scopo di definire e documentare i risultati aziendali previsti e misurabili e includono quanto segue:

-   Descrizione del processo aziendale corrente

-   Problemi con il processo aziendale esistente

-   Come la tecnologia può aiutare a superare queste sfide

-   I risultati aziendali previsti e misurabili, se queste sfide vengono superate

> [!TIP]
> Di seguito è riportato un esempio di un caso di utilizzo aziendale completato per i servizi di audioconferenza:
> 
> |         |
> |---------|
> |**Descrizione del processo aziendale corrente**<br>Contoso attualmente si basa su servizi di conferenza PSTN forniti dal provider di telefonia locale in carica a pagamento per i minuti di riunione per riunioni interne e riunioni che coinvolgono parti esterne.|
> |**Problemi con il processo aziendale esistente**<br>Contoso spende circa USD1 milioni all'anno per il servizio di conferenza PSTN corrente, con il 75% dei costi sostenuti per le riunioni interne. L'uso di endpoint di telefonia tradizionali per partecipare alle riunioni ospitate dal servizio di conferenza PSTN non è allineato con il piano per l'organizzazione di adottare teams come piattaforma di comunicazione e collaborazione moderna.|
> |**Come la tecnologia può superare queste sfide**<br>Con l'adozione di Microsoft teams come piattaforma di comunicazione e collaborazione moderna, gli utenti interni dovrebbero partecipare principalmente alle riunioni usando i loro PC dotati di auricolari ottimizzati e dispositivi per la sala riunioni. Il servizio di audioconferenza sarà disponibile per supportare partecipanti esterni o per supportare situazioni in cui l'uso di audio per PC non è favorevole per i partecipanti interni.|
> |**Attesi, misurabili, risultati aziendali**<br>Il passaggio a teams come piattaforma di comunicazione e collaborazione moderna, in combinazione con il servizio di audioconferenza, riduce notevolmente il costo di distribuzione del servizio di conferenza PSTN.|

<br>

> [!TIP]
> Di seguito è riportato un esempio di un caso di utilizzo aziendale completato per i piani di chiamata:
> 
> |         |
> |---------|
> |**Descrizione del processo aziendale corrente**<br>La configurazione standard delle aree di lavoro di Office di Contoso include un telefono da tavolo per ogni scrivania. A ogni dipendente è stato assegnato un numero di telefono diretto (DID). I telefoni desktop sono connessi a un sistema PBX e connessi alla rete PSTN tramite trunk SIP (Session Initiation Protocol). I dipendenti possono solo effettuare e ricevere chiamate telefoniche presso i telefoni desktop assegnati.|
> |**Problemi con il processo aziendale esistente**<br>L'analisi dell'uso dei telefoni desktop Mostra che solo il 10% dei telefoni desktop viene usato attivamente, con il resto configurato per inoltrare le chiamate ai telefoni cellulari o per squillare simultaneamente ai telefoni cellulari. Il mantenimento del sistema PBX esistente e dei telefoni desktop associati contribuisce al 20% del costo del servizio di telefonia mensile di contoso.|
> |**Come la tecnologia può superare queste sfide**<br>I piani per le chiamate consentiranno al computer personale dell'utente di ricevere e inserire chiamate telefoniche tramite la rete dati sfruttando l'app nativa di Microsoft teams. In questo modo, viene eliminata la necessità di implementare e gestire i telefoni desktop e si apre l'opportunità di rimuovere la Commissione dal sistema PBX esistente, perché il servizio telefonico può essere recapitato tramite il cloud tramite la rete senza dipendenze da un sistema telefonico tradizionale.|
> |**Attesi, misurabili, risultati aziendali**<br>La rimozione dei requisiti di manutenzione e la disattivazione di PBX legacy e telefoni desktop consentiranno una riduzione del 20% delle spese mensili del servizio di telefonia. I piani per le chiamate semplificano le aree di lavoro di Office, consentendo a Contoso di espandere le proprie attività stabilendo nuovi uffici con costi di telefonia upfront minimi.|

<br>

> [!TIP]
> Di seguito è riportato un esempio di un caso di utilizzo aziendale completato per il routing diretto:
> 
> |         |
> |---------|
> |**Descrizione del processo aziendale corrente**<br>La configurazione standard delle aree di lavoro di Office di Contoso include un telefono da tavolo per ogni scrivania. A ogni dipendente è stato assegnato un numero di telefono diretto (DID). I telefoni desktop sono connessi a un sistema PBX e connessi alla rete PSTN tramite trunk SIP (Session Initiation Protocol). I dipendenti possono solo effettuare e ricevere chiamate telefoniche presso i telefoni desktop assegnati.|
> |**Problemi con il processo aziendale esistente**<br>L'analisi dell'uso dei telefoni desktop Mostra che solo il 10% dei telefoni desktop viene usato attivamente, con il resto configurato per inoltrare le chiamate ai telefoni cellulari o per squillare simultaneamente ai telefoni cellulari. Il mantenimento del sistema PBX esistente e dei telefoni desktop associati contribuisce al 20% del costo del servizio di telefonia mensile di contoso.|
> |**Come la tecnologia può superare queste sfide**<br>Il contratto provider trunk SIP è stato firmato di recente e sarà in vigore per tre anni. Il routing diretto consente la fornitura di connettività PSTN da parte del provider trunk SIP e consentirà anche al computer personale dell'utente di ricevere e inserire chiamate telefoniche tramite la rete dati sfruttando l'app nativa di Microsoft teams. In questo modo, viene eliminata la necessità di implementare e gestire i telefoni desktop e si apre l'opportunità di rimuovere la Commissione dal sistema PBX esistente, mantenendo al contempo un ingombro limitato per il controller della sessione locale (SBC).|
> |**Attesi, misurabili, risultati aziendali**<br>La rimozione dei requisiti di manutenzione e la disattivazione di PBX legacy e telefoni desktop consentiranno una riduzione del 20% delle spese mensili del servizio di telefonia. Il routing diretto semplifica le aree di lavoro di Office, consentendo a Contoso di espandere le proprie attività stabilendo nuovi uffici con costi di telefonia upfront minimi.|

Oltre a definire i casi di utilizzo aziendale, per impostare i limiti del progetto, è necessario puntare alla chiarezza in giro:

-   **Ambito organizzativo:** L'implementazione di servizi di audioconferenza, piani di chiamata o routing diretto può includere l'intera organizzazione o solo le singole unità aziendali.

-   **Sequenza temporale del progetto:** Sequenza temporale specifica in cui verrà eseguito il progetto.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> |Punti decisionali|<ul><li>Quali sono tutti i casi di utilizzo aziendale per i servizi di audioconferenza che è possibile identificare nell'organizzazione?</li><li>Quali sono tutti i casi di utilizzo aziendale per i piani di chiamata che è possibile identificare nell'organizzazione?</li><li>Quali sono tutti i casi di utilizzo aziendale per il routing diretto che è possibile identificare nell'organizzazione?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Documentare tutti i casi di utilizzo aziendale per i servizi di audioconferenza per l'organizzazione.</li><li>Documentare tutti i casi di utilizzo aziendale per chiamare piani per l'organizzazione.</li><li>Documentare tutti i casi di utilizzo aziendale per il routing diretto per l'organizzazione.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identificare le parti interessate principali

I casi di utilizzo aziendale definiti nel passaggio precedente includono un ambito organizzativo per i servizi di audioconferenza, i piani di chiamata o l'implementazione di routing diretto. In base a questo, puoi completare la matrice completa degli stakeholder per includere le persone giuste da coinvolgere nel progetto.

> [!TIP]
> Di seguito è riportato un esempio di modello di matrice delle parti interessate che può essere usato per documentare le parti interessate del progetto:
> 
> |Ruolo  |Descrizione  |Nome, informazioni di contatto, posizione  |
> |---------|---------|---------|
> |Sponsor esecutivo di Project|<ul><li>Prendere l'ultima autorità e la responsabilità per il progetto e la consegna sugli obiettivi del progetto.</li><li>Aiutare a risolvere i problemi escalati dal Lead del progetto.</li><li>Sponsorizzare la comunicazione all'interno della società sugli obiettivi del progetto.</li><li>Prendere decisioni strategiche chiave.</li><li>Verificare la disponibilità delle risorse necessarie e del preventivo.</li><li>Conduci le recensioni commerciali trimestrali (QBRs).</li><li>Drive buy-in e supporto degli sforzi della campagna di sensibilizzazione.</li><li>Fungere da sponsor del progetto per l'implementazione del programma.</li></ul>|TBA|
> |Lead progetto|<ul><li>Gestire e guidare il team di progetto.</li><li>Coordinare partner e team di lavoro impegnati nel progetto.</li><li>Essere responsabili della creazione e della gestione dei piani di progetto per soddisfare i risultati chiave trimestrali.</li><li>Risolvere i problemi interfunzionali.</li><li>Fornisci aggiornamenti regolari agli sponsor del progetto.</li><li>Incorporare gli aspetti di adozione nel piano di progetto all-up.</li><li>Conduci le recensioni aziendali e operative mensili (MBR), Contribuisci a QBRs.</li></ul>|TBA|
> |Lead di collaborazione/architetto|<ul><li>Eseguire la strategia di collaborazione definita dai dirigenti aziendali.</li><li>Analizza e scegli i prodotti di collaborazione che soddisfano gli obiettivi aziendali per la società.</li><li>Progettare le operazioni per i prodotti di collaborazione.</li><li>Definire i modelli di operazione e supporto.</li><li>Contribuisci a revisioni commerciali mensili e trimestrali.</li></ul>|TBA|
> |Consulente|<ul><li>Essere responsabili per i servizi di configurazione</li><li>Contribuisci all'architettura complessiva della soluzione.</li></ul>|TBA|
> |Project Manager|<ul><li>Sviluppare e gestire il piano di progetto.</li><li>Gestire i risultati finali del progetto in linea con il piano di progetto e il preventivo.</li><li>Registrare e gestire i problemi di progetto, incluse le escalation.</li><li>Effettuare chiamate in standup settimanali.</li><li>Collaborare e dare aggiornamenti a Project Executive sponsor.</li><li>Collaborare con l'architetto per definire i piani di comunicazione e approccio per la gestione delle modifiche.</li></ul>|TBA|
> |Specialista per la gestione/adozione delle modifiche|<ul><li>Fornisci l'input durante la fase di individuazione nei processi di adozione e formazione.</li><li>Partecipare al workshop di strategia di adozione.</li><li>Sviluppare e assumersi la responsabilità della strategia di adozione.</li><li>Sviluppare ed eseguire il piano di comunicazione.</li><li>Offrire corsi di formazione agli utenti.</li><li>Raccogliere feedback e condurre sondaggi.</li></ul>|TBA|
> |Cavo di rete|<ul><li>Fornisca l'input durante la fase di individuazione nella progettazione della rete.</li><li>Partecipare alla pianificazione durante il workshop fase di ideazione.</li><li>Coordinare il lavoro del team di rete durante l'esecuzione del progetto.</li></ul>|TBA|
> |Lead di sicurezza|<ul><li>Fornisci l'input durante la fase di individuazione in progettazione e processi di sicurezza.</li><li>Partecipare alla pianificazione durante il workshop fase di ideazione.</li><li>Coordinare il lavoro del team di sicurezza durante l'esecuzione del progetto.</li></ul>|TBA|
> |Lead per la telefonia|<ul><li>Fornisci l'input durante la fase di individuazione nella progettazione della telefonia.</li><li>Partecipare alla pianificazione durante il workshop fase di ideazione.</li><li>Coordinare il lavoro del team di telefonia durante l'esecuzione del progetto.</li></ul>|TBA|
> |Lead desktop|<ul><li>Fornisci l'input durante la fase di individuazione nel processo client e aggiornamento.</li><li>Partecipare alla pianificazione durante il workshop di ideazione.</li><li>Coordinare il lavoro del team desktop durante l'esecuzione del progetto.</li></ul>|TBA|
> |Supporto/help desk lead|<ul><li>Fornisca l'input durante la fase di individuazione nei modelli operativi e di supporto.</li><li>Partecipare alla pianificazione durante il workshop fase di ideazione.</li><li>Partecipare alla pianificazione del modello di supporto.</li><li>Coordina il lavoro dei team e delle risorse di supporto durante l'esecuzione del progetto.</li></ul>|TBA|
> |Rappresentanti delle unità commerciali|<ul><li>Contribuisci a guide e materiali di adozione basati sull'utente.</li><li>Collaborare e rivedere i casi di utilizzo aziendale.</li></ul>|TBA|
> |Lead di distribuzione|<ul><li>Verificare che i prerequisiti di distribuzione vengano soddisfatti.</li><li>Coinvolgere le risorse per partecipare alle attività di fase a bordo.</li><li>Partecipare alle riunioni per rivedere e preparare report in stato di distribuzione.</li></ul>|TBA|
> |Amministratori IT|<ul><li>Assistenza per la pianificazione e l'esecuzione di test. Questo ruolo è per professionisti IT.</li></ul>|TBA|
> |Proprietario del servizio|<ul><li>Essere responsabili per il funzionamento dei servizi di audioconferenza, per i piani di chiamata o per il servizio di routing diretto.</li><li>Possedere i servizi di audioconferenza, i piani di chiamata o il servizio di routing diretto.</li></ul>|TBA|
> |Campioni di qualità|<ul><li>Qualità dell'unità, affidabilità e feedback degli utenti.</li><li>Identificare le tendenze della qualità e il risanamento delle unità con i rispettivi team.</li><li>Riporta il comitato direttivo alla leadership.</li><li>Segnalare la qualità, l'affidabilità e il sentimento degli utenti attraverso la valutazione della chiamata e del Punteggio di Net Promoter.</li></ul>|TBA|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Punti decisionali|<ul><li>Chi riempie ogni ruolo chiave delle parti interessate per l'organizzazione?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Documentare tutte le parti interessate chiave e comunicare le responsabilità e le aspettative del ruolo a ogni individuo assegnato.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Definire OKRs, KSIs e risks

Con le parti interessate del progetto assemblate, è possibile tradurre i casi di utilizzo aziendale, l'ambito organizzativo e le sequenze temporali di Project in obiettivi e risultati chiave (OKRs) e le misure di successo del progetto possono essere definite come elenco di indicatori di successo chiave (KSIs).

La partecipazione completa degli stakeholder del progetto alla definizione di OKRs e KSIs è essenziale per garantire che sentano il senso della proprietà e allineino queste misure di successo ai requisiti aziendali dell'organizzazione.

OKRs contiene gli obiettivi impostati all'inizio del progetto e si definiscono i risultati chiave misurabili su base trimestrale. È possibile rivedere mensilmente i risultati chiave per tenere traccia dello stato del progetto globale e, in base allo stato di avanzamento, si regolano i piani trimestrali, se necessario.

> [!TIP]
> Di seguito sono indicati alcuni esempi di OKRs rilevanti per un'implementazione di audioconferenza:
> <br>
> 
> **Visione: aumentare la produttività massimizzando gli investimenti in Office 365**
> 
> |Obiettivi  |Risultati chiave  |da fare  |
> |---------|---------|---------|
> |Distribuire i servizi di audioconferenza in teams entro la fine dell'anno fiscale 2018|FY18Q1: distribuire i servizi di conferenza audio in teams globalmente|Immaginare<ul><li>Creare un piano di successo</li><li>Creare un piano di implementazione tecnica dettagliato</li></ul><p>Accogli i<ul><li>Esegui piano di successo</li><li>Esecuzione di un piano di implementazione tecnica</li></ul>|
> |Smantellare il servizio di conferenza PSTN legacy a livello globale entro la metà dell'anno fiscale 2018|FY18Q2: discommission legacy servizi di conferenza PSTN a livello globale|Valore unità<ul><li>Aumentare l'impegno degli utenti e l'adozione delle unità</li><li>Gestire e preparare le modifiche</li><li>Misurare, condividere il successo e iterare</li>|

<br>

> [!TIP]
> Di seguito sono riportati alcuni esempi di OKRs rilevanti per l'implementazione di piani di chiamata:
> <br>
> 
> **Visione: aumentare la produttività massimizzando gli investimenti in Office 365**
> 
> |Obiettivi  |Risultati chiave  |da fare  |
> |---------|---------|---------|
> |Distribuire piani di chiamata nelle succursali europee entro la fine dell'anno fiscale 2018|FY18Q3: distribuire piani per le chiamate in Office a Londra|Immaginare<ul><li>Creare un piano di successo</li><li>Creare un piano di implementazione tecnica dettagliato</li></ul><p>Accogli i<ul><li>Esegui piano di successo</li><li>Esecuzione di un piano di implementazione tecnica</li></ul>|
> |Discommission legacy PBX a Londra Office entro la fine dell'anno fiscale 2018|FY18Q4: discommission legacy PBX in Office a Londra|Valore unità<ul><li>Aumentare l'impegno degli utenti e l'adozione delle unità</li><li>Gestire e preparare le modifiche</li><li>Misurare, condividere il successo e iterare</li>|
> 
> [!TIP]
> Di seguito sono indicati alcuni esempi di OKRs rilevanti per un'implementazione di routing diretto:
> <br>
> 
> **Visione: aumentare la produttività massimizzando gli investimenti in Office 365**
> 
> |Obiettivi  |Risultati chiave  |da fare  |
> |---------|---------|---------|
> |Distribuire il routing diretto nelle succursali canadesi entro la fine dell'anno fiscale 2018|FY18Q3: distribuire il routing diretto in Toronto Office|Immaginare<ul><li>Creare un piano di successo</li><li>Creare un piano di implementazione tecnica dettagliato</li></ul><p>Accogli i<ul><li>Esegui piano di successo</li><li>Esecuzione di un piano di implementazione tecnica</li></ul>|
> |Discommission legacy PBX in Toronto Office entro la fine dell'anno fiscale 2018|FY18Q4: discommission PBX legacy in Toronto Office|Valore unità<ul><li>Aumentare l'impegno degli utenti e l'adozione delle unità</li><li>Gestire e preparare le modifiche</li><li>Misurare, condividere il successo e iterare</li>|

<br>

KSIs misura la qualità e il successo dei risultati chiave e completano la natura binaria di OKRs (raggiunta o non conseguita) Detailing buoni e/o risultati negativi.

Quando si definisce KSIs, è consigliabile usare i criteri "specifici, misurabili, assegnabili, realistici e relativi al tempo" (SMART):

-   Specifico: destinazione di un'area specifica per il miglioramento

-   Misurabile: quantificare o almeno suggerire un indicatore dello stato di avanzamento

-   Assegnabile: specificare chi lo farà

-   Realistico: indicare i risultati realistici ottenuti, in base alle risorse disponibili

-   Correlazione temporale: specificare quando i risultati possono essere raggiunti

> [!TIP]
> Di seguito è riportato un esempio di KSI pertinente per questo progetto:
> 
> |Tipo  |KSI domanda & criteri  |Modalità di misurazione  |Criteri di successo  |Misurato  |Responsabile  |
> |---------|---------|---------|---------|---------|---------|
> |Uso/adozione|La qualità delle chiamate è uguale o migliore della soluzione precedente|Sondaggio|80% degli utenti concordano o sono fortemente concordi|Dopo l'abilitazione e il trimestrale|Team Information Technology|
> |Uso/adozione|Microsoft Teams ha semplificato il processo di comunicazione|Sondaggio|80% degli utenti concordano o sono fortemente concordi|Dopo l'abilitazione e il trimestrale|Team di gestione delle modifiche|
> |Uso/adozione|Gli utenti usano attivamente la soluzione|Report di Office 365, dashboard qualità chiamata|80% degli utenti sono utenti quotidiani attivi|Quotidiana|Team di gestione delle modifiche|
> |Uso/qualità|La percentuale di chiamate/conferenze non consentite dovrebbe essere minima|Dashboard qualità chiamata|< 5% delle chiamate scadenti per mese|Quotidiana|Team Information Technology|
> |Uso/supporto|So come ottenere supporto tecnico|Sondaggio|90% degli utenti concordano o sono fortemente concordi|Dopo l'abilitazione e il trimestrale|Team di gestione delle modifiche|
> |Uso/supporto|Sono soddisfatto della qualità del supporto tecnico|Sondaggio|80% degli utenti concordano o sono fortemente concordi|Dopo ogni incidente|Team Information Technology|
> |Finanziario|Riduzione dei minuti per i servizi di conferenza legacy|Sistema finanziario|Soddisfare il ROI definito|Basato su ROI|Team di gestione delle modifiche|

È necessario identificare i rischi aziendali nell'ambito di questo esercizio e definire un piano di attenuazione per ogni rischio identificato. Queste informazioni possono essere acquisite in un registro dei rischi.

> [!TIP]
> Il registro dei rischi può essere documentato come l'esempio seguente:
> 
> |Rischio  |Probabilità  |Impatto  |Generale  |Piano di attenuazione  |
> |---------|---------|---------|---------|---------|
> |L'imminente fusione aggiungerà fino a 1.000 persone|Alta|Alta|Alta|<ul><li>Per le società unite, creare un OKR separato che si applica alle proprie fasi di progetto (immaginare, a bordo, valore unità)</li><li>Non includere questi OKRs in OKRs esistente</li></ul>|
> |La portabilità del numero di telefono ritarderà il completamento del progetto|Alta|Alta|Alta|<ul><li>Preparare tutte le informazioni necessarie per supportare il trasferimento del numero di telefono in anticipo (record servizio clienti, dettagli fatturazione, lettera di autorizzazione)</li><li>Regolare la sequenza temporale del progetto per adattare l'esecuzione della conversione del numero di telefono alla data di consegna</li><li>Comunicare l'uso di nuovi numeri di conferenza telefonica con accesso esterno a partecipanti esterni</li><li>Usare numeri di telefono temporanei con la manipolazione dell'ID chiamante</li></ul>|
> |Riprogettazione della rete pianificata|Alta|Media|Media|<ul><li>Prima di implementare teams come piattaforma di comunicazione e collaborazione moderna, eseguire una valutazione della conformità della rete per i siti nell'ambito del progetto</li></ul>|
> |Configurazione SBC|Alta|Alta|Alta|<ul><li>Prima di implementare teams come sostituto per il PBX esistente, verificare che sia possibile soddisfare tutti i requisiti di configurazione di SBC</li><li>Verificare che le risorse di supporto SBC abbiano il set di competenze appropriato per configurare SBC per il routing diretto</li></ul>|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Punti decisionali|<ul><li>Quali sono le informazioni dell'organizzazione&#39;s OKRs e KSIs?</li><li>Quali sono i rischi identificati come rilevanti per l'implementazione di servizi di audioconferenza nell'organizzazione? Quali sono i piani di mitigazione per i rischi identificati?</li><li>Quali sono i rischi identificati come rilevanti per l'implementazione dei piani di chiamata nell'organizzazione? Quali sono i piani di mitigazione per i rischi identificati?</li><li>Quali sono i rischi identificati come rilevanti per l'implementazione del routing diretto nell'organizzazione? Quali sono i piani di mitigazione per i rischi identificati?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Documentare OKRs e KSIs e stabilire il registro dei rischi.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Creare un comitato direttivo

Un comitato direttivo è un gruppo direttivo di principali stakeholder e Project leader che sono stati riuniti per guidare un progetto o un programma verso i risultati aziendali definiti. Il comitato direttivo non è direttamente responsabile del *modo* in cui il progetto viene recapitato, bensì di *quello che* il progetto offre all'azienda.

Ogni progetto richiede una visione concordata e una carta. Per consegnare i risultati desiderati dal progetto, la visione deve essere definita in modo chiaro e deve essere monitorata e mantenuta. Questo diventa la responsabilità del comitato direttivo: guidare le decisioni, consigliare, fornire un controllo strategico, fungere da sostenitori dell'organizzazione per le iniziative del progetto e, se necessario, rimuovere i blocchi.

L'organizzazione deve inserire un pensiero significativo nella formazione del comitato direttivo. Il Comitato deve garantire che il progetto raggiunga gli obiettivi aziendali definiti per la modifica della Guida in tutta l'organizzazione, si incontri periodicamente per discutere l'impulso corrente del progetto e contribuisca a sbloccare gli eventuali ostacoli che si incontrano lungo il modo.

Il Comitato deve definire la sua carta per includere alcuni obiettivi chiave:

-   Mantieni un forte allineamento tra il team di progetto e lo sponsor esecutivo o l'Executive Leadership.

-   Fornisci informazioni sullo stato del progetto allo sponsor esecutivo o alla leadership esecutiva.

-   Consentire allo sponsor esecutivo o al team di dirigenti esecutivi di fornire indicazioni per il progetto e di assicurarne l'allineamento con gli obiettivi aziendali in generale, modificando i piani di progetto, i risultati delle chiavi oggettive (OKRs) e altre attività di progetto.

Il comitato direttivo si riunisce a un intervallo ricorrente per tutta la durata di un progetto per garantire l'allineamento tra la leadership organizzativa e il team di progetto. Questa riunione critica garantisce che la direzione del progetto contenga il supporto completo della leadership e incorpora tutti i feedback forniti dalla leadership nel progetto per guidare il successo. Il Comitato usa queste riunioni per ottenere informazioni sullo stato del progetto e per:

-   Concordare i risultati aziendali che si allineano al business case e per garantire che il progetto stia guidando al recapito di questi risultati.

-   Verificare e approvare il progetto per l'accuratezza e la conformità con il business case.

-   Esaminare e verificare le modifiche apportate al caso aziendale che potrebbero influire su eventuali risultati definiti.

-   Prendere decisioni strategiche per quanto riguarda la priorità dei risultati finali del progetto e approvare i risultati finali intermedi.

-   Identificare, gestire e mitigare le lacune, i rischi e i problemi per i quali è richiesta ulteriore influenza da parte del comitato.

-   Raccogliere il supporto del team Executive sponsor o Executive Leadership per problemi che richiedono l'escalation, la priorità e la risoluzione dei conflitti tra le unità aziendali delle parti interessate. 

-   Fornire un feedback formale e raccomandazioni per dirigenti esecutivi, il Consiglio consultivo per le modifiche o altri stakeholder aziendali e IT, se applicabile.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Punti decisionali|<ul><li>Decidere se è necessario un comitato direttivo per l'organizzazione.</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Identificare i membri del comitato direttivo.</li><li>Pianificare le riunioni del comitato direttivo.</li><li>Preparare le riunioni del comitato direttivo.</li><li>Tenere riunioni del comitato direttivo.</li><li>Agire in base all'input della riunione del comitato direttivo.</li></ul>|

Ulteriori indicazioni dettagliate su come gestire un comitato direttivo appropriato possono essere trovate nella [Guida del comitato direttivo](envision-steering-committee-complete-guide.md).

<!--ENDOFSECTION-->