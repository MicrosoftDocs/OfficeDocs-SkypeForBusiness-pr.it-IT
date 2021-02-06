---
title: Pianificare gli operatori automatici di teams e le code di chiamata
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
description: Informazioni sugli operatori automatici e sulle code di chiamata e su come usarli per consentire ai chiamanti di spostarsi in un sistema di menu per raggiungere persone o reparti dell'organizzazione.
ms.openlocfilehash: 65dac48267379d17b76443e42eb70e2e866f6e8f
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125668"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Pianificare gli operatori automatici di teams e le code di chiamata

Gli operatori automatici consentono di configurare le opzioni di menu per instradare le chiamate in base all'input del chiamante. Opzioni di menu, ad esempio "per le vendite, premere 1.  Per i servizi premere 2 ", per un operatore automatico consentire a un'organizzazione di creare una serie di scelte che guidano i chiamanti alla destinazione in modo rapido, senza affidarsi a un operatore umano per gestire le chiamate in arrivo.

Le code di chiamata sono aree di attesa per i chiamanti. Per le situazioni in cui i chiamanti devono raggiungere un utente con una particolare specialità, ad esempio vendite o servizi, anziché una persona specifica, è possibile usare le code di chiamata per connettere i chiamanti al gruppo di agenti che possono assisterli. I chiamanti vengono messi in attesa finché non è disponibile un agente assegnato alla coda per eseguire la chiamata.

Gli operatori automatici e le code di chiamata usati insieme possono facilmente instradare i chiamanti alla persona o al reparto appropriato dell'organizzazione.

## <a name="auto-attendants"></a>Operatori automatici

Lo scopo principale di un operatore automatico è quello di indirizzare un chiamante a una persona o reparto appropriata in base all'input del chiamante per le opzioni di menu fornite. I chiamanti possono essere indirizzati a utenti specifici all'interno dell'organizzazione, per chiamare le code in cui attendono di comunicare con il successivo agente disponibile o in segreteria telefonica. Le diverse opzioni di routing delle chiamate possono essere specificate per le ore lavorative, le ore e le festività.

Le richieste di menu possono essere create usando la sintesi vocale (prompt generati dal sistema) o caricando un file audio registrato. Il riconoscimento vocale accetta i comandi vocali per la navigazione senza mani, ma le persone che chiamano possono anche usare la tastiera del telefono per spostarsi tra i menu.

Ogni operatore automatico ha una lingua e un fuso orario specifici. Se si lavora in più lingue o in più parti del mondo, è possibile creare tutti gli operatori automatici diversi necessari per soddisfare i chiamanti.

Per ogni operatore automatico puoi configurare un operatore. Anche se puoi configurare le chiamate degli operatori per accedere a una varietà di destinazioni, la funzionalità operatore è progettata per consentire ai chiamanti di parlare con una persona specifica dell'organizzazione che può aiutarli.

Gli operatori automatici possono essere configurati per consentire ai chiamanti di eseguire ricerche nella directory dell'organizzazione, in base al nome o al numero di interno. All'interno di un operatore automatico puoi specificare chi è disponibile per la ricerca nella directory scegliendo gruppi di utenti da includere o escludere. (Questo è noto come *ambito di chiamata*.)

I chiamanti possono raggiungere un operatore automatico per numero di telefono diretto, se configurati o per essere reindirizzati da un altro operatore automatico o da una coda di chiamata.

## <a name="call-queues"></a>Code di chiamata

Una coda di chiamata è analoga a una sala di attesa in un edificio fisico. I chiamanti attendono il blocco mentre le chiamate vengono instradate agli agenti nella coda. Le code di chiamata sono comunemente usate per le funzioni di vendita e servizio. Tuttavia, le code di chiamata possono essere usate per qualsiasi situazione in cui il numero di chiamate supera la capacità interna, ad esempio un receptionist in uno strumento occupato.

Le code di chiamata consentono il routing specifico delle chiamate nei casi in cui il numero totale di chiamanti nella coda o il tempo di attesa supera i limiti specificati. Le chiamate possono essere indirizzate a persone specifiche, alla segreteria telefonica, ad altre code di chiamata o agli operatori automatici.

