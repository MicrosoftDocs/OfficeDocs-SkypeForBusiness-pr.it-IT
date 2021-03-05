---
title: Pianificare gli operatori automatici e le code di chiamata di Teams
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
description: Informazioni sugli operatori automatici e sulle code di chiamata e su come usarli per aiutare i chiamanti a spostarsi attraverso un sistema di menu per raggiungere persone o reparti dell'organizzazione.
ms.openlocfilehash: 2944f7b4add49b136d56620f41a2a1afb1a30a92
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460726"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Pianificare gli operatori automatici e le code di chiamata di Teams

Gli operatori automatici consentono di impostare opzioni di menu per instradare le chiamate in base all'input del chiamante. Opzioni di menu, ad esempio "Per vendite, premere 1.  Per i Servizi premere 2", per consentire a un operatore automatico di fornire una serie di scelte che guidano rapidamente i chiamanti verso la destinazione, senza affidarsi a un operatore umano per gestire le chiamate in arrivo.

Le code di chiamata sono aree di attesa per i chiamanti. Per le situazioni in cui i chiamanti devono raggiungere qualcuno con una particolare specializzazione, ad esempio vendite o servizio, invece di una persona specifica, è possibile usare le code di chiamata per collegare i chiamanti al gruppo di agenti che possono aiutarli. I chiamanti vengono messi in attesa finché un agente assegnato alla coda non è disponibile per la chiamata.

Usati insieme, gli operatori automatici e le code di chiamata possono facilmente instradare i chiamanti alla persona o al reparto appropriato dell'organizzazione.

## <a name="auto-attendants"></a>Operatori automatici

Lo scopo principale di un operatore automatico è di indirizzare il chiamante a una persona o a un reparto appropriato in base all'input del chiamante alle opzioni di menu fornite. I chiamanti possono essere indirizzati a persone specifiche all'interno dell'organizzazione, alle code di chiamata in cui aspettano di parlare con il successivo agente disponibile o alla segreteria telefonica. È possibile specificare diverse opzioni di instradamento delle chiamate per l'orario di ufficio, gli orari non lavorativi e le festività.

I prompt del menu possono essere creati con la sintesi vocale (prompt generati dal sistema) o caricando un file audio registrato. Il riconoscimento vocale accetta comandi vocali per la navigazione senza mani, ma i chiamanti possono anche utilizzare la tastiera del telefono per navigare nei menu.

Ogni operatore automatico ha una lingua e un fuso orario specifici. Se si fa business in più lingue o in più parti del mondo, è possibile creare tutti gli operatori automatici necessari per ospitare i chiamanti.

Per ogni operatore automatico, puoi configurare un operatore. Anche se è possibile configurare le chiamate operatore in modo che possano essere effettuate verso una varietà di destinazioni, la funzionalità dell'operatore è progettata per consentire ai chiamanti di parlare con una persona specifica dell'organizzazione che può aiutarli.

Gli operatori automatici possono essere configurati in modo da consentire ai chiamanti di eseguire ricerche nell'elenco dell'organizzazione, per nome o per numero di interno. All'interno di un operatore automatico, puoi specificare chi è disponibile per la ricerca in directory scegliendo gruppi di utenti da includere o escludere. Questo ambito è noto come *ambito di chiamata.*

I chiamanti possono raggiungere un operatore automatico tramite numero di telefono diretto, se configurato, oppure essere reindirizzati da un altro operatore automatico o una coda di chiamata.

## <a name="call-queues"></a>Code di chiamata

Una coda di chiamata è analoga a una sala d'attesa di un edificio fisico. I chiamanti aspettano in attesa mentre le chiamate vengono indirizzate agli agenti in coda. Le code di chiamata vengono in genere usate per le funzioni di vendita e di servizio. Tuttavia, le code di chiamata possono essere utilizzate per qualsiasi situazione in cui il numero di chiamate supera la capacità interna dell'utente, ad esempio un addetto alla reception in una struttura occupata.

Le code di chiamata consentono un instradamento specifico delle chiamate nei casi in cui il numero totale di chiamanti in coda o il tempo di attesa supera i limiti specificati. Le chiamate possono essere instradati a persone specifiche, messaggi vocali, altre code di chiamata o operatori automatici.

