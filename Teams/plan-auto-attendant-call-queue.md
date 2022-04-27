---
title: Pianificare Teams operatori automatici e code di chiamata
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Informazioni sugli operatori automatici e le code di chiamata e su come usarli per aiutare i chiamanti a spostarsi in un sistema di menu per raggiungere persone o reparti dell'organizzazione.
ms.openlocfilehash: 76755e722abdcde6673baac42681697165921aca
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059277"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Pianificare Teams operatori automatici e code di chiamata

Gli operatori automatici consentono di impostare le opzioni di menu per instradare le chiamate in base all'input del chiamante. Opzioni di menu, ad esempio "Per le vendite, premere 1.  Per Servizi premere 2", per un operatore automatico consentire a un'organizzazione di fornire una serie di scelte che guidano rapidamente i chiamanti verso la loro destinazione, senza affidarsi a un operatore umano per gestire le chiamate in arrivo.

Le code di chiamata sono aree di attesa per i chiamanti. Per le situazioni in cui i chiamanti devono raggiungere una persona con una particolare specialità, ad esempio le vendite o il servizio, invece di una persona specifica, è possibile usare le code di chiamata per connettere i chiamanti al gruppo di agenti che possono assisterli. I chiamanti vengono messi in attesa finché un agente assegnato alla coda non è disponibile per la chiamata.

Usati insieme, gli operatori automatici e le code di chiamata possono facilmente instradare i chiamanti alla persona o al reparto appropriato dell'organizzazione.

## <a name="auto-attendants"></a>Operatori automatici

Lo scopo principale di un operatore automatico è quello di indirizzare un chiamante a una persona o reparto appropriato in base all'input del chiamante alle opzioni di menu fornite. I chiamanti possono essere indirizzati a persone specifiche all'interno dell'organizzazione, a code di chiamata in cui aspettano di parlare con il successivo agente disponibile o alla segreteria telefonica. È possibile specificare opzioni di instradamento delle chiamate diverse per orario di ufficio, orario di chiusura e festività.

I prompt dei menu possono essere creati usando la sintesi vocale (prompt generati dal sistema) o caricando un file audio registrato. Il riconoscimento vocale accetta comandi vocali per la navigazione in vivavoce, ma le persone che chiamano possono anche usare la tastiera del telefono per spostarsi tra i menu.

Ogni operatore automatico ha una lingua e un fuso orario specifici. Se fai affari in più lingue o in più parti del mondo, puoi creare tutti gli operatori automatici necessari per ospitare i chiamanti.

Per ogni operatore automatico, puoi configurare un operatore. Sebbene sia possibile configurare le chiamate degli operatori per il trasferimento a varie destinazioni, la funzionalità operatore è progettata per consentire ai chiamanti di parlare con una persona specifica dell'organizzazione che può aiutarla.

Gli operatori automatici possono essere configurati in modo da consentire ai chiamanti di eseguire ricerche nella directory dell'organizzazione, sia per nome che per numero di interno. All'interno di un operatore automatico, puoi specificare chi è disponibile per la ricerca in directory scegliendo i gruppi di utenti da includere o escludere. Questo ambito è noto come *ambito di chiamata*.

I chiamanti possono raggiungere un operatore automatico sia tramite numero di telefono diretto, se configurato, sia tramite reindirizzamento da un altro operatore automatico o da una coda di chiamata.

## <a name="call-queues"></a>Code di chiamata

Una coda di chiamata è analoga a una sala d'attesa in un edificio fisico. I chiamanti aspettano in attesa mentre le chiamate vengono instradate agli agenti in coda. Le code di chiamata vengono in genere usate per le funzioni di vendita e di servizio. Tuttavia, le code di chiamata possono essere utilizzate per qualsiasi situazione in cui il numero di chiamate supera la capacità interna, ad esempio un addetto alla reception in una struttura affollata.

Le code di chiamata consentono il routing specifico delle chiamate nei casi in cui il numero totale di chiamanti in coda o il tempo di attesa supera i limiti specificati. Le chiamate possono essere indirizzate a persone specifiche, messaggi vocali, altre code di chiamata o operatori automatici.

Come gli operatori automatici, le code di chiamata hanno ciascuna un'impostazione della lingua. È possibile utilizzare code di chiamata diverse se si fa business in più lingue. Gli agenti possono essere membri di più code se sono multilingue.