Come gli operatori automatici, le code di chiamata hanno ognuna un'impostazione di lingua. Puoi usare code di chiamata diverse se fai affari in più lingue. Gli agenti possono essere membri di più di una coda se sono multilingue.

Per ogni coda di chiamata, è possibile specificare se gli agenti nella coda possono rifiutare di effettuare chiamate e se le chiamate devono essere instradate in base alla loro indicazione di presenza in teams.

È possibile assegnare un numero di telefono a una coda di chiamata, ma le code di chiamata non prevedono un routing delle chiamate separato per le ore e le festività. A meno che la coda di chiamata non abbia un personale di 24/7, è consigliabile assegnare il numero di telefono a un operatore automatico che reindirizza alla coda di chiamata durante le ore lavorative.

## <a name="prerequisites"></a>Prerequisiti

Per configurare gli operatori automatici e le code di chiamata, è necessario disporre delle risorse seguenti:

- Un account delle risorse per ogni operatore automatico e ogni coda di chiamata
- Un sistema telefonico gratuito-licenza per gli utenti virtuali per ogni account delle risorse
- Almeno un numero di [servizio Microsoft](getting-service-phone-numbers.md), un numero di routing diretto o un numero ibrido per ogni account delle risorse che si vuole applicare direttamente
 - Il numero di servizio può essere costituito da un numero verde o gratuito

Gli agenti che ricevono chiamate dalle code di chiamata devono essere gli utenti online o locali abilitati per VoIP aziendale. Inoltre, se le code di chiamata usano i numeri di routing diretto, gli agenti che devono eseguire chiamate di conferenza o trasferimento richiedono anche:

- Un criterio di routing vocale online assegnato se la coda di chiamata usa la modalità di trasferimento
- Una licenza per audioconferenza o un criterio di routing vocale online assegnato se la coda di chiamata usa la modalità conferenza

Se gli agenti usano l'app Microsoft teams per le chiamate alla coda di chiamata, devono essere in modalità TeamsOnly.

Quando si trasferiscono le chiamate a un numero di telefono esterno, l'account delle risorse che esegue il trasferimento, ovvero quello associato all'operatore automatico o alla coda di chiamata, deve avere un numero di telefono e una licenza per gli utenti virtuali di Microsoft 365 Phone System. Inoltre

- Per un account delle risorse con un numero di piano chiamante, assegnare una licenza per il [piano di chiamata](calling-plans-for-office-365.md) .
- Per un account delle risorse con un numero di routing diretto, assegnare un [criterio di routing vocale online](manage-voice-routing-policies.md).

> [!NOTE]
> I numeri di servizio di routing diretto per l'operatore automatico e le code di chiamata sono supportati solo per gli utenti di Microsoft teams e gli agenti di chiamata.<br>
> I trasferimenti tra Trunks del piano chiamante e trunk di routing diretto non sono supportati.

## <a name="business-decisions"></a>Decisioni aziendali

Prima di configurare gli operatori automatici e le code di chiamata, è necessario prendere alcune decisioni su come usare queste funzionalità nell'azienda. Queste decisioni determineranno le impostazioni scelte quando si configurano gli operatori automatici e le code di chiamata.

Documenta le risposte a queste domande e fornisci le informazioni all'amministratore che esegue la configurazione.

- Quali lingue sono necessarie? Dove sono necessarie queste lingue, quale reparto o gruppo?
- Si desidera consentire l'immissione di input vocali dai chiamanti o solo gli input di chiamata?
- È necessario un routing delle chiamate separato per le ore o le festività? Quali sono le ore e le festività?
- Si desidera consentire agli agenti in una coda di chiamata di rifiutare di ricevere chiamate?
- Si desidera che gli agenti nelle code di chiamata o l'operatore abbiano un ID chiamante specifico se effettuano la chiamata in uscita?
- Si desidera abilitare il [parcheggio e il recupero delle chiamate](call-park-and-retrieve.md) nell'organizzazione per facilitare la chiamata delegare tra le persone o i reparti?
- Per le istruzioni vocali, si vuole registrare il proprio o usare la voce generata dal sistema? La voce generata dal sistema è facile da aggiornare.

## <a name="technical-decisions"></a>Decisioni tecniche

