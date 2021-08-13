---
title: Audioconferenza, piani per chiamate o routing diretto
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/07/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Definizione del successo per la distribuzione di audioconferenze, Sistema telefonico con piani per chiamate o Sistema telefonico routing diretto per l'organizzazione.
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 04cd584be5b6333c579ab8b4685ad917236e660474d9e49150eb0f563670fa6c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320009"
---
# <a name="define-my-success"></a>Definizione del successo

Questo articolo offre una panoramica dei requisiti per la definizione del successo per la distribuzione di audioconferenza, Sistema telefonico con piani per chiamate o Sistema telefonico Direct Routing per l'organizzazione. Definendo correttamente l'aspetto del successo, è possibile misurare i risultati durante l'avanzamento della distribuzione e verificare che i risultati ottenuti siano quelli desiderati.

<!--ENDOFSECTION-->

**Le** audioconferenze forniscono alle organizzazioni ulteriori punti di accesso a qualsiasi riunione (ad hoc o pianificata) consentendo ai partecipanti alla riunione di partecipare tramite una rete PSTN (Public Switched Telephone Network) con accesso esterno tramite telefono fisso tradizionale, PBX (Private Branch Exchange) o telefoni cellulari. Questa opzione è utile quando l'organizzatore o i partecipanti non si trova davanti a un computer o quando le connessioni dati non sono disponibili o non sono troppo inaffidabili per supportare le comunicazioni vocali, ad esempio in un'area remota con copertura di dati mobili spotty o connessi a un servizio Wi-Fi pubblico gratuito con larghezza di banda limitata o quando i partecipanti alla riunione preferiscono accedere alla riunione usando un endpoint di telefonia facilmente accessibile.

Sistema telefonico piani per chiamate ("Piani per **chiamate")** offre alle organizzazioni un modo per modernizzare il proprio luogo di lavoro, consentendo agli utenti di effettuare chiamate telefoniche correlate all'azienda dai propri computer e dispositivi mobili. L'ammodernamento del luogo di lavoro può essere parte di un numero qualsiasi di scenari: un'implementazione di lavoro basata sulle attività, un'importante operazione di ufficio, un aggiornamento dell'ufficio, il ritiro di una soluzione PBX legacy, la conclusione di un contratto di provider di servizi PSTN e così via. Con i Piani per le chiamate, Microsoft facilita la connettività alla rete PSTN.

Sistema telefonico routing diretto **("Routing diretto")** offre alle organizzazioni gli stessi vantaggi elencati sopra per i Piani per chiamate, ad eccezione del fatto che la connettività PSTN è agevolata da un provider di terze parti anziché da Microsoft. In questo modo è possibile eseguire la distribuzione nei paesi in cui i piani per chiamate non sono disponibili o nelle distribuzioni in cui è necessario mantenere un contratto di provider di servizi PSTN esistente o l'interoperabilità con determinati sistemi locali. Un altro scenario da considerare per il routing diretto è l'interoperabilità dei sistemi di telefonia. Mentre gli utenti sono in fase di transizione a Chiamate in Teams, alcuni utenti potrebbero rimanere nei sistemi PBX legacy. Il routing diretto consente a entrambi i casi di utilizzo di coesistere. Il traffico di chiamata tra gli utenti di sistemi legacy e Teams utenti rimangono all'interno dell'organizzazione.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Definire casi d'uso aziendali per audioconferenze, piani per chiamate o routing diretto

Per iniziare, i principali stakeholder del progetto devono definire casi d'uso aziendali che supportano l'implementazione di audioconferenze, piani per chiamate o routing diretto.

I casi d'uso aziendali sono pensati per definire e documentare i risultati aziendali previsti e misurabili e includono quanto segue:

-   Descrizione del processo aziendale corrente

-   Sfide con il processo aziendale esistente

-   Come la tecnologia può servire al superamento di queste problematiche

-   I risultati aziendali previsti e misurabili se queste sfide vengono superate