Per ogni coda di chiamata, è possibile specificare se gli agenti in coda possono rifiutare esplicitamente di effettuare chiamate e se le chiamate devono essere indirizzate a loro in base all'indicazione della presenza in Teams.

È possibile assegnare un numero di telefono a una coda di chiamata, ma le code di chiamata non forniscono un routing di chiamata separato per le ore non lavorative e le festività. A meno che la coda di chiamata non abbia personale 24 ore su 24, 7 giorni su 7, ti consigliamo di assegnare il numero di telefono a un operatore automatico che reindirizza alla coda di chiamata durante l'orario di ufficio.

## <a name="prerequisites"></a>Prerequisiti

Per configurare gli operatori automatici e le code di chiamata, sono necessarie le risorse seguenti:

- Un account di risorsa per ogni operatore automatico e ogni coda di chiamata
- Un sistema Telefono Microsoft gratuito - Licenza utente virtuale per ogni account di risorsa
- Almeno un [numero di servizio Microsoft](getting-service-phone-numbers.md), un numero di Connessione con operatore, un numero di routing diretto o un numero ibrido per ogni account di risorsa che si vuole rendere direttamente componibile
 - Il numero di servizio può essere un numero a pagamento o numero verde

> [!NOTE]
> Gli account delle risorse sono disabilitati per l'accesso e devono rimanere tali. La chat e la presenza non sono disponibili per questi account.

Gli agenti che ricevono chiamate dalle code di chiamata devono essere VoIP aziendale abilitati utenti online o locali. Inoltre, se le code di chiamata utilizzano numeri direct routing, gli agenti che devono effettuare conferenze o trasferire chiamate richiedono anche:

- Un criterio di routing vocale online assegnato se la coda di chiamata usa la modalità di trasferimento
- Una licenza per i servizi di audioconferenza o un criterio di routing vocale online assegnato se la coda di chiamata usa la modalità conferenza

Se gli agenti usano l'app Microsoft Teams per le chiamate in coda di chiamata, devono essere in modalità TeamsOnly.

Quando si utilizza un account di risorsa per scopi di ID riga di chiamata nelle code di chiamata o quando un operatore automatico o una coda di chiamata sta trasferendo chiamate a un numero di telefono esterno, l'account della risorsa deve avere una licenza utente virtuale Sistema telefonico e una delle seguenti assegnate:

- Una licenza [per un Piano per chiamate](calling-plans-for-office-365.md) e un numero di telefono assegnato
- Un [numero di telefono Connessione con operatore](operator-connect-plan.md) assegnato
- Un [criterio di routing vocale online](manage-voice-routing-policies.md) (l'assegnazione del numero di telefono è facoltativa quando si usa l'instradamento diretto)

> [!NOTE]
> Se il Piano per chiamate assegnato all'account della risorsa viene disabilitato o rimosso, verranno utilizzati i [Crediti comunicazioni](what-are-communications-credits.md), se disponibili nel tenant (senza essere assegnati all'account della risorsa). Se non sono presenti Piani per chiamate o Crediti comunicazioni, la chiamata avrà esito negativo.
>
> I numeri di servizio direct routing per l'operatore automatico e le code di chiamata sono supportati solo per Microsoft Teams utenti e agenti di chiamata.
> 
> I trasferimenti tra i trunk Piano per chiamate, Connessione con operatore e Routing diretto non sono supportati.
> 
> In uno scenario ibrido, l'account della risorsa deve essere creato in locale. Per ulteriori informazioni, vedi [Pianificare le code di chiamata cloud](/skypeforbusiness/hybrid/plan-call-queue).

## <a name="business-decisions"></a>Decisioni aziendali

Prima di configurare gli operatori automatici e le code di chiamata, è necessario prendere alcune decisioni su come usare queste funzionalità nell'azienda. Queste decisioni determineranno le impostazioni che scegli quando configuri gli operatori automatici e le code di chiamata.

Documentare le risposte a queste domande e fornire le informazioni all'amministratore che esegue la configurazione.

- Quali lingue ti servono? Dove sono necessarie queste lingue, quale reparto o gruppo?
- Vuoi consentire gli input vocali dei chiamanti o solo gli input di chiamata?
- È necessario separare il routing delle chiamate per le ore non lavorative o le festività? Quali sono gli orari e le festività?
- Vuoi consentire agli agenti in una coda di chiamata di rifiutare esplicitamente di effettuare chiamate?
- Vuoi che gli agenti nelle tue code di chiamata o il tuo operatore abbiano un ID chiamante specifico se eseguono la chiamata in uscita?
- Si desidera abilitare il [parcheggio e il recupero delle chiamate](call-park-and-retrieve.md) nell'organizzazione per facilitare le comunicazioni tra persone o reparti?
- Per i comandi vocali, vuoi registrarne uno personale o usare la voce generata dal sistema? La voce generata dal sistema è facile da aggiornare.

