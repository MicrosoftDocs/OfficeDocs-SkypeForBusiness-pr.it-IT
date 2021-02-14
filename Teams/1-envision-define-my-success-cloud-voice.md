---
title: Audioconferenza, piani per chiamate o instradamento diretto
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/07/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Definizione del successo per la distribuzione di Audioconferenze, Sistema telefonico con Piani per chiamate o Instradamento diretto sistema telefonico per l'organizzazione.
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 94430052082d523861ed4a938e0e0b02b70049f9
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610985"
---
# <a name="define-my-success"></a>Definizione del successo

Questo articolo fornisce una panoramica dei requisiti per definire il successo della distribuzione di Audioconferenze, Sistema telefonico con Piani per chiamate o Instradamento diretto sistema telefonico per l'organizzazione. Definendo correttamente l'aspetto del successo, è possibile misurare i risultati man via che si procede con la distribuzione e verificare che i risultati ottenuti siano quelli desiderati.

<!--ENDOFSECTION-->

 I servizi di audioconferenza forniscono alle organizzazioni ulteriori punti di accesso a qualsiasi riunione (ad hoc o pianificata), consentendo ai partecipanti alla riunione di partecipare tramite PSTN (Public Switched Telephone Network) tramite telefono fisso tradizionale, PBX (Private Branch Exchange) o cellulari. È utile quando l'organizzatore o i partecipanti non sono davanti a un computer o quando le connessioni dati non sono disponibili o non sono troppo inaffidabili a supportare le comunicazioni vocali, ad esempio in un'area remota con copertura di dati mobili spotty, o quando sono connessi a un servizio gratuito di Wi-Fi pubblico con larghezza di banda limitata oppure quando i partecipanti alla riunione preferiscono accedere alla riunione usando un endpoint di telefonia prontamente accessibile.

**Sistema telefonico con Piani** per chiamate ("Piani per chiamate") offre alle organizzazioni un modo per modernizzare il proprio luogo di lavoro consentendo agli utenti di effettuare chiamate telefoniche aziendali dal proprio computer e dispositivo mobile. L'modernizzazione del luogo di lavoro può far parte di un numero qualsiasi di scenari: implementazione del lavoro basata su attività, trasferta di un ufficio principale, aggiornamento della configurazione dell'ufficio, ritiro di una soluzione PBX legacy, conclusione di un contratto di un provider di servizi PSTN e così via. Con i Piani per chiamate, Microsoft facilita la connettività alla rete PSTN.

L'instradamento diretto del sistema telefonico **("Routing diretto")** offre alle organizzazioni gli stessi vantaggi elencati sopra per i Piani per chiamate, tranne per il fatto che la connettività PSTN è semplificata da un provider di terze parti anziché da Microsoft. Ciò consente la distribuzione nei paesi in cui non sono disponibili piani per chiamate o in distribuzioni in cui è necessario mantenere un contratto esistente di provider di servizi PSTN o interoperabilità con determinati sistemi locali. Uno scenario aggiuntivo da considerare per il routing diretto è l'interoperabilità del sistema di telefonia. Mentre gli utenti stanno effettuando la transizione alle chiamate in Teams, alcuni utenti potrebbero rimanere nei PBX legacy. Il routing diretto consente a entrambi i casi di utilizzo di coesistere. Il traffico delle chiamate tra gli utenti dei sistemi legacy e gli utenti di Teams rimane all'interno dell'organizzazione.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Definire casi d'uso aziendali per audioconferenze, piani per chiamate o instradamento diretto

Per iniziare, i principali stakeholder del progetto devono definire casi d'uso aziendali che supportino l'implementazione di Audioconferenze, Piani per chiamate o Instradamento diretto.

I casi d'uso aziendali sono pensati per definire e documentare i risultati di business previsti e misurabili e includono:

-   Descrizione del processo aziendale corrente

-   Sfide con l'esistente processo aziendale

-   Come la tecnologia può servire al superamento di queste problematiche

-   I risultati di business previsti e misurabili se queste sfide vengono superate

