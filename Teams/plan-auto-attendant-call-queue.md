---
title: Pianificare Teams operatori automatici e code di chiamata
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Informazioni sugli operatori automatici e sulle code di chiamata e su come usarli per aiutare i chiamanti a spostarsi in un sistema di menu per raggiungere persone o reparti dell'organizzazione.
ms.openlocfilehash: 1ccce8205afcf019fea539823c21e3a29a2fa206
ms.sourcegitcommit: d5e77f8a3b8084ed92f0a77888a555626309591b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "52517749"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Pianificare Teams operatori automatici e code di chiamata

Gli operatori automatici consentono di configurare le opzioni di menu per instradare le chiamate in base all'input del chiamante. Opzioni di menu, ad esempio "Per le vendite, premere 1.  Per i servizi premere 2", per un operatore automatico consentire a un'organizzazione di fornire una serie di scelte che guidano i chiamanti verso la destinazione rapidamente, senza affidarsi a un operatore umano per gestire le chiamate in arrivo.

Le code di chiamata sono aree di attesa per i chiamanti. Per le situazioni in cui i chiamanti devono contattare qualcuno con una particolare specializzazione, ad esempio vendite o servizi, invece di una persona specifica, è possibile usare le code di chiamata per connettere i chiamanti al gruppo di agenti che possono assisterli. I chiamanti vengono messi in attesa finché un agente assegnato alla coda non è disponibile per la chiamata.

Usati insieme, gli operatori automatici e le code di chiamata possono instradare facilmente i chiamanti alla persona o al reparto appropriato dell'organizzazione.

## <a name="auto-attendants"></a>Operatori automatici

Lo scopo principale di un operatore automatico è indirizzare un chiamante a una persona o un reparto appropriato in base all'input del chiamante alle opzioni di menu fornite. I chiamanti possono essere indirizzati a persone specifiche all'interno dell'organizzazione, alle code di chiamata in cui aspettano di parlare con il prossimo agente disponibile o alla segreteria telefonica. È possibile specificare diverse opzioni di instradamento delle chiamate per gli orari di ufficio, gli orari di ferie e le festività.

Le richieste di menu possono essere create usando la sintesi vocale (prompt generati dal sistema) o caricando un file audio registrato. Il riconoscimento vocale accetta i comandi vocali per la navigazione senza mani, ma le persone che chiamano possono anche usare il tastierino del telefono per spostarsi tra i menu.

Ogni operatore automatico ha una lingua e un fuso orario specifici. Se si fanno affari in più lingue o in più parti del mondo, è possibile creare tutti gli operatori automatici necessari per soddisfare i chiamanti.

Per ogni operatore automatico, è possibile configurare un operatore. Anche se è possibile configurare le chiamate dell'operatore in modo che vadano verso un'ampia gamma di destinazioni, la funzionalità dell'operatore è progettata per consentire ai chiamanti di parlare con una persona specifica dell'organizzazione che può aiutarla.

Gli operatori automatici possono essere configurati per consentire ai chiamanti di eseguire ricerche nella directory dell'organizzazione, in base al nome o al numero di interno. All'interno di un operatore automatico è possibile specificare chi è disponibile per la ricerca nella directory scegliendo gruppi di utenti da includere o escludere. Questo ambito è noto come *ambito di chiamata.*

I chiamanti possono raggiungere un operatore automatico tramite un numero di telefono diretto, se configurato, oppure essere reindirizzati da un altro operatore automatico o da una coda di chiamata.

## <a name="call-queues"></a>Code di chiamata

Una coda di chiamata è analoga a una sala d'attesa in un edificio fisico. I chiamanti aspettano in attesa mentre le chiamate vengono instradati agli agenti nella coda. Le code di chiamata vengono in genere usate per le funzioni di vendita e servizio. Tuttavia, le code di chiamata possono essere usate per qualsiasi situazione in cui il numero di chiamate supera la capacità interna, ad esempio un addetto alla ricezione in una struttura occupata.

Le code di chiamata consentono un instradamento specifico delle chiamate nei casi in cui il numero totale di chiamanti in coda o il tempo di attesa supera i limiti specificati. Le chiamate possono essere instradati a persone specifiche, segreteria telefonica, altre code di chiamata o operatori automatici.

Come gli operatori automatici, le code di chiamata hanno ognuna un'impostazione della lingua. È possibile usare code di chiamata diverse se si fanno affari in più lingue. Gli agenti possono essere membri di più code se sono multilingue.