Quando si usano gli operatori automatici e le code di chiamata per connettere i chiamanti agli utenti dell'organizzazione, è necessario prendere alcune decisioni tecniche prima di iniziare la configurazione.

Gli agenti possono essere aggiunti alle code di chiamata nei modi seguenti:

- Singoli utenti
- Liste di distribuzione
- Gruppi di sicurezza, inclusi i gruppi di sicurezza abilitati per la posta elettronica
- Gruppi o team di Microsoft 365

Se necessario, è possibile usare una combinazione di queste opzioni per ogni coda. I gruppi con un indirizzo di posta elettronica possono essere usati per la segreteria telefonica. L'uso di teams offre numerosi vantaggi, tra cui l'archiviazione di file condivisi e la chat tra gli agenti, una cassetta postale comune in cui è possibile ricevere messaggi vocali e una piattaforma estensibile che può includere l'integrazione con le applicazioni aziendali o le app di Power Apps.

È consigliabile scegliere una strategia per l'aggiunta di agenti di chiamata alle code prima di iniziare la configurazione.

Se si ha un operatore automatico e un'infrastruttura di coda di chiamata esistenti e si esegue la migrazione a teams, è necessario disporre di un piano per trasferire i numeri di telefono esistenti ai nuovi operatori automatici e alle code di chiamata. Potrebbe essere necessario creare un [ordine](phone-number-calling-plans/port-order-overview.md) di trasferimento per trasferire i numeri da un altro provider. È consigliabile acquisire temporaneamente uno o più numeri di telefono nuovi e verificare i flussi di operatore automatico e coda di chiamata prima di scambiarli tra i numeri attualmente in servizio.

La *modalità conferenza* è un'opzione nelle code di chiamata che riduce significativamente la quantità di tempo necessaria per connettere le chiamate VoIP dei team e le chiamate PSTN a un agente. Per il funzionamento della modalità conferenza, gli agenti nella coda di chiamata devono usare uno dei client seguenti:

- La versione più recente di Microsoft teams desktop client, Android app o iOS app
  - Telefono Microsoft teams versione 1449/1.0.94.2020051601 o successiva
  
Impostare gli account teams degli agenti in modalità solo teams. Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di routing delle chiamate.

È consigliabile abilitare la modalità conferenza per le code di chiamata se gli agenti usano tutti i client compatibili.

## <a name="plan-your-call-routing-flow"></a>Pianificare il flusso di routing delle chiamate

Come parte del processo di pianificazione, è consigliabile elaborare il routing delle chiamate per l'organizzazione in un diagramma. Il diagramma consente di determinare il routing più efficiente per le persone che chiamano l'organizzazione. È anche possibile usare il diagramma per determinare gli operatori automatici e le code di chiamata che è necessario creare, insieme ai relativi requisiti, ad esempio numeri di servizio, licenze e account delle risorse.

Esaminiamo le chiamate agli operatori automatici e alle code di chiamata.

Gli operatori automatici instradano tutte le chiamate in uno dei modi seguenti:

- **Reindirizza immediatamente** : le chiamate possono essere reindirizzate a una delle destinazioni di routing delle chiamate (elencate di seguito) immediatamente dopo aver risposto o dopo un saluto iniziale.
- **Reindirizzamento basato sulle opzioni** di chiamata: i chiamanti possono scegliere tra le opzioni assegnate ai numeri sulla tastiera del telefono, 0-9. A ogni tasto di scelta può essere assegnata una destinazione di routing delle chiamate.
- Gli **utenti con chiamate per nome o estensione** possono essere indirizzati a digitare il numero di interno della persona che si sta provando a raggiungere nella directory dell'organizzazione o a compitare il nome della persona.
- **Disconnetti** : l'operatore automatico può interrompere la chiamata.

> [!NOTE]
> Un singolo operatore automatico può supportare solo un singolo metodo "dial by".  Per consentire ai chiamanti di effettuare chiamate per nome e per numero, è necessario creare un operatore automatico che disponga di un'opzione per il nome della chiamata e l'altro per l'estensione dial by.  Ognuna di queste opzioni verrà instradata per separare gli operatori automatici configurati per questi scenari "dial by".