> [!TIP]
> Di seguito è riportato un esempio completo di utilizzo aziendale per i servizi di audioconferenza:
> 
> |         |
> |---------|
> |**Descrizione del processo aziendale corrente**<br>Attualmente Contoso si basa sui servizi di conferenza PSTN forniti dal provider di telefonia locale in carica, addebitabile tramite i minuti delle riunioni per le riunioni interne e le riunioni che coinvolgono parti esterne.|
> |**Sfide con il processo aziendale esistente**<br>Contoso spende circa un milione di usd all'anno per l'attuale servizio di conferenza PSTN, con il 75% del costo sostenuto per le riunioni interne. L'uso degli endpoint di telefonia tradizionali per partecipare alle riunioni ospitate dal servizio di conferenza PSTN non è allineato al piano per l'adozione di Teams come piattaforma di comunicazione e collaborazione moderna.|
> |**In che modo la tecnologia può superare queste sfide?**<br>Con l'adozione di Microsoft Teams come piattaforma moderna di comunicazione e collaborazione, gli utenti interni dovrebbero partecipare principalmente alle riunioni usando i loro PC dotati di cuffie ottimizzate e dispositivi per sale riunioni. Il servizio di audioconferenza sarà disponibile per supportare i partecipanti esterni o per supportare situazioni in cui l'uso dell'audio del PC non è vantaggioso per i partecipanti interni.|
> |**Risultati aziendali previsti, misurabili e di business**<br>Il passaggio a Teams come piattaforma moderna di comunicazione e collaborazione, combinata con il servizio di audioconferenza, ridurrà notevolmente i costi per la distribuzione del servizio di conferenza PSTN.|

<br>

> [!TIP]
> Di seguito è riportato un esempio completo di utilizzo aziendale completo per i Piani per chiamate:
> 
> |         |
> |---------|
> |**Descrizione del processo aziendale corrente**<br>La configurazione standard delle aree di lavoro di Office di Contoso include un telefono da scrivania per ogni scrivania. A ogni dipendente è stato assegnato un numero di telefono di composizione diretta verso l'interno (DID). I telefoni da scrivania sono connessi a un sistema PBX e a PSTN tramite un trunk SIP (Session Initiation Protocol). I dipendenti possono effettuare e ricevere chiamate solo sui telefoni da scrivania assegnati.|
> |**Sfide con il processo aziendale esistente**<br>L'analisi dell'utilizzo dei telefoni da scrivania mostra che solo il 10% dei telefoni da scrivania viene utilizzato attivamente, con il resto configurato per inoltrare le chiamate ai telefoni cellulari o per chiamarsi contemporaneamente ai cellulari. Mantenere il sistema PBX esistente e i telefoni da scrivania associati contribuisce al 20% del costo mensile del servizio di telefonia di Contoso.|
> |**In che modo la tecnologia può superare queste sfide?**<br>I Piani per chiamate consentono al computer personale di un utente di ricevere ed effettuare chiamate telefoniche tramite la rete dati, sfruttando l'app nativa Microsoft Teams. In questo modo si elimina l'esigenza di implementare e mantenere i telefoni da scrivania e si apre l'opportunità di rimuovere il sistema PBX esistente, perché il servizio telefonico può essere consegnato tramite il cloud tramite la rete, senza dipendenza da un sistema telefonico tradizionale.|
> |**Risultati aziendali previsti, misurabili e di business**<br>La rimozione dei requisiti di manutenzione e la rimozione dei telefoni PBX legacy e dei telefoni da scrivania offrono una riduzione del 20% delle spese mensili per il servizio di telefonia. I Piani per chiamate semplificano le aree di lavoro per gli uffici, consentendo a Contoso di espandere le attività stabilendo nuovi uffici con costi di telefonia iniziale minimi.|

<br>