> [!TIP]
> Di seguito è riportato un esempio di caso di utilizzo aziendale completato per le audioconferenze:
> 
> |         |
> |---------|
> |**Descrizione del processo aziendale corrente**<br>Contoso attualmente si basa sui servizi di conferenza PSTN forniti dal provider di telefonia locale in carica, addebitabile in base ai minuti delle riunioni per le riunioni interne e le riunioni che coinvolgono parti esterne.|
> |**Sfide con il processo aziendale esistente**<br>Contoso spende circa 1 milione di dollari all'anno per l'attuale servizio di conferenza PSTN, con il 75% dei costi sostenuti per le riunioni interne. L'uso degli endpoint di telefonia tradizionali per partecipare alle riunioni ospitate dal servizio di conferenza PSTN non è allineato al piano per l'adozione di Teams come piattaforma moderna di comunicazione e collaborazione.|
> |**Come la tecnologia può superare queste sfide**<br>Con l'adozione di Microsoft Teams come piattaforma moderna di comunicazione e collaborazione, gli utenti interni dovrebbero partecipare principalmente alle riunioni usando i loro PC dotati di cuffie ottimizzate e dispositivi per sale riunioni. Il servizio di audioconferenza sarà disponibile per supportare i partecipanti esterni o per supportare situazioni in cui l'uso dell'audio del PC non è vantaggioso per i partecipanti interni.|
> |**Risultati aziendali previsti, misurabili**<br>Il passaggio a Teams moderna piattaforma di comunicazione e collaborazione, combinata con il servizio di audioconferenza, ridurrà notevolmente i costi per la distribuzione del servizio di conferenza PSTN.|

<br>

> [!TIP]
> Di seguito è riportato un esempio di caso di utilizzo aziendale completato per i piani per chiamate:
> 
> |         |
> |---------|
> |**Descrizione del processo aziendale corrente**<br>La configurazione standard delle aree di lavoro dell'ufficio di Contoso include un telefono desktop per ogni scrivania. A ogni dipendente è stato assegnato un numero di telefono DID (Direct Inward Dialing). I telefoni desktop sono connessi a un sistema PBX e a PSTN tramite un trunk SIP (Session Initiation Protocol). I dipendenti possono effettuare e ricevere chiamate telefoniche solo presso i telefoni desktop assegnati.|
> |**Sfide con il processo aziendale esistente**<br>L'analisi dell'utilizzo dei telefoni desktop mostra che solo il 10% dei telefoni desktop viene usato attivamente, con il resto configurato per inoltrare le chiamate ai telefoni cellulari o per squillare contemporaneamente ai telefoni cellulari. La manutenzione del sistema PBX esistente e dei telefoni desktop associati contribuisce al 20% del costo mensile del servizio di telefonia di Contoso.|
> |**Come la tecnologia può superare queste sfide**<br>Piani per chiamate consentirà al personal computer di un utente di ricevere e effettuare chiamate telefoniche tramite la rete dati sfruttando l'app Microsoft Teams nativa. In questo modo si elimina la necessità di implementare e gestire i telefoni desktop e si apre l'opportunità di rimuovere il sistema PBX esistente, perché il servizio telefonico può essere consegnato tramite cloud tramite la rete senza alcuna dipendenza da un sistema telefonico tradizionale.|
> |**Risultati aziendali previsti, misurabili**<br>La rimozione dei requisiti di manutenzione e la rimozione dei telefoni PBX e desktop legacy offriranno una riduzione del 20% delle spese mensili per i servizi di telefonia. Piani per chiamate semplificherà le aree di lavoro per gli uffici, consentendo a Contoso di espandere le proprie attività stabilendo nuovi uffici con costi di telefonia iniziali minimi.|

<br>