## <a name="technical-decisions"></a>Decisioni tecniche

Quando si usano operatori automatici e code di chiamata per connettere i chiamanti alle persone dell'organizzazione, è necessario prendere alcune decisioni tecniche prima di avviare la configurazione.

Gli agenti possono essere aggiunti alle code di chiamata nei modi seguenti:

- Singoli utenti
- Liste di distribuzione
- Gruppi di sicurezza, inclusi i gruppi di sicurezza abilitati alla posta elettronica
- Gruppi di Microsoft 365 o Teams

Se necessario, è possibile usare una combinazione di queste opzioni per ogni coda. I gruppi con un indirizzo di posta elettronica possono essere usati per la segreteria telefonica. L'uso di Teams offre molti vantaggi, tra cui l'archiviazione di file condivisi e la chat tra agenti, una cassetta postale comune in cui è possibile ricevere i messaggi vocali e una piattaforma estendibile che può includere l'integrazione con applicazioni line-of-business o Power Apps.

È consigliabile scegliere una strategia per l'aggiunta di agenti di chiamata alle code prima di avviare la configurazione.

Se hai già un operatore automatico e un'infrastruttura della coda di chiamata e stai eseguendo la migrazione a Teams, avrai bisogno di un piano per trasferire i numeri di telefono esistenti ai nuovi operatori automatici e code di chiamata. Potrebbe essere necessario creare un [ordine di trasferimento](phone-number-calling-plans/port-order-overview.md) per spostare i numeri da altri provider. Ti consigliamo di acquisire temporaneamente uno o più nuovi numeri di telefono e testare i flussi dell'operatore automatico e della coda di chiamata prima di passare ai numeri attualmente in servizio.

*La modalità conferenza* è un'opzione nelle code di chiamata che riduce significativamente la quantità di tempo necessaria per connettersi Teams chiamate VOIP e chiamate PSTN a un agente. Per il funzionamento della modalità conferenza, gli agenti nella coda di chiamata devono utilizzare uno dei client seguenti:

- La versione più recente del client desktop Microsoft Teams, dell'app Android o dell'app iOS
- Telefono Microsoft Versione di sistema 1449/1.0.94.2020051601 o successiva
  
Impostare gli account Teams agenti sulla modalità di sola Teams. Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di routing delle chiamate.

È consigliabile abilitare la modalità conferenza per le code di chiamata se gli agenti usano tutti client compatibili.

## <a name="plan-your-call-routing-flow"></a>Pianificare il flusso di instradamento delle chiamate

Nell'ambito del processo di pianificazione, è consigliabile elaborare il routing delle chiamate per l'organizzazione in un diagramma. Il diagramma aiuta a determinare il routing più efficiente per le persone che chiamano l'organizzazione. Puoi anche utilizzare il diagramma per determinare gli operatori automatici e le code di chiamata che devi creare, oltre a requisiti correlati come numeri di servizio, licenze e account delle risorse.

Esaminiamo il modo in cui gli operatori automatici e le code di chiamata instradano le chiamate.

Gli operatori automatici instradano tutte le chiamate in uno dei modi seguenti:

- **Reindirizza immediatamente** : le chiamate possono essere reindirizzate a una delle destinazioni di instradamento delle chiamate (elencate di seguito) immediatamente dopo la risposta o dopo il saluto iniziale.
- **Reindirizzamento in base alle opzioni di chiamata** : i chiamanti possono essere indirizzati per scegliere tra le opzioni assegnate ai numeri sulla tastiera del telefono, 0-9. A ogni tasto di chiamata possono essere assegnate destinazioni di routing delle chiamate.
- **Comporre le persone per nome o estensione** : i chiamanti possono essere indirizzati a comporre il numero di interno della persona che si sta cercando di raggiungere nella directory dell'organizzazione o digitando il nome della persona.
- **Disconnetti** - un operatore automatico può riagganciare la chiamata.

> [!NOTE]
> Un singolo operatore automatico può supportare solo un singolo metodo "chiamata per".  Per consentire ai chiamanti di comporre per nome e per numero, dovrai creare un operatore automatico che abbia un'opzione per comporre per nome e l'altro per comporre per estensione.  Ognuna di queste opzioni verrà instradata a operatori automatici separati configurati per questi scenari di "chiamata per".