> [!TIP]
> Di seguito è riportato un esempio completo di caso d'uso aziendale completo per il routing diretto:
> 
> |         |
> |---------|
> |**Descrizione del processo aziendale corrente**<br>La configurazione standard delle aree di lavoro di Office di Contoso include un telefono da scrivania per ogni scrivania. A ogni dipendente è stato assegnato un numero di telefono di composizione diretta verso l'interno (DID). I telefoni da scrivania sono connessi a un sistema PBX e a PSTN tramite un trunk SIP (Session Initiation Protocol). I dipendenti possono effettuare e ricevere chiamate solo sui telefoni da scrivania assegnati.|
> |**Sfide con il processo aziendale esistente**<br>L'analisi dell'utilizzo dei telefoni da scrivania mostra che solo il 10% dei telefoni da scrivania viene utilizzato attivamente, con il resto configurato per inoltrare le chiamate ai telefoni cellulari o per chiamarsi contemporaneamente ai cellulari. Mantenere il sistema PBX esistente e i telefoni da scrivania associati contribuisce al 20% del costo mensile del servizio di telefonia di Contoso.|
> |**In che modo la tecnologia può superare queste sfide?**<br>Il contratto del provider di trunk SIP è stato firmato di recente e sarà in essere per tre anni. Il routing diretto consente la connettività PSTN fornita dal provider di trunk SIP e consente inoltre al personal computer di un utente di ricevere ed effettuare chiamate telefoniche tramite la rete dati sfruttando l'app nativa Microsoft Teams. In questo modo si elimina la necessità di implementare e mantenere i telefoni da scrivania e si apre l'opportunità di rimuovere il sistema PBX esistente, mantenendo un ingombro limitato di session border controller (SBC) locale.|
> |**Risultati aziendali previsti, misurabili e di business**<br>La rimozione dei requisiti di manutenzione e la rimozione dei telefoni PBX legacy e dei telefoni da scrivania offrono una riduzione del 20% delle spese mensili per il servizio di telefonia. L'instradamento diretto semplifica le aree di lavoro per gli uffici, consentendo a Contoso di espandere le proprie operazioni stabilendo nuovi uffici con costi di telefonia iniziale minimi.|

Oltre a definire casi d'uso aziendali, per definire i limiti del progetto è consigliabile fare chiarezza:

-   **Ambito dell'organizzazione:** L'implementazione di Audioconferenza, Piani per chiamate o Instradamento diretto potrebbe includere l'intera organizzazione o solo specifiche unità aziendali.

-   **Sequenza temporale del progetto:** La sequenza temporale specifica per l'esecuzione del progetto.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> |Punti decisionali|<ul><li>Quali sono tutti i casi d'uso aziendali per i servizi di audioconferenza che è possibile identificare nell'organizzazione?</li><li>Quali sono tutti i casi d'uso aziendali per i Piani per chiamate che è possibile identificare nell'organizzazione?</li><li>Quali sono tutti i casi d'uso aziendali per il routing diretto che è possibile identificare nell'organizzazione?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Documentare tutti i casi d'uso aziendali per le audioconferenze per l'organizzazione.</li><li>Documentare tutti i casi d'uso aziendali per i Piani per chiamate dell'organizzazione.</li><li>Documentare tutti i casi d'uso aziendali per il routing diretto per l'organizzazione.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identificare gli stakeholder chiave

I casi d'uso aziendali definiti nel passaggio precedente includono un ambito organizzativo per l'implementazione di Audioconferenze, Piani per chiamate o Instradamento diretto. In base a questo, è possibile completare la matrice completa degli stakeholder per includere le persone giuste da coinvolgere nel progetto.