> [!TIP]
> Di seguito è riportato un esempio di caso di utilizzo aziendale completato per il routing diretto:
> 
> |         |
> |---------|
> |**Descrizione del processo aziendale corrente**<br>La configurazione standard delle aree di lavoro dell'ufficio di Contoso include un telefono desktop per ogni scrivania. A ogni dipendente è stato assegnato un numero di telefono DID (Direct Inward Dialing). I telefoni desktop sono connessi a un sistema PBX e a PSTN tramite un trunk SIP (Session Initiation Protocol). I dipendenti possono effettuare e ricevere chiamate telefoniche solo presso i telefoni desktop assegnati.|
> |**Sfide con il processo aziendale esistente**<br>L'analisi dell'utilizzo dei telefoni desktop mostra che solo il 10% dei telefoni desktop viene usato attivamente, con il resto configurato per inoltrare le chiamate ai telefoni cellulari o per squillare contemporaneamente ai telefoni cellulari. La manutenzione del sistema PBX esistente e dei telefoni desktop associati contribuisce al 20% del costo mensile del servizio di telefonia di Contoso.|
> |**Come la tecnologia può superare queste sfide**<br>Il contratto del provider trunk SIP è stato firmato di recente e sarà in essere per tre anni. Il routing diretto consente la connettività PSTN fornita dal provider trunk SIP e consente inoltre al personal computer di un utente di ricevere e effettuare chiamate telefoniche tramite la rete dati sfruttando l'app Microsoft Teams nativa. In questo modo si elimina la necessità di implementare e gestire i telefoni desktop e si apre l'opportunità di rimuovere il sistema PBX esistente, mantenendo un ingombro limitato di SBC (Session Border Controller) locale.|
> |**Risultati aziendali previsti, misurabili**<br>La rimozione dei requisiti di manutenzione e la rimozione dei telefoni PBX e desktop legacy offriranno una riduzione del 20% delle spese mensili per i servizi di telefonia. Il routing diretto semplifica le aree di lavoro per gli uffici, consentendo a Contoso di espandere le proprie operazioni stabilendo nuovi uffici con costi di telefonia anticipata minimi.|

Oltre a definire i casi d'uso aziendali, per impostare i limiti del progetto è consigliabile puntare a una maggiore chiarezza:

-   **Ambito dell'organizzazione:** L'implementazione di audioconferenze, piani per chiamate o routing diretto potrebbe includere l'intera organizzazione o solo specifiche unità aziendali.

-   **Project sequenza temporale:** Sequenza temporale specifica in cui verrà eseguito il progetto.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> |Punti decisionali|<ul><li>Quali sono tutti i casi d'uso aziendali per le audioconferenze che è possibile identificare nell'organizzazione?</li><li>Quali sono tutti i casi d'uso aziendali per i piani di chiamata che è possibile identificare nell'organizzazione?</li><li>Quali sono tutti i casi d'uso aziendali per il routing diretto che è possibile identificare nell'organizzazione?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Documentare tutti i casi d'uso aziendali per le audioconferenze per l'organizzazione.</li><li>Documentare tutti i casi d'uso aziendali per i piani per chiamate per l'organizzazione.</li><li>Documentare tutti i casi d'uso aziendali per il routing diretto per l'organizzazione.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identificare gli stakeholder chiave

I casi d'uso aziendali definiti nel passaggio precedente includono un ambito organizzativo per l'implementazione di audioconferenze, piani per chiamate o instradamento diretto. In base a questo, è possibile completare la matrice completa degli stakeholder per includere le persone giuste da coinvolgere nel progetto.

