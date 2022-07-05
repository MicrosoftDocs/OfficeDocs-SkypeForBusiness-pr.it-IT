---
title: Pianificare gli operatori automatici di Teams e le code di chiamata
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
description: Informazioni su operatori automatici e code di chiamata e su come usarli per aiutare i chiamanti a spostarsi in un sistema di menu per raggiungere persone o reparti dell'organizzazione.
ms.openlocfilehash: 1f439ca0a6eb9ff3487582253cdd0aad7b2fad6c
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/05/2022
ms.locfileid: "66616082"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>Pianificare gli operatori automatici di Teams e le code di chiamata

Gli operatori automatici consentono di impostare le opzioni di menu per instradare le chiamate in base all'input del chiamante. Opzioni di menu per un operatore automatico, ad esempio "For Sales, press 1--For Services press 2"-- consente a un'organizzazione di fornire una serie di scelte che guidano rapidamente i chiamanti verso la loro destinazione, senza affidarsi a un operatore umano per gestire le chiamate in arrivo.

Le code di chiamata sono aree di attesa per i chiamanti. Per le situazioni in cui i chiamanti devono raggiungere una persona con una particolare specializzazione, ad esempio vendite o servizi, invece di una persona specifica, è possibile usare le code di chiamata per connettere i chiamanti al gruppo di agenti che possono assisterli. I chiamanti vengono messi in attesa finché un agente assegnato alla coda non è disponibile per la chiamata.

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
- Una licenza gratuita Telefono di Microsoft Teams Resource Account per ogni account di risorsa che sarà direttamente raggiungibile da utenti di Teams o numeri di telefono esterni
- Almeno un [numero di servizio Microsoft](getting-service-phone-numbers.md), un numero di connessione operatore, un numero di routing diretto o un numero ibrido per ogni account di risorsa che desideri sia direttamente componibile da numeri di telefono esterni
  - Il numero di servizio può essere un numero a pagamento o numero verde

> [!NOTE]
> Gli account delle risorse sono disabilitati per l'accesso e devono rimanere tali. La chat e la presenza non sono disponibili per questi account.

Gli agenti che ricevono chiamate dalle code di chiamata devono essere VoIP aziendale abilitati utenti online o locali. Inoltre, se le code di chiamata utilizzano numeri direct routing, gli agenti che devono effettuare conferenze o trasferire chiamate richiedono anche:

- Un criterio di routing vocale online assegnato se la coda di chiamata usa la modalità di trasferimento
- Una licenza per i servizi di audioconferenza o un criterio di routing vocale online assegnato se la coda di chiamata usa la modalità conferenza

Se gli agenti usano l'app Microsoft Teams per le chiamate in coda di chiamata, devono essere in modalità TeamsOnly.

Quando si usa un account di risorsa per scopi di ID riga di chiamata nelle code di chiamata, l'account della risorsa deve avere una licenza Account risorse di Teams Phone e una delle seguenti assegnate:

- Una licenza [per un Piano per chiamate](calling-plans-for-office-365.md) e un numero di telefono assegnato
- Numero di telefono [Operator Connect](operator-connect-plan.md) assegnato
- Un [criterio di routing vocale online](manage-voice-routing-policies.md) (l'assegnazione del numero di telefono è facoltativa quando si usa l'instradamento diretto)

Quando un operatore automatico o una coda di chiamata trasferisce le chiamate a un numero esterno, gli account di risorse specifici come descritto di seguito devono avere una licenza Account di risorse di Teams Phone e una delle seguenti assegnate:

- Una licenza [per un Piano per chiamate](calling-plans-for-office-365.md) e un numero di telefono assegnato
- Numero di telefono [Operator Connect](operator-connect-plan.md) assegnato
- Un [criterio di routing vocale online](manage-voice-routing-policies.md) (l'assegnazione del numero di telefono è facoltativa quando si usa l'instradamento diretto)

Quale account della risorsa assegnare in licenza:
- Assegnare una licenza all'account della risorsa sul primo operatore automatico che riceve la chiamata quando l'operatore automatico si trasferisce ad altri operatori automatici o code di chiamata che trasferiscono chiamate esternamente
- In tutti gli altri scenari di chiamata, assegna una licenza all'account della risorsa dell'operatore automatico o della coda di chiamata che esegue il trasferimento esterno

> [!NOTE]
> Se il Piano per chiamate assegnato all'account della risorsa viene disabilitato o rimosso, verranno utilizzati i [Crediti comunicazioni](what-are-communications-credits.md), se disponibili nel tenant (senza essere assegnati all'account della risorsa). Se non sono presenti Piani per chiamate o Crediti comunicazioni, la chiamata avrà esito negativo.
>
> I numeri di servizio routing diretto per l'operatore automatico e le code di chiamata sono supportati solo per gli utenti di Microsoft Teams e gli agenti di chiamata.
> 
> I trasferimenti tra i trunk Piano per chiamate, Connessione operatore e Routing diretto non sono supportati.
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