Quando le chiamate vengono reindirizzate da un operatore automatico o da una coda di chiamata, puoi scegliere tra le seguenti destinazioni di instradamento delle chiamate:

- **Persona dell'organizzazione** : una persona dell'organizzazione che è in grado di ricevere chiamate vocali. Può trattarsi di un utente online o di un utente ospitato in locale usando Skype for Business Server.
- **App vocale** : un altro operatore automatico o una coda di chiamata. Scegliere l'account della risorsa associato alla destinazione.
- **Numero di telefono esterno** : qualsiasi numero di telefono. (Vedere [i dettagli tecnici sul trasferimento esterno](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- **Segreteria telefonica**: cassetta postale vocale associata a un gruppo di Microsoft 365 specificato. È possibile scegliere se si vogliono le trascrizioni della segreteria telefonica e "Lascia un messaggio dopo il tono". richiesta di sistema.
- **Operatore** (solo operatore automatico) - operatore definito per l'operatore automatico. La definizione di un operatore è facoltativa. Un operatore può essere una qualsiasi delle altre destinazioni in questo elenco.

Gli operatori automatici offrono opzioni di instradamento delle chiamate separate per le chiamate ricevute al di fuori dell'orario di ufficio e nei giorni festivi. 

Le code di chiamata bloccano il chiamante finché un agente assegnato alla coda non è disponibile per la chiamata. Esistono due situazioni in cui un chiamante potrebbe essere escluso dalla coda:

- **Overflow chiamata** : se il numero di chiamate in coda supera il limite impostato, i nuovi chiamanti vengono reindirizzati fuori dalla coda.
- **Timeout chiamata** : se un chiamante è rimasto in coda più a lungo dell'impostazione di timeout configurata, viene reindirizzato fuori dalla coda.

Le chiamate reindirizzate da una coda possono essere inviate a una delle destinazioni di routing delle chiamate elencate sopra, ad eccezione di un operatore. Le code di chiamata non includono operatori, ma puoi reindirizzare i chiamanti alla stessa destinazione di un operatore configurato per un operatore automatico.

L'esempio seguente mostra un esempio di routing delle chiamate tramite operatori automatici e code di chiamata.

![Diagramma del routing delle chiamate con operatori automatici e code di chiamata.](media/attendant-and-queue-call-routing.png)

Nell'esempio precedente:

- Il tasto zero (0) reindirizza i chiamanti a un operatore. L'operatore per quell'operatore automatico è stato configurato come **Persona nell'organizzazione**.
- Il tasto uno (1) reindirizza i chiamanti alla coda di chiamata di vendita. Questa coda di chiamata è connessa a un team che contiene il team di vendita assegnato alla coda.
- Il tasto due (2) reindirizza i chiamanti alla coda di chiamata di supporto. Questa coda di chiamata è connessa a un team che contiene il team di supporto assegnato al team.
- La coda di chiamata di supporto ha un numero di telefono diretto tramite un operatore automatico intercorso. Chiedere a un operatore automatico di rispondere alla linea di supporto consente di separare orario di attesa e instradamento delle chiamate durante le festività.
- Il codice tre (3) reindirizza gli utenti a un altro operatore automatico per l'elenco aziendale. L'operatore automatico dell'elenco aziendale consente ai chiamanti di chiamare i singoli utenti dell'organizzazione componendo il nome o l'estensione.

È consigliabile creare uno o più diagrammi simili a quello riportato sopra per mappare il routing delle chiamate. Assicurarsi di includere quanto segue nel diagramma o nella documentazione di accompagnamento:

- Quali operatori automatici avranno accesso diretto tramite i numeri di telefono?
- Quali sono i requisiti di routing off-hours e holiday per ogni operatore automatico?
- Appartenenza per ogni coda di chiamata. È possibile aggiungere utenti singolarmente o mappare la coda a diversi tipi di gruppi. Il mapping di una coda a un team offre l'esperienza più versatile.

Ecco alcune procedure consigliate per il routing delle chiamate:

- Controlla il sistema di chiamate esistente e analizza i tipi e la frequenza delle chiamate in arrivo. Usa queste informazioni per informare l'operatore automatico e la struttura della coda di chiamata.
- Inserisci le opzioni più comuni al più presto nel menu per instradare le chiamate il più velocemente possibile.
- Evita di collegare i numeri di servizio direttamente alle code di chiamata, a meno che le code non siano disponibili 24 ore su 24, 7 giorni su 7. Le code di chiamata non consentono la gestione separata delle chiamate per le ore non lavorative o le festività. Se vuoi avere una coda con un numero diretto, assegna il numero a un operatore automatico che reindirizza automaticamente alla coda durante l'orario di ufficio.
- Se ricevi numerose chiamate che richiedono informazioni di base sulla tua azienda, ad esempio l'orario di ufficio, la posizione o l'indirizzo del sito Web, valuta la possibilità di creare un operatore automatico per rispondere a queste domande con messaggi registrati.
- Mantenere l'elenco delle voci di menu a cinque o meno. I chiamanti possono avere difficoltà a ricordare più di cinque opzioni. Usa gli operatori automatici annidati se sono necessarie più opzioni per instradare correttamente una chiamata.
- Descrivi prima il servizio, seguito dall'opzione di pressione (ad esempio: For Sales press 1) anziché viceversa (ad esempio. Premere 1 per Vendite).
- La terminologia dell'utente che i chiamanti comprenderanno invece di ciò che è possibile usare internamente.
- Evitare aggiornamenti frequenti per il routing delle chiamate. Se cambi le opzioni di menu per un operatore automatico in futuro, puoi chiamarlo nelle istruzioni vocali per i primi 30 giorni.

## <a name="getting-started"></a>Introduzione

Dopo aver completato le attività di pianificazione in questo articolo, segui questi passaggi per configurare gli operatori automatici e le code di chiamata:

1. Ottieni i numeri di servizio necessari per gli operatori automatici e le code di chiamata che desideri siano accessibili componendo direttamente dall'esterno dell'organizzazione. Può essere incluso il [trasferimento di numeri da un altro provider](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o [la richiesta di nuovi numeri di servizio](getting-service-phone-numbers.md).

2. Ottenere una [licenza Sistema telefonico - Utente virtuale](teams-add-on-licensing/virtual-user.md) per ogni account di risorsa che si prevede di creare. Queste licenze sono gratuite, quindi è consigliabile ottenere alcuni extra nel caso in cui si decida di apportare modifiche agli account delle risorse in futuro.

3. [Crea un account di risorsa](manage-resource-accounts.md) per ogni operatore automatico e coda di chiamata che vuoi creare. Assegnare a ogni account una licenza Sistema telefonico - Utente virtuale e, facoltativamente, un numero di servizio.

4. [Crea le festività](set-up-holidays-in-teams.md) per le quali desideri disporre di routing delle chiamate separato negli operatori automatici.

5. Facoltativamente, [impostare il parcheggio e il recupero delle chiamate](call-park-and-retrieve.md) se si vuole usare questa funzionalità per facilitare i trasferimenti di chiamata.

6. Creare i gruppi da usare per contenere gli agenti di chiamata per le code di chiamata.

7. Se si prevede di consentire la chiamata per estensione, assicurarsi di aver aggiunto il numero di interno degli utenti al loro profilo di Azure Active Directory.

Dopo aver completato i passaggi precedenti, sei pronto per creare gli operatori automatici e le code di chiamata. Poiché gli operatori automatici e le code di chiamata possono reindirizzare le chiamate reciprocamente, fare riferimento al diagramma del flusso di lavoro creato per determinare quale operatore automatico o coda di chiamata deve essere creato per primo. Nell'esempio riportato nel diagramma precedente, è necessario creare le code di chiamata di vendita e supporto prima di creare l'operatore automatico principale Contoso perché l'operatore automatico principale deve indirizzare i chiamanti alle code di chiamata di vendita e di supporto.

Vedi gli articoli seguenti per informazioni su come creare operatori automatici e code di chiamata:

- [Configurare un operatore automatico](create-a-phone-system-auto-attendant.md)
- [Creare una coda di chiamata](create-a-phone-system-call-queue.md)

Se sono necessarie funzionalità più estese, ad esempio l'integrazione con flussi di lavoro, bot e SMS, considerare [Servizi di comunicazione di Azure](/azure/communication-services/overview).

## <a name="related-topics"></a>Argomenti correlati

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Creare una coda di chiamata - Esercitazione per piccole imprese](business-voice/create-a-phone-system-call-queue-smb.md)

[Configurare un operatore automatico - Esercitazione per piccole imprese](business-voice/create-a-phone-system-auto-attendant-smb.md)