> [!TIP]
> Di seguito è riportato un esempio di modello di matrice stakeholder che è possibile usare per documentare gli stakeholder del progetto:
> 
> |Ruolo  |Descrizione  |Nome, informazioni di contatto, posizione  |
> |---------|---------|---------|
> |Project Executive Sponsor|<ul><li>Prendere l'autorità finale e la responsabilità per il progetto e la consegna sugli obiettivi del progetto.</li><li>Consente di risolvere i problemi riassegnati dal cliente potenziale Project cliente potenziale.</li><li>Sponsorizzare la comunicazione all'interno dell'azienda sugli obiettivi del progetto.</li><li>Prendere decisioni strategiche chiave.</li><li>Verificare la disponibilità delle risorse necessarie e del preventivo.</li><li>Condurre revisioni trimestrali delle attività (QBR).</li><li>Aumentare il buy-in e il supporto per le campagne di sensibilizzazione.</li><li>Fungere da Project sponsor per l'implementazione del programma.</li></ul>|TBA|
> |Project Cliente potenziale|<ul><li>Gestire e guidare il team di progetto.</li><li>Coordinare i partner e i team di lavoro coinvolti nel progetto.</li><li>È necessario essere in grado di creare e gestire piani di progetto per soddisfare i risultati trimestrali.</li><li>Risolvere i problemi interfunzionale.</li><li>Fornire aggiornamenti regolari agli sponsor del progetto.</li><li>Incorporare gli aspetti dell'adozione nel piano di progetto generale.</li><li>Condurre mensilmente le revisioni aziendali e operative (MBR), contribuire ai QBR.</li></ul>|TBA|
> |Cliente potenziale/architetto della collaborazione|<ul><li>Eseguire la strategia di collaborazione definita dai dirigenti aziendali.</li><li>Analizzare e scegliere prodotti di collaborazione che soddisfino gli obiettivi aziendali per l'azienda.</li><li>Operazioni di progettazione per i prodotti di collaborazione.</li><li>Definire i modelli di funzionamento e supporto.</li><li>Contribuire alle revisioni commerciali mensili e trimestrali.</li></ul>|TBA|
> |Consulente|<ul><li>Essere responsabili dei servizi di configurazione</li><li>Contribuire all'architettura generale della soluzione.</li></ul>|TBA|
> |Project Responsabile|<ul><li>Sviluppare e gestire il piano di progetto.</li><li>Gestire i risultati finali del progetto in linea con il piano di progetto e il preventivo.</li><li>Registrare e gestire i problemi del progetto, incluse le escalation.</li><li>Effettua chiamate di supporto settimanali.</li><li>È possibile creare un collegamento con e fornire aggiornamenti agli sponsor dei dirigenti di progetto.</li><li>Collaborare con l'architetto per definire l'approccio di gestione delle modifiche e i piani di comunicazione.</li></ul>|TBA|
> |Change Management/Adoption Specialist|<ul><li>Fornire input durante la fase di individuazione per i processi di adozione e formazione.</li><li>Partecipare al workshop sulla strategia di adozione.</li><li>Sviluppare e assumersi la responsabilità della strategia di adozione.</li><li>Sviluppare ed eseguire il piano di comunicazione.</li><li>Offrire corsi di formazione agli utenti.</li><li>Raccogliere feedback e condurre sondaggi.</li></ul>|TBA|
> |Cliente potenziale della rete|<ul><li>Fornire input durante la fase di individuazione nella progettazione della rete.</li><li>Partecipare alla pianificazione durante il workshop sulla fase di Envision.</li><li>Coordinare il lavoro del team di rete durante l'esecuzione del progetto.</li></ul>|TBA|
> |Cliente potenziale della sicurezza|<ul><li>Fornire input durante la fase di individuazione per la progettazione e i processi di sicurezza.</li><li>Partecipare alla pianificazione durante il workshop sulla fase di Envision.</li><li>Coordinare il lavoro del team di sicurezza durante l'esecuzione del progetto.</li></ul>|TBA|
> |Cliente potenziale di telefonia|<ul><li>Fornire input durante la fase di individuazione nella progettazione della telefonia.</li><li>Partecipare alla pianificazione durante il workshop sulla fase di Envision.</li><li>Coordinare il lavoro del team di telefonia durante l'esecuzione del progetto.</li></ul>|TBA|
> |Cliente potenziale del desktop|<ul><li>Fornire input durante la fase di individuazione nei client e nel processo di aggiornamento.</li><li>Partecipare alla pianificazione durante il workshop di Envision.</li><li>Coordinare il lavoro del team desktop durante l'esecuzione del progetto.</li></ul>|TBA|
> |Lead del supporto tecnico/help desk|<ul><li>Fornire input durante la fase di individuazione nei modelli operativi e di supporto.</li><li>Partecipare alla pianificazione durante il workshop sulla fase di Envision.</li><li>Partecipare alla pianificazione del modello di supporto.</li><li>Coordinare il lavoro dei team di supporto e delle risorse durante l'esecuzione del progetto.</li></ul>|TBA|
> |Rappresentanti delle business unit|<ul><li>Contribuire alle guide e ai materiali di adozione basati sull'utente.</li><li>Contribuire e rivedere i casi d'uso aziendali.</li></ul>|TBA|
> |Cliente potenziale di distribuzione|<ul><li>Assicurarsi che i prerequisiti di distribuzione siano soddisfatti.</li><li>Coinvolgere le risorse per partecipare alle attività della fase di onboard.</li><li>Partecipare alle riunioni per rivedere e preparare report sullo stato della distribuzione.</li></ul>|TBA|
> |Amministratori IT|<ul><li>Assistenza per la pianificazione e l'esecuzione dei test. Questo ruolo è per i professionisti IT.</li></ul>|TBA|
> |Proprietario del servizio|<ul><li>Sii responsabile del funzionamento del servizio di audioconferenza, piani per chiamate o routing diretto.</li><li>È proprietaria del servizio di audioconferenza, piani per chiamate o routing diretto.</li></ul>|TBA|
> |Campioni di qualità|<ul><li>Migliorare la qualità, l'affidabilità e il feedback degli utenti.</li><li>Identificare le tendenze qualitative e guidare la correzione con i rispettivi team.</li><li>Riferire tramite il comitato direttivo alla direzione.</li><li>Report su qualità, affidabilità e valutazione degli utenti tramite Valuta la mia chiamata e Punteggio net promoter.</li></ul>|TBA|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Punti decisionali|<ul><li>Who ogni ruolo chiave degli stakeholder per l'organizzazione?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Documentare tutti gli stakeholder principali e comunicare le responsabilità e le aspettative del ruolo a ogni singolo utente assegnato.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Definire OKR, INDICATORI KPI e rischi