Quando le chiamate vengono reindirizzate da un operatore automatico o da una coda di chiamata, è possibile scegliere tra le destinazioni di routing delle chiamate seguenti:

- **Persona dell'organizzazione** : una persona dell'organizzazione che è in grado di ricevere chiamate vocali. Può trattarsi di un utente online o di un utente ospitato in locale con Skype for Business Server.
- **App vocale** : un altro operatore automatico o una coda di chiamata. Scegliere l'account delle risorse associato alla destinazione.
- **Numero di telefono esterno** -qualsiasi numero di telefono. (Vedi [Dettagli tecnici del trasferimento esterno](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- **Segreteria telefonica** : casella vocale associata a un gruppo Microsoft 365 specificato.
- **Operator** (solo operatore automatico)-l'operatore definito per l'assistente automatico. La definizione di un operatore è facoltativa. Un operatore può essere una qualsiasi delle altre destinazioni in questo elenco.

Gli operatori automatici offrono opzioni di routing delle chiamate separate per le chiamate ricevute all'esterno delle ore lavorative e delle festività. Il routing delle chiamate after-hours consente di visualizzare tutte le opzioni elencate sopra, mentre il routing delle chiamate per le festività consente solo di reindirizzare o disconnettere una chiamata, ma senza opzioni di tasti di scelta rapida.

Chiamate code posizionare il chiamante in attesa fino a quando non è disponibile un agente assegnato alla coda per eseguire la chiamata. Esistono due situazioni in cui un chiamante potrebbe essere diretto fuori dalla coda:

- **Overflow** delle chiamate: se il numero di chiamate nella coda supera il limite impostato, i nuovi chiamanti vengono reindirizzati fuori dalla coda.
- **Timeout chiamata** : se un chiamante è stato nella coda più a lungo dell'impostazione di timeout configurata, viene reindirizzato dalla coda.

Le chiamate reindirizzate da una coda possono essere inviate a tutte le destinazioni di routing delle chiamate elencate sopra, ad eccezione di un operatore. Le code di chiamata non hanno operatori, ma è possibile reindirizzare i chiamanti alla stessa destinazione di un operatore configurato per un operatore automatico.

L'esempio seguente mostra un esempio di routing delle chiamate con gli operatori automatici e le code di chiamata.

![Diagramma del routing delle chiamate con gli operatori automatici e le code di chiamata](media/attendant-and-queue-call-routing.png)

Nell'esempio precedente:

- Il tasto zero (0) reindirizza i chiamanti a un operatore. L'operatore di tale operatore automatico è stato configurato come **persona nell'organizzazione**.
- Il tasto One (1) reindirizza i chiamanti alla coda delle chiamate di vendita. La coda di chiamata è connessa a un team che contiene il team di vendita assegnato alla coda.
- Il tasto due (2) reindirizza i chiamanti alla coda di chiamata del supporto. La coda di chiamata è connessa a un team che contiene il team di supporto assegnato al team.
- La coda di chiamata di supporto ha un numero di telefono diretto tramite un operatore automatico che interviene. Avendo una risposta all'operatore automatico la linea di supporto consente di separare le ore e il routing delle chiamate per le festività.
- Il tasto tre (3) reindirizza gli utenti a un altro operatore automatico per la directory aziendale. L'operatore automatico della directory aziendale consente ai chiamanti di chiamare gli utenti dell'organizzazione componendo il nome o l'estensione.

Ti consigliamo di creare uno o più diagrammi simili a quelli descritti sopra per mappare il routing delle chiamate. Assicurarsi di includere i seguenti elementi nel diagramma o nella documentazione di accompagnamento:

- Quali operatori automatici avranno accesso diretto tramite numeri di telefono?
- Quali sono i requisiti di routing off-hours e Holiday per ogni operatore automatico?
- L'appartenenza per ogni coda di chiamata. È possibile aggiungere utenti singolarmente o eseguire il mapping della coda a diversi tipi di gruppi. Il mapping di una coda a un team offre un'esperienza più versatile.

Ecco alcune procedure consigliate per il routing delle chiamate:

- Esaminare il sistema di chiamate esistente e analizzare i tipi e la frequenza delle chiamate in arrivo. Usare queste informazioni per informare l'operatore automatico e la struttura delle code di chiamata.
- Inserire le opzioni più comuni prima nel menu per instradare le chiamate il più rapidamente possibile.
- Evitare di connettere i numeri di servizio direttamente alle code di chiamata, a meno che le code non siano disponibili 24/7. Le code di chiamata non consentono la gestione delle chiamate separata per le ore o le festività. Se si vuole avere una coda con un numero diretto, assegnare il numero a un operatore automatico che reindirizza automaticamente la coda durante le ore lavorative.
- Se si ricevono numerose chiamate che richiedono informazioni di base sulla società, ad esempio orari di ufficio, località o indirizzo del sito Web, valutare la possibilità di creare un operatore automatico per rispondere a queste domande con i messaggi registrati.
- Mantieni l'elenco delle voci di menu su cinque o meno. I chiamanti possono avere problemi a ricordare più di cinque opzioni. Usare gli operatori automatici annidati se sono necessarie più opzioni per indirizzare correttamente una chiamata.
- Descrivere il servizio prima di tutto, seguito dall'opzione da premere (ad esempio: per le vendite premere 1) invece che nell'altro modo (ad esempio. Premere 1 per le vendite).
- Terminologia utente che i chiamanti capiranno invece di quello che si può usare internamente.
- Evitare aggiornamenti frequenti per chiamare routing. Se si modificano le opzioni di menu per un operatore automatico in futuro, chiamarlo nelle istruzioni vocali per i primi 30 giorni.

## <a name="getting-started"></a>Introduzione

Dopo aver completato le attività di pianificazione in questo articolo, eseguire la procedura seguente per ottenere gli operatori automatici e le code di chiamata configurate:

1. Ottenere i numeri di servizio necessari per gli operatori automatici e le code di chiamata a cui si vuole accedere tramite chiamata diretta dall'esterno dell'organizzazione. Questo potrebbe includere il [trasferimento di numeri da un altro provider](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o la [richiesta di nuovi numeri di servizio](getting-service-phone-numbers.md).

2. Ottenere un [sistema telefonico-licenza utente virtuale](teams-add-on-licensing/virtual-user.md) per ogni account delle risorse che si prevede di creare. Queste licenze sono gratuite, quindi ti consigliamo di ottenere qualche extra nel caso in cui decidi di apportare modifiche agli account delle risorse in futuro.

3. [Creare un account delle risorse](manage-resource-accounts.md) per ogni operatore automatico e coda di chiamata che si vuole creare. Assegnare a ogni account un sistema telefonico-licenza utente virtuale e, facoltativamente, un numero di servizio.

4. [Creare le festività](set-up-holidays-in-teams.md) per cui si vuole avere un routing delle chiamate separato negli operatori automatici.

5. Facoltativamente, [configurare il parcheggio e il recupero delle chiamate](call-park-and-retrieve.md) se si vuole usare questa funzionalità per agevolare i trasferimenti delle chiamate.

6. Creare i gruppi che si desidera utilizzare per contenere gli agenti di chiamata per le code di chiamata.

7. Se si prevede di consentire la chiamata tramite estensione, verificare di aver aggiunto il numero di interno degli utenti al proprio profilo di Azure Active Directory.

Dopo aver completato la procedura precedente, si è pronti per creare gli operatori automatici e le code di chiamata. Poiché gli operatori automatici e le code di chiamata possono reindirizzare le chiamate tra loro, vedere il diagramma del flusso di lavoro creato per determinare quale operatore automatico o coda di chiamata deve essere creato per primo. Nell'esempio riportato sopra è necessario creare le code di chiamata Sales e Support prima di creare l'operatore automatico principale di Contoso, perché l'operatore automatico principale deve indirizzare i chiamanti alle code di chiamata Sales e support.

Per informazioni su come creare gli operatori automatici e le code di chiamata, vedere gli articoli seguenti:

- [Configurare un operatore automatico](create-a-phone-system-auto-attendant.md)
- [Creare una coda di chiamata](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a>Argomenti correlati

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Creare una coda di chiamata-esercitazione sulle piccole imprese](business-voice/create-a-phone-system-call-queue-smb.md)

[Configurare un operatore automatico-esercitazione sulle piccole imprese](business-voice/create-a-phone-system-auto-attendant-smb.md)