Come gli operatori automatici, le code di chiamata hanno ognuna un'impostazione di lingua. Puoi utilizzare code di chiamata diverse se fai affari in più lingue. Gli agenti possono essere membri di più code se sono multilingue.

Per ogni coda di chiamata, è possibile specificare se gli agenti in coda possono rifiutare esplicitamente di effettuare le chiamate e se devono essere instradati a loro in base all'indicazione di presenza in Teams.

È possibile assegnare un numero di telefono a una coda di chiamata, tuttavia le code di chiamata non forniscono un instradamento delle chiamate separato per gli orari non lavorativi e le festività. A meno che la coda di chiamata non sia assegnata al personale 24 ore su 24, è consigliabile assegnare il numero di telefono a un operatore automatico che reindirizza alla coda di chiamata durante gli orari di ufficio.

## <a name="prerequisites"></a>Prerequisiti

Per configurare gli operatori automatici e le code di chiamata, sono necessarie le risorse seguenti:

- Un account delle risorse per ogni operatore automatico e coda di chiamata
- Una licenza Sistema telefonico - Utente virtuale per ogni account delle risorse
- Almeno un [numero di servizio Microsoft,](getting-service-phone-numbers.md)un numero di instradamento diretto o un numero ibrido per ogni account di risorsa che si desidera chiamare direttamente
 - Il numero di servizio può essere a numero verde o a numero verde

Gli agenti che ricevono chiamate dalle code di chiamata devono VoIP aziendale utenti online o locali. Inoltre, se le code di chiamata usano numeri di instradamento diretto, gli agenti che devono effettuare conferenze o trasferire chiamate richiedono anche:

- Criterio di instradamento vocale online assegnato se la coda di chiamata usa la modalità di trasferimento
- Una licenza audioconferenza o un criterio di instradamento vocale online assegnato se la coda di chiamata usa la modalità conferenza

Se i tuoi agenti usano l'app Microsoft Teams per le chiamate in coda di chiamata, devono essere in modalità TeamsOnly.

Quando si trasferiscono chiamate a un numero di telefono esterno, l'account della risorsa che esegue il trasferimento (ovvero quello associato all'operatore automatico o alla coda di chiamata) deve avere una licenza Utente virtuale sistema telefonico Microsoft 365 e una delle seguenti:

- Licenza [per un Piano per chiamate](calling-plans-for-office-365.md)
- Criteri [di routing vocale online](manage-voice-routing-policies.md)

> [!NOTE]
> I numeri di servizio di instradamento diretto per l'operatore automatico e le code di chiamata sono supportati solo per gli utenti di Microsoft Teams e gli agenti di chiamata.<br>
> I trasferimenti tra i trunk del Piano per chiamate e i trunk di routing diretto non sono supportati.<br>
> In uno scenario ibrido l'account delle risorse deve essere creato in locale. Per ulteriori informazioni, consulta [Pianificare le code di chiamata cloud.](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-queue)

## <a name="business-decisions"></a>Decisioni aziendali

Prima di impostare gli operatori automatici e le code di chiamata, è opportuno prendere alcune decisioni su come usare queste funzionalità nella propria azienda. Queste decisioni determineranno le impostazioni scelte durante la configurazione degli operatori automatici e delle code di chiamata.

Documentare le risposte a queste domande e fornire le informazioni all'amministratore durante la configurazione.

- Quali lingue sono necessarie? Dove sono necessarie queste lingue, quale reparto o gruppo?
- Vuoi consentire gli input vocali dei chiamanti o solo gli input di composizione?
- È necessario un instradamento delle chiamate separato per fuori orario o festività? Quali sono le ore e le festività?
- Vuoi consentire agli agenti in coda di rifiutare esplicitamente di effettuare chiamate?
- Vuoi che gli agenti nelle code di chiamata o il tuo operatore siano in grado di avere un ID chiamante specifico in caso di chiamata in uscita?
- Si desidera abilitare il [parking delle chiamate](call-park-and-retrieve.md) e il recupero nella propria organizzazione per facilitare il trascino delle chiamate tra le persone o i reparti?
- Per i comandi vocali, vuoi registrare la tua voce o usare la voce generata dal sistema? La voce generata dal sistema è facile da aggiornare.

## <a name="technical-decisions"></a>Decisioni tecniche