Una volta assemblati gli stakeholder del progetto, è possibile tradurre i casi d'uso aziendali, l'ambito dell'organizzazione e le sequenze temporali del progetto in obiettivi e risultati chiave (OKR) e le misure di successo del progetto possono essere definite come un elenco di indicatori di successo chiave (KPI).

La piena partecipazione degli stakeholder del progetto alla definizione di OKR e KSI è essenziale per assicurarsi che senta un senso di proprietà e allineare queste misure di successo ai requisiti aziendali dell'organizzazione.

Gli OKR contengono gli obiettivi impostati all'inizio del progetto e si definiscono i risultati chiave misurabili su base trimestrale. I risultati chiave vengono esaminati mensilmente per tenere traccia dello stato del progetto complessivo e, in base allo stato di avanzamento, si modificano i piani trimestrali in base alle esigenze.

> [!TIP]
> Di seguito sono riportati alcuni esempi di okR rilevanti per un'implementazione di audioconferenza:
> <br>
> 
> **Visione: Aumentare la produttività massimizzando Microsoft 365 o Office 365 investimenti**
> 
> |Obiettivi  |Risultati principali  |da fare  |
> |---------|---------|---------|
> |Distribuire audioconferenze Teams entro la fine dell'anno fiscale 2018|FY18Q1: Distribuire audioconferenze in Teams globale|Concezione<ul><li>Creare un piano di successo</li><li>Creare un piano di implementazione tecnica dettagliato</li></ul><p>Onboard<ul><li>Eseguire un piano di successo</li><li>Eseguire un piano di implementazione tecnica</li></ul>|
> |Rimuovere il servizio di conferenza PSTN legacy a livello globale entro la metà dell'anno fiscale 2018|FY18Q2: Rimuovere il servizio di conferenza PSTN legacy a livello globale|Valore Unità<ul><li>Aumentare il coinvolgimento degli utenti e promuovere l'adozione</li><li>Gestire e preparare le modifiche</li><li>Misurare, condividere il successo e scorrere</li>|