> [!TIP]
> Di seguito è riportato un esempio di modello di matrice degli stakeholder che è possibile usare per documentare le parti interessate al progetto:
> 
> |Ruolo  |Descrizione  |Nome, informazioni di contatto, posizione  |
> |---------|---------|---------|
> |Project Executive Sponsor|<ul><li>È necessario assumere l'autorità e la responsabilità per il progetto e la consegna degli obiettivi del progetto.</li><li>Consente di risolvere i problemi inoltrati dal cliente potenziale.</li><li>Sponsorizzare la comunicazione all'interno dell'azienda sugli obiettivi del progetto.</li><li>Prendere decisioni strategiche importanti.</li><li>Verificare la disponibilità delle risorse necessarie e il preventivo.</li><li>Condurre revisioni aziendali trimestrali (QBR).</li><li>Aumentare l'acquisto e il supporto delle campagne di consapevolezza.</li><li>Fungere da Project Sponsor per l'implementazione del programma.</li></ul>|TBA|
> |Cliente potenziale del progetto|<ul><li>Gestire e condurre il team di progetto.</li><li>Coordinare partner e team di lavoro coinvolti nel progetto.</li><li>È necessario gestire e creare piani di progetto per soddisfare i risultati principali trimestrali.</li><li>Risolvere i problemi interfunzionale.</li><li>Fornire aggiornamenti regolari agli sponsor del progetto.</li><li>Incorporare gli aspetti di adozione nel piano di progetto generale.</li><li>È possibile condurre recensioni aziendali e operative mensili (MBRs), contribuire ai QBR.</li></ul>|TBA|
> |Lead/Architect per la collaborazione|<ul><li>Si può scegliere la strategia di collaborazione definita dai dirigenti aziendali.</li><li>Analizzare e scegliere prodotti per la collaborazione che soddisfano gli obiettivi aziendali dell'azienda.</li><li>Operazioni di progettazione per i prodotti di collaborazione.</li><li>Definire modelli di operazioni e supporto.</li><li>Collabora alle recensioni aziendali mensili e trimestrali.</li></ul>|TBA|
> |Consulente|<ul><li>Essere responsabili dei servizi di configurazione</li><li>Contribuire all'architettura complessiva della soluzione.</li></ul>|TBA|
> |Project Manager|<ul><li>Sviluppare e gestire il piano di progetto.</li><li>Gestire i risultati finali del progetto in linea con il piano di progetto e il preventivo.</li><li>Registrare e gestire i problemi del progetto, incluse le riassegnazioni.</li><li>Effettua chiamate in piedi settimanali.</li><li>Consente di creare e fornire aggiornamenti agli sponsor della direzione del progetto.</li><li>Collaborare con l'architetto per definire l'approccio e i piani di comunicazione per la gestione delle modifiche.</li></ul>|TBA|
> |Esperto nella gestione delle modifiche e nell'adozione|<ul><li>Fornire input durante la fase di individuazione in processi di adozione e formazione.</li><li>Partecipare al workshop sulla strategia di adozione.</li><li>Sviluppare e assumersi la responsabilità della strategia di adozione.</li><li>Sviluppare ed eseguire il piano di comunicazione.</li><li>Offrire corsi di formazione agli utenti.</li><li>Raccogliere feedback ed eseguire sondaggi.</li></ul>|TBA|
> |Cliente potenziale rete|<ul><li>Fornire input durante la fase di individuazione nella progettazione di rete.</li><li>Partecipare alla pianificazione durante il corso di preparazione alla fase di pianificazione.</li><li>Coordinare il lavoro del team di rete durante l'esecuzione del progetto.</li></ul>|TBA|
> |Cliente potenziale della sicurezza|<ul><li>Fornire input durante la fase di individuazione nella progettazione e nei processi di sicurezza.</li><li>Partecipare alla pianificazione durante il corso di preparazione alla fase di pianificazione.</li><li>Coordinare il lavoro del team di sicurezza durante l'esecuzione del progetto.</li></ul>|TBA|
> |Cliente potenziale telefonia|<ul><li>Fornire input durante la fase di individuazione nella progettazione della telefonia.</li><li>Partecipare alla pianificazione durante il corso di preparazione alla fase di pianificazione.</li><li>Coordinare il lavoro del team di telefonia durante l'esecuzione del progetto.</li></ul>|TBA|
> |Cliente potenziale desktop|<ul><li>Fornire input durante la fase di individuazione nei client e nel processo di aggiornamento.</li><li>Partecipare alla pianificazione durante il workshop Envision.</li><li>Coordinare il lavoro del team desktop durante l'esecuzione del progetto.</li></ul>|TBA|
> |Cliente potenziale del supporto tecnico/help desk|<ul><li>Fornire input durante la fase di individuazione in modelli operativi e di supporto.</li><li>Partecipare alla pianificazione durante il corso di preparazione alla fase di pianificazione.</li><li>Partecipare alla pianificazione del modello di supporto.</li><li>Coordinare il lavoro dei team di supporto e delle risorse durante l'esecuzione del progetto.</li></ul>|TBA|
> |Rappresentanti dell'unità commerciale|<ul><li>Contribuire alle guide all'adozione e ai materiali basati sull'utente.</li><li>Collaborare e rivedere casi d'uso aziendali.</li></ul>|TBA|
> |Cliente potenziale distribuzione|<ul><li>Assicurarsi che siano soddisfatti i prerequisiti di distribuzione.</li><li>Coinvolgere le risorse da coinvolgere nelle attività della fase di onboard.</li><li>Partecipare alle riunioni per rivedere e preparare report sullo stato della distribuzione.</li></ul>|TBA|
> |Amministratori IT|<ul><li>Assistenza per la pianificazione e l'esecuzione dei test. Questo ruolo è per i professionisti IT.</li></ul>|TBA|
> |Proprietario del servizio|<ul><li>Sii responsabile dell'operazione dei servizi di audioconferenza, piani per chiamate o servizi di instradamento diretto.</li><li>Proprietà del servizio audioconferenza, piani per chiamate o instradamento diretto.</li></ul>|TBA|
> |Campioni della qualità|<ul><li>Qualità delle unità, affidabilità e feedback degli utenti.</li><li>Identificare le tendenze di qualità e correggere le unità con i rispettivi team.</li><li>Riporta alla leadership il comitato che mi ha fatto tornare.</li><li>Report su qualità, affidabilità e valutazione degli utenti tramite Valuta chiamata e Punteggio Net Promoter.</li></ul>|TBA|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Punti decisionali|<ul><li>Chi ricoderà ogni ruolo chiave degli stakeholder per l'organizzazione?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Documentare tutti gli stakeholder principali e comunicare le responsabilità e le aspettative del ruolo a ogni singolo utente assegnato.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Definire OKR, indicatori KPI e rischi