Quando si usano operatori automatici e code di chiamata per connettere i chiamanti alle persone dell'organizzazione, ci sono alcune decisioni tecniche da prendere prima di iniziare la configurazione.

È possibile aggiungere agenti alle code di chiamata nei modi seguenti:

- Singoli utenti
- Liste di distribuzione
- Gruppi di sicurezza, inclusi i gruppi di sicurezza abilitati alla posta elettronica
- Gruppi o team di Microsoft 365

Se necessario, è possibile usare una combinazione di queste opzioni per ogni coda. I gruppi che hanno un indirizzo e-mail possono essere utilizzati per la segreteria telefonica. L'uso di Teams offre una serie di vantaggi, tra cui l'archiviazione di file condivisi e la chat tra agenti, una cassetta postale comune in cui è possibile ricevere i messaggi vocali e una piattaforma estensibile che può includere l'integrazione con le applicazioni line-of-business o con Power Apps.

Ti consigliamo di scegliere una strategia per aggiungere agenti di chiamata alle code prima di iniziare la configurazione.

Se hai già un'infrastruttura di operatore automatico e coda di chiamata e stai eseguendo la migrazione a Teams, avrai bisogno di un piano per trasferire i numeri di telefono esistenti ai nuovi operatori automatici e alle code di chiamata. Potrebbe essere necessario creare un ordine di [trasferimento per](phone-number-calling-plans/port-order-overview.md) trasferire i numeri da un altro provider. Ti consigliamo di acquisire temporaneamente uno o più nuovi numeri di telefono e testare i flussi dell'operatore automatico e della coda di chiamata prima di passare da un numero all'altro rispetto ai numeri attualmente in servizio.

*La modalità conferenza* è un'opzione nelle code di chiamata che riduce significativamente il tempo necessario per collegare le chiamate VOIP di Teams e le chiamate PSTN a un agente. Per il funzionamento della modalità conferenza, gli agenti in coda di chiamata devono utilizzare uno dei client seguenti:

- La versione più recente del client desktop di Microsoft Teams, dell'app Android o dell'app iOS
  - Telefono Microsoft Teams versione 1449/1.0.94.2020051601 o successiva
  
Impostare gli account di Teams degli agenti sulla modalità solo di Teams. Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di instradamento chiamate.

Ti consigliamo di abilitare la modalità conferenza per le code di chiamata se tutti i tuoi agenti utilizzano client compatibili.

## <a name="plan-your-call-routing-flow"></a>Pianificare il flusso del routing delle chiamate

Come parte del processo di pianificazione, è consigliabile elaborare il routing delle chiamate per l'organizzazione in un diagramma. Il diagramma aiuta a determinare il routing più efficiente per le persone che chiamano l'organizzazione. È anche possibile usare il diagramma per determinare gli operatori automatici e le code di chiamata che è necessario creare, insieme a requisiti correlati come numeri di servizio, licenze e account delle risorse.

Diamo un'occhiata a come gli operatori automatici e le code di chiamata instradino le chiamate.

Gli operatori automatici instradano tutte le chiamate in uno dei modi seguenti:

- **Reindirizza** immediatamente: le chiamate possono essere reindirizzate a una delle destinazioni di routing delle chiamate (elencate di seguito) immediatamente dopo aver risposto o dopo un messaggio di saluto iniziale.
- **Reindirizzamento in base alle opzioni** di chiamata: i chiamanti possono essere indirizzati alla scelta tra le opzioni assegnate ai numeri sulla tastiera del telefono, da 0 a 9. A ogni tasto di chiamata può essere assegnata una destinazione di instradamento delle chiamate.
- **Chiamare le** persone per nome o interno: i chiamanti possono essere indirizzati a comporre il numero di interno della persona che stanno cercando di raggiungere nell'elenco dell'organizzazione o digitando il nome della persona.
- **Disconnetti:** un operatore automatico può interrompere la chiamata.

> [!NOTE]
> Un unico operatore automatico può supportare un solo metodo di chiamata per.  Per consentire ai chiamanti di comporre per nome e per numero, sarà necessario creare un operatore automatico che abbia un'opzione per comporre per nome e l'altro per chiamata per interno.  Ognuna di queste opzioni instraderà a operatori automatici separati configurati per questi scenari di chiamata da.