<br>

> [!TIP]
> Di seguito sono riportati alcuni esempi di OKR rilevanti per un'implementazione di Piani per chiamate:
> <br>
> 
> **Visione: Aumentare la produttività massimizzando Microsoft 365 o Office 365 investimenti**
> 
> |Obiettivi  |Risultati principali  |da fare  |
> |---------|---------|---------|
> |Distribuire piani per chiamate nelle filiali europee entro la fine dell'anno fiscale 2018|FY18Q3: Distribuire piani per chiamate nell'ufficio di Londra|Concezione<ul><li>Creare un piano di successo</li><li>Creare un piano di implementazione tecnica dettagliato</li></ul><p>Onboard<ul><li>Eseguire un piano di successo</li><li>Eseguire un piano di implementazione tecnica</li></ul>|
> |Rimuovere il PBX legacy nell'ufficio di Londra entro la fine dell'anno fiscale 2018|FY18Q4: Rimuovere il PBX legacy nell'ufficio di Londra|Valore Unità<ul><li>Aumentare il coinvolgimento degli utenti e promuovere l'adozione</li><li>Gestire e preparare le modifiche</li><li>Misurare, condividere il successo e scorrere</li>|
> 
> [!TIP]
> Di seguito sono riportati esempi di OKR rilevanti per un'implementazione di Routing diretto:
> <br>
> 
> **Visione: Aumentare la produttività massimizzando Microsoft 365 o Office 365 investimenti**
> 
> |Obiettivi  |Risultati principali  |da fare  |
> |---------|---------|---------|
> |Distribuire il routing diretto nelle succursali canadesi entro la fine dell'anno fiscale 2018|FY18Q3: Distribuire il routing diretto nell'ufficio di Toronto|Concezione<ul><li>Creare un piano di successo</li><li>Creare un piano di implementazione tecnica dettagliato</li></ul><p>Onboard<ul><li>Eseguire un piano di successo</li><li>Eseguire un piano di implementazione tecnica</li></ul>|
> |Rimuovere il PBX legacy nell'ufficio di Toronto entro la fine dell'anno fiscale 2018|FY18Q4: Rimuovere il PBX legacy nell'ufficio di Toronto|Valore Unità<ul><li>Aumentare il coinvolgimento degli utenti e promuovere l'adozione</li><li>Gestire e preparare le modifiche</li><li>Misurare, condividere il successo e scorrere</li>|

<br>

Gli indicatori KPI misurano la qualità e il successo dei risultati chiave e integrano la natura binaria degli OKR (ottenuti o non raggiunti) con la descrizione dettagliata dei risultati positivi e/o non corretti.

Quando si definiscono gli indicatori KPI, è consigliabile usare criteri "specifici, misurabili, assegnabili, realistici, relativi al tempo" (SMART):

-   Specifico: mirare a un'area specifica per il miglioramento

-   Misurabile: quantificare o almeno suggerire un indicatore di avanzamento

-   Assegnabile: specificare chi lo farà

-   Realistico: specificare quali risultati possono essere realisticamente raggiunti, date le risorse disponibili

-   Tempo: specificare quando è possibile ottenere i risultati