Dopo l'assemblaggio delle parti interessate al progetto, è possibile tradurre casi d'uso aziendali, ambito organizzativo e tempistiche del progetto in obiettivi e risultati chiave (OKR) e le misure del successo del progetto possono essere definite come un elenco di indicatori di successo chiave (KPI).

La partecipazione completa delle parti interessate al progetto alla definizione di OKRs e indicatori KPI è essenziale per contribuire a far sì che senta un senso di proprietà e allinea le misure di successo ai requisiti aziendali dell'organizzazione.

Le ok contengono gli obiettivi impostati all'inizio del progetto e vengono definiti i risultati chiave misurabili su base trimestrale. Rivedere mensilmente i risultati principali per tenere traccia dello stato dell'intero progetto e, in base all'avanzamento, modificare i piani trimestrali in base alle esigenze.

> [!TIP]
> Di seguito sono riportati alcuni esempi di okrs rilevanti per un'implementazione di audioconferenza:
> <br>
> 
> **Vista: Aumentare la produttività ottimizzando gli investimenti in Microsoft 365 o Office 365**
> 
> |Obiettivi  |Risultati principali  |da fare  |
> |---------|---------|---------|
> |Distribuire le audioconferenze in Teams entro la fine dell'anno fiscale 2018|FY18Q1: Distribuire le audioconferenze in Teams a livello globale|Concezione<ul><li>Creare un piano di successo</li><li>Creare un piano dettagliato di implementazione tecnica</li></ul><p>Onboard<ul><li>Eseguire un piano di successo</li><li>Eseguire un piano di implementazione tecnica</li></ul>|
> |Rimuovere il servizio di conferenza PSTN legacy a livello globale entro la metà dell'anno fiscale 2018|FY18Q2: Rimuovere il servizio di conferenza PSTN legacy a livello globale|Valore Unità<ul><li>Aumentare il coinvolgimento degli utenti e guidare l'adozione</li><li>Gestire e preparare le modifiche</li><li>Misurare, condividere il successo e scorrere</li>|