Quando le chiamate vengono reindirizzate da un operatore automatico o una coda di chiamata, puoi scegliere una delle seguenti destinazioni per il routing delle chiamate:

- **Persona nell'organizzazione,** una persona dell'organizzazione che può ricevere chiamate vocali. Può trattarsi di un utente online o di un utente ospitato in locale con Skype for Business Server.
- **App voce:** un altro operatore automatico o una coda di chiamata. Scegliere l'account della risorsa associato alla destinazione.
- **Numero di telefono esterno:** qualsiasi numero di telefono. (Vedere [i dettagli tecnici sul trasferimento esterno).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)
- **Segreteria telefonica:** cassetta postale vocale associata a un gruppo di Microsoft 365 specificato dall'utente.
- **Operatore** (solo operatore automatico): l'operatore definito per l'operatore automatico. La definizione di un operatore è facoltativa. Un operatore può essere una qualsiasi delle altre destinazioni nell'elenco.

Gli operatori automatici offrono opzioni di instradamento delle chiamate separate per le chiamate ricevute al di fuori dell'orario di ufficio e durante le festività. L'instradamento delle chiamate in orario di fine orario consente di utilizzare tutte le opzioni elencate sopra, mentre l'instradamento delle chiamate natalizie consente solo di reindirizzare o disconnettere una chiamata, ma non di utilizzare i tasti di chiamata.

Le code di chiamata metteranno il chiamante in attesa finché un agente assegnato alla coda non sarà disponibile per la chiamata. Esistono due situazioni in cui un chiamante può essere diretto fuori dalla coda:

- **Overflow delle** chiamate: se il numero di chiamate in coda supera il limite impostato, i nuovi chiamanti vengono reindirizzati fuori dalla coda.
- **Timeout di** chiamata: se un chiamante è in coda più a lungo dell'impostazione di timeout configurata, viene reindirizzato fuori dalla coda.

Le chiamate reindirizzate da una coda possono essere inviate a una qualsiasi delle destinazioni di instradamento chiamate elencate sopra ad eccezione di un operatore. Le code di chiamata non sono operatori, ma puoi reindirizzare i chiamanti alla stessa destinazione di un operatore configurato per un operatore automatico.

L'esempio seguente mostra un esempio di routing delle chiamate con operatori automatici e code di chiamata.

![Diagramma del routing delle chiamate con operatori automatici e code di chiamata](media/attendant-and-queue-call-routing.png)

Nell'esempio precedente:

- Il tasto zero (0) reindirizza i chiamanti a un operatore. L'operatore per tale operatore automatico è stato configurato **come Persona nell'organizzazione.**
- Il tasto uno (1) reindirizza i chiamanti alla coda di chiamata di vendita. Questa coda di chiamata è connessa a un team che contiene il team di vendita assegnato alla coda.
- Il tasto due (2) reindirizza i chiamanti alla coda di chiamata di supporto. Questa coda di chiamata è connessa a un team che contiene il team di supporto assegnato al team.
- La coda di chiamata di supporto ha un numero di telefono diretto tramite un operatore automatico intervenendo. La risposta di un operatore automatico alla linea di supporto consente di separare gli orari non lavorativi e l'instradamento delle chiamate in vacanza.
- Il tasto tre (3) reindirizza gli utenti a un altro operatore automatico per l'elenco aziendale. L'operatore automatico directory aziendale consente ai chiamanti di chiamare persone dell'organizzazione componendo il nome o l'interno.

È consigliabile creare uno o più diagrammi simili a quello riportato sopra per mappare il routing delle chiamate. Assicurarsi di includere quanto segue nel diagramma o nella documentazione a corredato:

- Quali operatori automatici avranno accesso diretto tramite numeri di telefono?
- Quali sono i requisiti di instradamento fuori orario e vacanze per ogni operatore automatico?
- L'appartenenza per ogni coda di chiamata. È possibile aggiungere utenti singolarmente o mappare la coda a diversi tipi di gruppi. L'associazione di una coda a un team offre un'esperienza più versatile.

Ecco alcune procedure consigliate per l'instradamento delle chiamate:

- Esaminare il sistema di chiamate esistente e analizzare i tipi e la frequenza delle chiamate in arrivo. Utilizza queste informazioni per informare il tuo operatore automatico e la struttura della coda di chiamata.
- Inserire le opzioni più comuni nel menu per instradare le chiamate il più rapidamente possibile.
- Evita di connettere i numeri di servizio direttamente alle code di chiamata, a meno che non siano disponibili 24 ore su 24, 7 giorni su 7. Le code di chiamata non consentono una gestione separata delle chiamate per orari non lavorativi o vacanze. Se desideri avere una coda con un numero diretto, assegna il numero a un operatore automatico che reindirizza automaticamente alla coda durante gli orari di ufficio.
- Se ricevi numerose chiamate che richiedono informazioni di base sulla tua azienda, come l'orario di ufficio, la posizione o l'indirizzo del sito Web, puoi creare un operatore automatico per rispondere a queste domande con messaggi registrati.
- Mantenere l'elenco delle voci di menu su un valore inferiore a cinque. I chiamanti possono avere difficoltà a ricordare più di cinque opzioni. Usare operatori automatici annidati se sono necessarie più opzioni per instradare correttamente una chiamata.
- Descrivere prima il servizio, seguito dall'opzione da premere (ad esempio: Per vendite premere 1) invece del contrario (ad esempio. Premere 1 per Vendite).
- La terminologia utente sarà comprensibile per i chiamanti anziché per quanto possibile usare internamente.
- Evitare frequenti aggiornamenti al routing delle chiamate. Se in futuro cambi le opzioni di menu per un operatore automatico, chiamali nei prompt vocali per i primi 30 giorni.

## <a name="getting-started"></a>Introduzione

Dopo aver completato le attività di pianificazione in questo articolo, seguire questa procedura per configurare gli operatori automatici e le code di chiamata:

1. Ottieni i numeri di servizio necessari per gli operatori automatici e le code di chiamata che desideri siano accessibili componendo direttamente dall'esterno dell'organizzazione. Può includere il [trasferimento di numeri da un altro provider](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o la richiesta di nuovi numeri di [servizio.](getting-service-phone-numbers.md)

2. Ottenere una [licenza Sistema telefonico - Utente virtuale](teams-add-on-licensing/virtual-user.md) per ogni account delle risorse che si prevede di creare. Queste licenze sono gratuite, quindi ti consigliamo di ottenere qualche ulteriore prodotto se decidi di apportare modifiche agli account delle risorse in futuro.

3. [Crea un account delle risorse](manage-resource-accounts.md) per ogni operatore automatico e coda di chiamata che desideri creare. Assegnare a ogni account un Sistema telefonico - Licenza Utente virtuale e, facoltativamente, un numero di servizio.

4. [Creare le festività](set-up-holidays-in-teams.md) per cui si vuole impostare l'instradamento delle chiamate separato negli operatori automatici.

5. Facoltativamente, [impostare il parco chiamate e il](call-park-and-retrieve.md) recupero se si vuole usare questa caratteristica per facilitare i trasferimenti di chiamata.

6. Creare i gruppi da usare per contenere gli agenti di chiamata per le code di chiamata.

7. Se si prevede di consentire la chiamata per interno, verificare di aver aggiunto il numero di interno degli utenti al loro profilo Azure Active Directory.

Una volta completata la procedura precedente, sei pronto per creare gli operatori automatici e le code di chiamata. Poiché gli operatori automatici e le code di chiamata possono reindirizzare le chiamate tra loro, fai riferimento al diagramma del flusso di lavoro che hai creato per determinare quale operatore automatico o coda di chiamata deve essere creato per primo. Nell'esempio del diagramma precedente, creare le code di chiamata di vendita e supporto prima di creare l'operatore automatico principale di Contoso perché l'operatore automatico principale deve indirizzare i chiamanti alle code di chiamata di vendita e di supporto.

Consulta gli articoli seguenti per informazioni su come creare operatori automatici e code di chiamata:

- [Impostare un operatore automatico](create-a-phone-system-auto-attendant.md)
- [Creare una coda di chiamata](create-a-phone-system-call-queue.md)

## <a name="related-topics"></a>Argomenti correlati

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Creare una coda di chiamata - esercitazione per piccole aziende](business-voice/create-a-phone-system-call-queue-smb.md)

[Configurare un operatore automatico - esercitazione aziendale di piccole dimensioni](business-voice/create-a-phone-system-auto-attendant-smb.md)