> [!TIP]
> Di seguito è riportato un esempio di KSI rilevante per questo progetto:
> 
> |Tipo  |Criteri di & KSI  |Modalità di misurazione  |Criteri di successo  |Misurato  |Responsabile  |
> |---------|---------|---------|---------|---------|---------|
> |Utilizzo/adozione|La qualità delle chiamate è uguale o superiore alla soluzione precedente|Sondaggio|L'80% degli utenti accetta o concorda con forza|Dopo l'abilitazione e trimestrale|Team information technology|
> |Utilizzo/adozione|Microsoft Teams semplificato il processo di comunicazione|Sondaggio|L'80% degli utenti accetta o concorda con forza|Dopo l'abilitazione e trimestrale|Team di gestione delle modifiche|
> |Utilizzo/adozione|Gli utenti usano attivamente la soluzione|Microsoft 365, Call Quality Dashboard|L'80% degli utenti è attivo ogni giorno|Tutti i giorni|Team di gestione delle modifiche|
> |Utilizzo/qualità|La percentuale di chiamate/conferenze scadenti dovrebbe essere minima|Dashboard qualità delle chiamate|< 5% delle chiamate scadente al mese|Tutti i giorni|Team information technology|
> |Utilizzo/supporto|So come ottenere supporto tecnico|Sondaggio|Il 90% degli utenti concorda o concorda con forza|Dopo l'abilitazione e trimestrale|Team di gestione delle modifiche|
> |Utilizzo/supporto|Sono soddisfatto della qualità del supporto tecnico|Sondaggio|L'80% degli utenti accetta o concorda con forza|Dopo ogni evento imprevisto|Team information technology|
> |Finanziarie|Riduzione dei minuti di conferenza legacy|Sistema finanziario|Soddisfare il ROI definito|In base al ROI|Team di gestione delle modifiche|

È necessario identificare i rischi aziendali nell'ambito di questo esercizio e definire un piano di attenuazione per ogni rischio identificato. Queste informazioni possono essere acquisite in un registro dei rischi.

> [!TIP]
> Il registro dei rischi può essere documentato come nell'esempio seguente:
> 
> |Rischio  |Probabilità  |Impatto  |Nel complesso  |Piano di attenuazione  |
> |---------|---------|---------|---------|---------|
> |La prossima fusione aggiungerà fino a 1.000 persone|Alta|Alta|Alta|<ul><li>Per le società unite, creare una funzione OKR separata che si applica alle proprie fasi di progetto (Envision, Onboard, Drive Value)</li><li>Non includere questi OKR negli OKR esistenti</li></ul>|
> |La portabilità del numero di telefono ritarda il completamento del progetto|Alta|Alta|Alta|<ul><li>Preparare in anticipo tutte le informazioni necessarie per supportare la portabilità del numero di telefono (record del servizio clienti, dettagli di fatturazione, lettera di autorizzazione)</li><li>Regolare la sequenza temporale del progetto per adattare il tempo di consegna dell'esecuzione della portabilità del numero di telefono</li><li>Comunicare l'uso di nuovi numeri di conferenza telefonica con accesso esterno a partecipanti esterni</li><li>Usare numeri di telefono temporanei con la modifica dell'ID chiamante</li></ul>|
> |Riprogettazione pianificata della rete|Alta|Media.|Media.|<ul><li>Prima di implementare Teams come piattaforma moderna di comunicazione e collaborazione, eseguire una valutazione della conformità della rete per i siti nell'ambito del progetto</li></ul>|
> |Configurazione SBC|Alta|Alta|Alta|<ul><li>Prima di implementare Teams in sostituzione del PBX esistente, verificare che sia possibile soddisfare tutti i requisiti di configurazione SBC</li><li>Verificare che le risorse di supporto SBC hanno le competenze appropriate per configurare SBC per il routing diretto</li></ul>|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Punti decisionali|<ul><li>Quali sono gli OKR e gli indicatori KPI&#39;'organizzazione?</li><li>Quali rischi sono stati identificati pertinenti all'implementazione delle audioconferenze nell'organizzazione? Quali sono i piani di attenuazione per i rischi identificati?</li><li>Quali rischi sono stati identificati pertinenti all'implementazione dei Piani per chiamate nell'organizzazione? Quali sono i piani di attenuazione per i rischi identificati?</li><li>Quali rischi sono stati identificati pertinenti all'implementazione del routing diretto nell'organizzazione? Quali sono i piani di attenuazione per i rischi identificati?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Documentare gli OKR e gli indicatori KPI e stabilire il registro dei rischi.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Creare un comitato direttivo