<br>

> [!TIP]
> Di seguito sono riportati alcuni esempi di OKRs rilevanti per l'implementazione di piani per chiamate:
> <br>
> 
> **Vista: Aumentare la produttività ottimizzando gli investimenti in Microsoft 365 o Office 365**
> 
> |Obiettivi  |Risultati principali  |da fare  |
> |---------|---------|---------|
> |Distribuire i piani per chiamate nelle succursali europee entro la fine dell'anno fiscale 2018|FY18Q3: Distribuire piani per chiamate nell'ufficio londinese|Concezione<ul><li>Creare un piano di successo</li><li>Creare un piano dettagliato di implementazione tecnica</li></ul><p>Onboard<ul><li>Eseguire un piano di successo</li><li>Eseguire un piano di implementazione tecnica</li></ul>|
> |Rimuovere pbx legacy nell'ufficio di Londra entro la fine dell'anno fiscale 2018|FY18Q4: Rimuovere pbx legacy nell'ufficio londinese|Valore Unità<ul><li>Aumentare il coinvolgimento degli utenti e guidare l'adozione</li><li>Gestire e preparare le modifiche</li><li>Misurare, condividere il successo e scorrere</li>|
> 
> [!TIP]
> Di seguito sono riportati alcuni esempi di okRs rilevanti per un'implementazione di routing diretto:
> <br>
> 
> **Vista: Aumentare la produttività ottimizzando gli investimenti in Microsoft 365 o Office 365**
> 
> |Obiettivi  |Risultati principali  |da fare  |
> |---------|---------|---------|
> |Distribuire il routing diretto nelle succursali canadesi entro la fine dell'anno fiscale 2018|FY18Q3: Distribuire il routing diretto nell'ufficio di Toronto|Concezione<ul><li>Creare un piano di successo</li><li>Creare un piano dettagliato di implementazione tecnica</li></ul><p>Onboard<ul><li>Eseguire un piano di successo</li><li>Eseguire un piano di implementazione tecnica</li></ul>|
> |Rimuovere il sistema PBX legacy nell'ufficio di Toronto entro la fine dell'anno fiscale 2018|FY18Q4: Rimuovere il SISTEMA PBX legacy nell'ufficio di Toronto|Valore Unità<ul><li>Aumentare il coinvolgimento degli utenti e guidare l'adozione</li><li>Gestire e preparare le modifiche</li><li>Misurare, condividere il successo e scorrere</li>|

<br>

Gli indicatori KPI misurano la qualità e il successo dei risultati principali e integrano la natura binaria delle okRs (ottenute o non ottenute) indicando nel dettaglio risultati positivi e/o non ottimali.

Quando si definiscono gli indicatori KPI, è consigliabile usare criteri "specifici, misurabili, assegnabili, realistici, correlati al tempo" (SMART):

-   Specifico: obiettivo di un'area specifica per il miglioramento

-   Misurabile: quantificare, o almeno suggerire un indicatore di avanzamento

-   Assegnabile: specificare chi dovrà eseguire l'operazione

-   Realistico: specificare quali risultati possono realisticamente essere raggiunti, considerando le risorse disponibili

-   Data/ora: specificare quando è possibile ottenere i risultati

