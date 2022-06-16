---
title: Pianificare il flusso di instradamento delle chiamate per Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
ms.custom:
- Phone System
description: Scopri come pianificare il flusso del routing delle chiamate per gli operatori automatici e le code di chiamata in Microsoft Teams.
ms.openlocfilehash: 3be72f17f876eb694d3b46293f039ccc07d65fbb
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124583"
---
# <a name="plan-your-call-routing-flow"></a>Pianificare il flusso di instradamento delle chiamate

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