Per ogni coda di chiamata, è possibile specificare se gli agenti in coda possono rifiutare esplicitamente di effettuare chiamate e se le chiamate devono essere instradati a loro in base all'indicazione di presenza in Teams.

È possibile assegnare un numero di telefono a una coda di chiamata, tuttavia le code di chiamata non forniscono un instradamento delle chiamate separato per le ore non lavorative e le festività. A meno che la coda di chiamata non venga assegnata 24 ore su 24, 7 giorni su 7, è consigliabile assegnare il numero di telefono a un operatore automatico che reindirizza alla coda di chiamata durante l'orario di ufficio.

## <a name="prerequisites"></a>Prerequisiti

Per configurare gli operatori automatici e le code di chiamata, sono necessarie le risorse seguenti:

- Un account di risorsa per ogni operatore automatico e ogni coda di chiamata
- Una licenza Sistema telefonico - Utente virtuale gratuita per ogni account delle risorse
- Almeno un numero [di servizio Microsoft,](getting-service-phone-numbers.md)un numero di routing diretto o un numero ibrido per ogni account della risorsa che si vuole chiamare direttamente
 - Il numero del servizio può essere a numero verde o a numero verde

Gli agenti che ricevono chiamate dalle code di chiamata devono essere abilitati VoIP aziendale utenti online o locali. Inoltre, se le code di chiamata usano numeri di instradamento diretto, anche gli agenti che devono effettuare conferenze o trasferire chiamate richiedono:

- Criterio di routing vocale online assegnato se la coda di chiamata usa la modalità di trasferimento
- Una licenza di audioconferenza o un criterio di routing vocale online assegnato se la coda di chiamata usa la modalità conferenza

Se gli agenti usano l'app Microsoft Teams per le chiamate in coda di chiamata, devono essere in modalità TeamsOnly.

Quando si trasferiscono chiamate a un numero di telefono esterno, l'account della risorsa che esegue il trasferimento, ovvero quello associato all'operatore automatico o alla coda di chiamata, deve avere una licenza utente virtuale Microsoft 365 Sistema telefonico e una delle seguenti:

- Una [licenza per il piano](calling-plans-for-office-365.md) di chiamata e un numero di telefono assegnato
- Criteri [di routing vocale online](manage-voice-routing-policies.md) (l'assegnazione del numero di telefono è facoltativa quando si usa Il routing diretto)

> [!NOTE]
> I numeri di servizio Instradamento diretto per l'operatore automatico e le code di chiamata sono supportati solo per Microsoft Teams utenti e agenti di chiamata.<br>
> I trasferimenti tra i trunk del piano di chiamata e i trunk di routing diretto non sono supportati.<br>
> In uno scenario ibrido, l'account della risorsa deve essere creato in locale. Per altre informazioni, vedere [Pianificare le code di chiamata cloud.](/skypeforbusiness/hybrid/plan-call-queue)

## <a name="business-decisions"></a>Decisioni aziendali

Prima di configurare gli operatori automatici e le code di chiamata, è necessario prendere alcune decisioni su come usare queste funzionalità nell'azienda. Queste decisioni determineranno le impostazioni scelte quando si configurano gli operatori automatici e le code di chiamata.

Documentare le risposte a queste domande e fornire le informazioni all'amministratore che effettua la configurazione.

- Quali lingue sono necessarie? Dove sono necessarie queste lingue, quale reparto o gruppo?
- Si vogliono consentire gli input vocali dei chiamanti o solo gli input di composizione?
- È necessario un instradamento delle chiamate separato per gli orari di ferie o le ferie? Quali sono le ore e le festività?
- Si vuole consentire agli agenti in coda di chiamata di rifiutare esplicitamente di effettuare chiamate?
- Si vuole che gli agenti nelle code di chiamata o l'operatore abbiano un ID chiamante specifico se ese chiamano in uscita?
- Si vuole abilitare il [parcheggio e](call-park-and-retrieve.md) il recupero delle chiamate all'interno dell'organizzazione per agevolare i consenzimenti delle chiamate tra persone o reparti?
- Per le istruzioni vocali, si vuole registrare la propria voce o usare la voce generata dal sistema? La voce generata dal sistema è facile da aggiornare.

## <a name="technical-decisions"></a>Decisioni tecniche

Quando si usano operatori automatici e code di chiamata per connettere i chiamanti alle persone dell'organizzazione, è necessario prendere alcune decisioni tecniche prima di avviare la configurazione.

Gli agenti possono essere aggiunti alle code di chiamata nei modi seguenti:

- Singoli utenti
- Liste di distribuzione
- Gruppi di sicurezza, inclusi i gruppi di sicurezza abilitati alla posta elettronica
- Microsoft 365 Gruppi o Teams

Se necessario, è possibile usare una combinazione di queste opzioni per ogni coda. I gruppi con un indirizzo di posta elettronica possono essere usati per la segreteria telefonica. L'uso di Teams offre una serie di vantaggi, tra cui l'archiviazione condivisa dei file e la chat tra agenti, una cassetta postale comune in cui è possibile ricevere i messaggi vocali e una piattaforma estendibile che può includere l'integrazione con le applicazioni line-of-business o con Power Apps.

È consigliabile scegliere una strategia per l'aggiunta di agenti di chiamata alle code prima di iniziare la configurazione.

Se si ha un operatore automatico e un'infrastruttura della coda di chiamata esistente e si esegue la migrazione a Teams, è necessario un piano per trasferire i numeri di telefono esistenti ai nuovi operatori automatici e alle nuove code di chiamata. Potrebbe essere necessario creare un ordine [di trasferimento per](phone-number-calling-plans/port-order-overview.md) spostare i numeri da un altro provider. È consigliabile acquisire temporaneamente uno o più nuovi numeri di telefono e testare i flussi dell'operatore automatico e della coda di chiamata prima di cambiarli rispetto ai numeri attualmente in servizio.

*La modalità* conferenza è un'opzione nelle code di chiamata che riduce significativamente il tempo necessario per connettere le chiamate VOIP e PSTN Teams chiamate VOIP a un agente. Per il funzionamento della modalità conferenza, gli agenti nella coda di chiamata devono usare uno dei client seguenti:

- La versione più recente del client desktop Microsoft Teams, dell'app Android o dell'app iOS
  - Microsoft Teams telefono 1449/1.0.94.2020051601 o versione successiva
  
Impostare gli account Teams agenti sulla Teams solo utenti. Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di routing delle chiamate.

È consigliabile abilitare la modalità conferenza per le code di chiamata se tutti gli agenti usano client compatibili.

## <a name="plan-your-call-routing-flow"></a>Pianificare il flusso di routing delle chiamate

Nell'ambito del processo di pianificazione, è consigliabile elaborare il routing delle chiamate per l'organizzazione in un diagramma. Il diagramma consente di determinare il routing più efficiente per le persone che chiamano all'organizzazione. È anche possibile usare il diagramma per determinare gli operatori automatici e le code di chiamata da creare, insieme ai requisiti correlati, ad esempio numeri di servizio, licenze e account delle risorse.

Diamo un'occhiata a come gli operatori automatici e le code di chiamata instradare le chiamate.

Gli operatori automatici instradare tutte le chiamate in uno dei modi seguenti:

- **Reindirizza** immediatamente: le chiamate possono essere reindirizzate a una delle destinazioni di routing delle chiamate (elencate di seguito) immediatamente dopo aver risposto o dopo un messaggio di saluto iniziale.
- **Reindirizza** in base alle opzioni di chiamata: i chiamanti possono scegliere tra le opzioni assegnate ai numeri sul tastierino del telefono, 0-9. A ogni tasto di chiamata può essere assegnata una destinazione di routing delle chiamate.
- **Comporre persone per** nome o interno: i chiamanti possono essere indirizzati a comporre il numero di interno della persona che stanno cercando di raggiungere nell'elenco dell'organizzazione o digitando il nome della persona.
- **Disconnetti:** un operatore automatico può riagganciare la chiamata.

> [!NOTE]
> Un singolo operatore automatico può supportare un solo metodo di chiamata.  Per consentire ai chiamanti di effettuare chiamate in base al nome e al numero, è necessario creare un operatore automatico che abbia un'opzione per comporre per nome e l'altro per comporre per interno.  Ognuna di queste opzioni instraderà a operatori automatici separati configurati per questi scenari di chiamata per.

Quando le chiamate vengono reindirizzate da un operatore automatico o da una coda di chiamata, è possibile scegliere tra le destinazioni di routing delle chiamate seguenti:

- **Persona dell'organizzazione:** una persona dell'organizzazione che è in grado di ricevere chiamate vocali. Può trattarsi di un utente online o di un utente ospitato in locale usando Skype for Business Server.
- **App vocale:** un altro operatore automatico o una coda di chiamata. Scegliere l'account della risorsa associato alla destinazione.
- **Numero di telefono esterno:** qualsiasi numero di telefono. (Vedere [dettagli tecnici sul trasferimento esterno).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)
- **Segreteria telefonica:** la cassetta postale vocale associata a Microsoft 365 gruppo specificato dall'utente.
- **Operatore** (solo operatore automatico): l'operatore definito per l'operatore automatico. La definizione di un operatore è facoltativa. Un operatore può essere una qualsiasi delle altre destinazioni dell'elenco.

Gli operatori automatici offrono opzioni di routing delle chiamate separate per le chiamate ricevute al di fuori dell'orario di ufficio e nei giorni festivi. L'instradamento delle chiamate dopo le ore consente tutte le opzioni elencate sopra, mentre l'instradamento delle chiamate natalizie consente solo il reindirizzamento o la disconnessione di una chiamata, ma non le opzioni dei tasti di chiamata.

Le code di chiamata tengono il chiamante in attesa finché un agente assegnato alla coda non è disponibile per la chiamata. Esistono due situazioni in cui un chiamante potrebbe essere indirizzato fuori dalla coda:There are two situations where a caller might be directed out of the queue:

- **Overflow delle** chiamate: se il numero di chiamate nella coda supera il limite impostato, i nuovi chiamanti vengono reindirizzati fuori dalla coda.
- **Timeout chiamata:** se un chiamante è stato in coda più a lungo dell'impostazione di timeout configurata, viene reindirizzato fuori dalla coda.

Le chiamate reindirizzate da una coda possono essere inviate a una delle destinazioni di routing delle chiamate elencate sopra, ad eccezione di un operatore. Le code di chiamata non hanno operatori, ma è possibile reindirizzare i chiamanti alla stessa destinazione di un operatore configurato per un operatore automatico.

L'esempio seguente mostra un esempio di routing delle chiamate con operatori automatici e code di chiamata.

![Diagramma del routing delle chiamate con operatori automatici e code di chiamata](media/attendant-and-queue-call-routing.png)

Nell'esempio precedente:

- Il tasto zero (0) reindirizza i chiamanti a un operatore. L'operatore per l'operatore automatico è stato configurato come **Persona nell'organizzazione.**
- Il tasto uno (1) reindirizza i chiamanti alla coda di chiamata di vendita. Questa coda di chiamata è connessa a un team che contiene il team di vendita assegnato alla coda.
- Il tasto due (2) reindirizza i chiamanti alla coda di chiamata di supporto. Questa coda di chiamata è connessa a un team che contiene il team di supporto assegnato al team.
- La coda di chiamata di supporto ha un numero di telefono diretto tramite un operatore automatico interviene. Avere un operatore automatico che risponda alla linea di supporto consente orari di ferie separati e instradamento delle chiamate per le festività.
- Il tasto tre (3) reindirizza gli utenti a un altro operatore automatico per la directory aziendale. L'operatore automatico dell'elenco aziendale consente ai chiamanti di chiamare persone dell'organizzazione componendo il nome o l'interno.

È consigliabile creare uno o più diagrammi simili a quello precedente per mappare il routing delle chiamate. Assicurarsi di includere quanto segue nel diagramma o nella documentazione di accompagnamento:

- Quali operatori automatici avranno accesso diretto tramite numeri di telefono?
- Quali sono i requisiti di instradamento fuori orario e festive per ogni operatore automatico?
- Appartenenza per ogni coda di chiamata. È possibile aggiungere utenti singolarmente o mappare la coda a diversi tipi di gruppi. Il mapping di una coda a un team offre l'esperienza più versatile.

Ecco alcune procedure consigliate per il routing delle chiamate:

- Esaminare il sistema di chiamate esistente e analizzare i tipi e la frequenza delle chiamate in arrivo. Usare queste informazioni per informare l'operatore automatico e la struttura della coda di chiamata.
- Inserire le opzioni più comuni nel menu per instradare le chiamate il più rapidamente possibile.
- Evitare di connettere i numeri di servizio direttamente alle code di chiamata, a meno che le code non siano disponibili 24 ore su 24, 7 giorni su 7. Le code di chiamata non consentono una gestione separata delle chiamate per le ore non lavorative o le festività. Se si vuole avere una coda con un numero diretto, assegnare il numero a un operatore automatico che reindirizza automaticamente alla coda durante l'orario di ufficio.
- Se si ricevono numerose chiamate che richiedono informazioni di base sulla società, ad esempio l'orario di ufficio, la posizione o l'indirizzo del sito Web, è consigliabile creare un operatore automatico per rispondere a queste domande con i messaggi registrati.
- Mantenere l'elenco delle voci di menu fino a cinque o meno. I chiamanti possono avere problemi a ricordare più di cinque opzioni. Usare operatori automatici annidati se sono necessarie altre opzioni per instradare correttamente una chiamata.
- Descrivere prima il servizio, seguito dall'opzione da premere (ad esempio: Per le vendite premere 1) invece che dall'altra parte (ad esempio. Premere 1 per Vendite).
- Terminologia degli utenti che i chiamanti comprenderanno invece di ciò che è possibile usare internamente.
- Evitare frequenti aggiornamenti al routing delle chiamate. Se si modificano le opzioni di menu per un operatore automatico in futuro, chiamare questa opzione nelle istruzioni vocali per i primi 30 giorni.

## <a name="getting-started"></a>Introduzione

Dopo aver completato le attività di pianificazione descritte in questo articolo, seguire questa procedura per configurare gli operatori automatici e le code di chiamata:

1. Ottenere i numeri di servizio necessari per gli operatori automatici e le code di chiamata a cui si vuole essere accessibili componendo direttamente dall'esterno dell'organizzazione. Questo può includere [il trasferimento di numeri da un altro provider o](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) la richiesta di nuovi numeri di [servizio.](getting-service-phone-numbers.md)

2. Ottenere una [Sistema telefonico - Licenza utente virtuale](teams-add-on-licensing/virtual-user.md) per ogni account delle risorse che si prevede di creare. Queste licenze sono gratuite, quindi ti consigliamo di ottenere qualche ulteriore abbonamento nel caso in cui decidi di apportare modifiche agli account delle risorse in futuro.

3. [Creare un account della risorsa](manage-resource-accounts.md) per ogni operatore automatico e coda di chiamata che si vuole creare. Assegnare a ogni account Sistema telefonico - Licenza utente virtuale e, facoltativamente, un numero di servizio.

4. [Creare le festività](set-up-holidays-in-teams.md) per cui si vuole disporre di un instradamento delle chiamate separato negli operatori automatici.

5. Facoltativamente, [configurare il parcheggio e il](call-park-and-retrieve.md) recupero delle chiamate se si vuole usare questa funzionalità per facilitare i trasferimenti di chiamata.

6. Creare i gruppi da usare per contenere gli agenti di chiamata per le code di chiamata.

7. Se si prevede di consentire la chiamata per interno, assicurarsi di aver aggiunto il numero di interno degli utenti al profilo Azure Active Directory telefono.

Dopo aver completato i passaggi precedenti, è possibile creare gli operatori automatici e le code di chiamata. Poiché gli operatori automatici e le code di chiamata possono reindirizzare le chiamate tra loro, fare riferimento al diagramma del flusso di lavoro creato per determinare quale operatore automatico o coda di chiamata deve essere creato per primo. Nell'esempio del diagramma precedente è necessario creare le code di chiamata di vendita e supporto prima di creare l'operatore automatico principale contoso, perché l'operatore automatico principale deve indirizzare i chiamanti alle code di chiamata di vendita e supporto.

Per informazioni su come creare operatori automatici e code di chiamata, vedere gli articoli seguenti:

- [Configurare un operatore automatico](create-a-phone-system-auto-attendant.md)
- [Creare una coda di chiamata](create-a-phone-system-call-queue.md)

Se sono necessarie funzionalità più estese, ad esempio l'integrazione con flussi di lavoro, bot e SMS, prendere in considerazione [Servizi di comunicazione di Azure.](/azure/communication-services/overview)

## <a name="related-topics"></a>Argomenti correlati

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Creare una coda di chiamata - Esercitazione sulle piccole imprese](business-voice/create-a-phone-system-call-queue-smb.md)

[Configurare un operatore automatico - Esercitazione sulle piccole imprese](business-voice/create-a-phone-system-auto-attendant-smb.md)