> [!TIP]
> Di seguito è riportato un esempio di KSI pertinente per il progetto:
> 
> |Tipo  |Criteri di & KSI  |Misura  |Criteri di successo  |Misurata  |Responsabile  |
> |---------|---------|---------|---------|---------|---------|
> |Utilizzo/adozione|La qualità delle chiamate è uguale o migliore della soluzione precedente|Sondaggio|L'80% degli utenti è d'accordo o pienamente d'accordo|Dopo l'abilitazione e trimestrale|Team di Information Technology|
> |Utilizzo/adozione|Microsoft Teams ha reso più semplice il processo di comunicazione|Sondaggio|L'80% degli utenti è d'accordo o pienamente d'accordo|Dopo l'abilitazione e trimestrale|Team di gestione delle modifiche|
> |Utilizzo/adozione|Gli utenti usano attivamente la soluzione|Report di Microsoft 365, Call Quality Dashboard|L'80% degli utenti è attivo ogni giorno|Ogni giorno|Team di gestione delle modifiche|
> |Utilizzo/qualità|La percentuale di chiamate/conferenze di qualità scarsa dovrebbe essere minima|Dashboard qualità delle chiamate|< 5% delle chiamate di qualità scarsa al mese|Ogni giorno|Team di Information Technology|
> |Utilizzo/supporto|Come ottenere supporto tecnico|Sondaggio|Il 90% degli utenti è d'accordo o pienamente d'accordo|Dopo l'abilitazione e trimestrale|Team di gestione delle modifiche|
> |Utilizzo/supporto|Sono soddisfatto della qualità del supporto tecnico|Sondaggio|L'80% degli utenti è d'accordo o pienamente d'accordo|Dopo ogni incidente|Team di Information Technology|
> |Finanziarie|Riduzione dei minuti di conferenze legacy|Sistema finanziario|Informazioni sul ROI definito|In base al ROI|Team di gestione delle modifiche|

È necessario identificare i rischi aziendali nell'ambito di questo esercizio e definire un piano di attenuazione per ogni rischio identificato. Queste informazioni possono essere acquisite in una registrazione dei rischi.

> [!TIP]
> Il registro dei rischi può essere documentato come nell'esempio seguente:
> 
> |Rischio  |Probabilità  |Impatto  |Generale  |Piano di attenuazione  |
> |---------|---------|---------|---------|---------|
> |La fusione imminente aggiungererà fino a 1.000 persone|Alta|Alta|Alta|<ul><li>Per le società unite, creare un OKR separato da applicare alle proprie fasi di progetto (Envision, Onboard, Drive Value)</li><li>Non includere questi okRs negli OKRs esistenti</li></ul>|
> |La portabilità del numero di telefono ritarda il completamento del progetto|Alta|Alta|Alta|<ul><li>Preparare in anticipo tutte le informazioni necessarie per supportare la portabilità del numero di telefono (record del servizio clienti, dettagli di fatturazione, lettera di autorizzazione)</li><li>Regolare la sequenza temporale del progetto in modo da adattare il tempo di consegna dell'esecuzione della portabilità del numero di telefono</li><li>Comunicare l'uso di nuovi numeri di conferenza telefonica con accesso esterno a partecipanti esterni</li><li>Usare numeri di telefono temporanei con la modifica dell'ID chiamante</li></ul>|
> |Rete riprogettata pianificata|Alta|Media.|Media.|<ul><li>Prima di implementare Teams come piattaforma moderna di comunicazione e collaborazione, condurre una valutazione della conformità della rete per i siti nell'ambito del progetto</li></ul>|
> |Configurazione SBC|Alta|Alta|Alta|<ul><li>Prima di implementare Teams in sostituzione del PBX esistente, verifica che tu sia in grado di soddisfare tutti i requisiti di configurazione SBC</li><li>Verificare che le risorse di supporto SBC abbia il set di competenze appropriato per configurare SBC per il routing diretto</li></ul>|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Punti decisionali|<ul><li>Quali sono le&#39;e gli indicatori KPI dell'organizzazione?</li><li>Quali rischi hai identificato pertinenti all'implementazione delle audioconferenze nella tua organizzazione? Quali sono i piani di attenuazione per i rischi identificati?</li><li>Quali rischi hai individuato rilevanti per l'implementazione dei Piani per chiamate nella tua organizzazione? Quali sono i piani di attenuazione per i rischi identificati?</li><li>Quali rischi sono stati identificati rilevanti per l'implementazione del routing diretto nell'organizzazione? Quali sono i piani di attenuazione per i rischi identificati?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Documentare gli OKR e gli indicatori KPI e definire i rischi registrati.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Stabilire un comitato competente