Se necessario, è possibile usare una combinazione di queste opzioni per ogni coda. I gruppi con un indirizzo di posta elettronica possono essere usati per la segreteria telefonica. L'uso di Teams offre molti vantaggi, tra cui l'archiviazione di file condivisi e la chat tra agenti, una cassetta postale comune in cui i messaggi vocali possono essere ricevuti e una piattaforma estendibile che può includere l'integrazione con le applicazioni line-of-business o con Power Apps.

È consigliabile scegliere una strategia per l'aggiunta di agenti di chiamata alle code prima di avviare la configurazione.

Se hai già un operatore automatico e un'infrastruttura della coda di chiamata e stai eseguendo la migrazione a Teams, avrai bisogno di un piano per trasferire i tuoi numeri di telefono esistenti ai nuovi operatori automatici e code di chiamata. Potrebbe essere necessario creare un [ordine di trasferimento](phone-number-calling-plans/port-order-overview.md) per spostare i numeri da altri provider. Ti consigliamo di acquisire temporaneamente uno o più nuovi numeri di telefono e testare i flussi dell'operatore automatico e della coda di chiamata prima di passare ai numeri attualmente in servizio.

**La modalità conferenza** è un'opzione nelle code di chiamata che riduce significativamente la quantità di tempo necessaria per connettere le chiamate VOIP e le chiamate PSTN di Teams a un agente. Per il funzionamento della modalità conferenza, gli agenti nella coda di chiamata devono utilizzare uno dei client seguenti:

- L'ultima versione del client desktop di Microsoft Teams, dell'app Android o dell'app iOS
- Microsoft Phone System versione 1449/1.0.94.2020051601 o successiva
  
Impostare gli account di Teams degli agenti sulla modalità solo teams. Gli agenti che non soddisfano i requisiti non sono inclusi nell'elenco di routing delle chiamate.

È consigliabile abilitare la modalità conferenza per le code di chiamata se gli agenti usano tutti client compatibili.

**I piani del flusso di instradamento delle chiamate** aiutano a determinare il routing più efficiente per le persone che chiamano l'organizzazione. Per informazioni su come pianificare il flusso di instradamento delle chiamate, vedere [Pianificare il flusso di instradamento delle chiamate](plan-your-call-routing-flow.md).

## <a name="getting-started"></a>Introduzione

Dopo aver completato le attività di pianificazione in questo articolo, segui questi passaggi per configurare gli operatori automatici e le code di chiamata:

1. Ottieni i numeri di servizio necessari per gli operatori automatici e le code di chiamata che desideri siano accessibili componendo direttamente dall'esterno dell'organizzazione. Può essere incluso il [trasferimento di numeri da un altro provider](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) o [la richiesta di nuovi numeri di servizio](getting-service-phone-numbers.md).

2. Ottenere una [licenza Account risorse di Teams Phone](teams-add-on-licensing/virtual-user.md) per ogni account di risorsa che si prevede di creare. Queste licenze sono gratuite, quindi è consigliabile ottenere alcuni extra nel caso in cui si decida di apportare modifiche agli account delle risorse in futuro.

3. [Crea un account di risorsa](manage-resource-accounts.md) per ogni operatore automatico e coda di chiamata che vuoi creare. Assegnare a ogni account una licenza per l'account di risorse del telefono di Teams e, facoltativamente, un numero di servizio.

4. [Crea le festività](set-up-holidays-in-teams.md) per le quali desideri disporre di routing delle chiamate separato negli operatori automatici.

5. Facoltativamente, [impostare il parcheggio e il recupero delle chiamate](call-park-and-retrieve.md) se si vuole usare questa funzionalità per facilitare i trasferimenti di chiamata.

6. Creare i gruppi da usare per contenere gli agenti di chiamata per le code di chiamata.

7. Se si prevede di consentire la chiamata per estensione, assicurarsi di aver aggiunto il numero di interno degli utenti al profilo di Azure Active Directory.

Dopo aver completato i passaggi precedenti, sei pronto per creare gli operatori automatici e le code di chiamata. Poiché gli operatori automatici e le code di chiamata possono reindirizzare le chiamate reciprocamente, fare riferimento al diagramma del flusso di lavoro creato per determinare quale operatore automatico o coda di chiamata deve essere creato per primo. Nell'esempio riportato nel diagramma precedente, è necessario creare le code di chiamata di vendita e supporto prima di creare l'operatore automatico principale Contoso perché l'operatore automatico principale deve indirizzare i chiamanti alle code di chiamata di vendita e di supporto.

Vedi gli articoli seguenti per informazioni su come creare operatori automatici e code di chiamata:

- [Configurare un operatore automatico](create-a-phone-system-auto-attendant.md)
- [Creare una coda di chiamata](create-a-phone-system-call-queue.md)

Se sono necessarie funzionalità più estese, ad esempio l'integrazione con flussi di lavoro, bot e SMS, considerare [Servizi di comunicazione di Azure](/azure/communication-services/overview).

## <a name="related-topics"></a>Argomenti correlati

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