Un comitato direttivo è un gruppo direttivo di stakeholder e project leader chiave che sono stati riuniti per guidare un progetto o un programma verso i risultati aziendali definiti. Il comitato direttivo non è  direttamente responsabile del modo  in cui viene consegnato il progetto, ma piuttosto di ciò che il progetto fornisce all'azienda.

Ogni progetto richiede una visione e una carta concordate. Per ottenere i risultati desiderati dal progetto, la visione deve essere definita in modo chiaro e deve essere monitorata e mantenuta. Questo diventa responsabilità del comitato direttivo: guidare le decisioni, consigliare, fornire supervisione strategica, fungere da sostenitori dell'organizzazione per le iniziative del progetto e, se necessario, rimuovere i blocchi.

L'organizzazione dovrebbe prendere in considerazione in modo significativo la formazione del comitato direttivo. Il comitato deve assicurarsi che il progetto raggiunga gli obiettivi aziendali definiti per guidare il cambiamento in tutta l'organizzazione, incontrarsi periodicamente per discutere dell'attuale polso del progetto e contribuire a sbloccare gli eventuali ostacoli che si verificano lungo il percorso.

Il comitato dovrebbe definire la propria carta per includere alcuni obiettivi chiave:

-   Mantenere un forte allineamento tra il team di progetto e lo sponsor esecutivo o la dirigenza.

-   Fornire informazioni approfondite sullo stato del progetto allo sponsor esecutivo o ai dirigenti.

-   Consentire agli sponsor o ai dirigenti del team dirigenziale di fornire direzione e input al progetto e assicurarsi che sia allineato agli obiettivi aziendali generali, modificando i piani di progetto, i risultati chiave obiettivi (OKR) e altre attività del progetto.

Il comitato direttivo si riunirà a intervalli ricorrenti per tutta la durata di un progetto per garantire l'allineamento tra la leadership dell'organizzazione e il team di progetto. Questa riunione critica assicura che la direzione del progetto abbia il supporto completo della leadership e incorpora nel progetto qualsiasi feedback fornito dalla leadership per guidare il successo. Il comitato usa queste riunioni per ottenere informazioni approfondite sullo stato del progetto e per:

-   Concordare i risultati aziendali che si allineano al caso aziendale e per assicurarsi che il progetto guidi verso la distribuzione di questi risultati.

-   Verificare e approvare il progetto per l'accuratezza e la conformità al caso aziendale.

-   Esaminare e verificare le modifiche apportate al caso aziendale che potrebbero influire sui risultati definiti.

-   Prendere decisioni strategiche relative alla definizione delle priorità dei risultati finali del progetto e approvare i risultati finali provvisori.

-   Identificare, gestire e ridurre le lacune, i rischi e i problemi in cui è necessario un'ulteriore influenza da parte del comitato.

-   Raccogliere il supporto dello sponsor esecutivo o del team dirigenziale per i problemi che richiedono un'escalation, l'assegnazione delle priorità e la risoluzione di eventuali conflitti tra le business unit degli stakeholder. 

-   Fornire feedback e consigli formali ai dirigenti, al comitato consultivo per le modifiche o ad altri stakeholder aziendali e IT, se applicabile.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Punti decisionali|<ul><li>Decidere se è necessario un comitato direttivo per l'organizzazione.</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Identificare i membri del comitato direttivo.</li><li>Pianificare le riunioni del comitato direttivo.</li><li>Prepararsi per le riunioni del comitato direttivo.</li><li>Tenere riunioni del comitato direttivo.</li><li>Intervenire in base all'input della riunione del comitato direttivo.</li></ul>|

Altre indicazioni dettagliate su come gestire un comitato di direzione appropriato sono disponibili nella guida [del comitato direttivo.](envision-steering-committee-complete-guide.md)

<!--ENDOFSECTION-->