Un comitato competente è un gruppo di governanti di stakeholder e responsabili di progetto che sono stati riuniti per guidare un progetto o un programma verso i risultati di business definiti. Il comitato competente non è  direttamente responsabile della consegna  del progetto, bensì di ciò che il progetto offre all'azienda.

Ogni progetto richiede una visione concordata e uno statuto. Per ottenere i risultati desiderati dal progetto, la visione deve essere definita in modo chiaro e deve essere monitorata e mantenuta. Questo diventa la responsabilità del comitato competente: guidare le decisioni, consigliare, fornire la supervisione strategica, fungere da sostenitori dell'organizzazione per le iniziative del progetto e, se necessario, rimuovere i blocchi.

L'organizzazione dovrebbe pensare in modo significativo alla formazione del comitato competente. Il comitato deve assicurarsi che il progetto raggiunga gli obiettivi aziendali definiti per guidare il cambiamento in tutta l'organizzazione, incontrarsi periodicamente per discutere del momento attuale del progetto e sbloccare eventuali ostacoli incontrati durante il percorso.

Il comitato dovrebbe definire il suo statuto per includere alcuni obiettivi principali:

-   Mantenere un forte allineamento tra il team di progetto e lo sponsor della direzione o la dirigenza.

-   Fornire informazioni sullo stato del progetto allo sponsor o ai dirigenti della direzione.

-   Consentire lo sponsor o il team di leadership della dirigenza di fornire la direzione e l'input per il progetto e assicurarsi che sia allineato con l'archiviazione generale degli obiettivi aziendali, modificando i piani di progetto, i risultati chiave obiettivi (OKRs) e altre attività di progetto.

Il comitato competente si incontra a intervalli ricorrenti per tutta la durata di un progetto per garantire l'allineamento tra la leadership dell'organizzazione e il team di progetto. Questa riunione critica garantisce che la direzione del progetto abbia il pieno supporto della leadership e incorpori nel progetto il feedback dei dirigenti per guidare il successo. Il comitato usa queste riunioni per ottenere informazioni approfondite sullo stato del progetto e per:

-   Concordare i risultati di business allineati al caso commerciale e assicurarsi che il progetto sia in linea con la consegna di tali risultati.

-   Controllare e approvare il progetto per l'accuratezza e la conformità al caso aziendale.

-   Esaminare e verificare le modifiche apportate al caso commerciale che potrebbero influire su eventuali risultati definiti.

-   Prendere decisioni strategiche relative alla definizione delle priorità dei risultati finali del progetto e approvare i risultati finali provvisori.

-   Identificare, gestire e alleviare lacune, rischi e problemi in cui è necessario un ulteriore parere del comitato.

-   Raccogliere il supporto dello sponsor della dirigenza o della leadership della dirigenza per problemi che richiedono l'escalation, l'assegnazione di priorità e la risoluzione di eventuali conflitti tra le business unit degli stakeholder. 

-   Fornire feedback e suggerimenti formali alla leadership della dirigenza, al consiglio di amministrazione per il cambiamento o ad altre parti interessate aziendali e IT, se applicabile.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Punti decisionali|<ul><li>Decidere se è necessario un comitato competente per l'organizzazione.</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Passaggi successivi|<ul><li>Identificare i membri del comitato competente.</li><li>Pianifica riunioni del comitato.</li><li>Prepararsi per le riunioni del comitato.</li><li>Sono in corso riunioni del comitato.</li><li>Intervenire in base alla rimozione del contributo della riunione del comitato.</li></ul>|

Altre indicazioni dettagliate su come gestire un comitato competente sono disponibili nella guida del [comitato competente.](envision-steering-committee-complete-guide.md)

<!--ENDOFSECTION-->
