---
title: Informazioni di riferimento sulla composizione e il riconoscimento vocale dell'operatore automatico e della coda di chiamata
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
description: Informazioni sulle opzioni di composizione e riconoscimento vocale dell'operatore automatico e della coda di chiamata in Teams.
ms.openlocfilehash: acd3202a3f27beaf40af09422687be490f0695c5
ms.sourcegitcommit: e7f6125d348b6f14eeba28e09d5f1975ad4fde69
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2021
ms.locfileid: "60249688"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Informazioni di riferimento sulla composizione e il riconoscimento vocale dell'operatore automatico e della coda di chiamata

Chiama per nome è una caratteristica di un operatore automatico noto anche come ricerca nella directory. Consente alle persone che chiamano l'operatore automatico di usare la voce (riconoscimento vocale) o le risposte del tastierino del telefono (DTMF) per immettere un nome completo o parziale per cercare nell'elenco aziendale, individuare la persona e quindi trasferire la chiamata. È possibile configurare la chiamata per nome quando si [configurano le impostazioni del flusso di chiamata in un operatore automatico.](create-a-phone-system-auto-attendant.md#call-flow)

## <a name="searching-for-users"></a>Ricerca di utenti

Gli utenti che desideri trovare e raggiungere usando Chiama per nome non devono avere un numero di telefono o avere piani di chiamata **assegnati,** ma devono essere abilitati VoIP aziendale per gli utenti Skype for Business Server chiamata . Chiama per nome sarà anche in grado di trovare e trasferire chiamate a Microsoft Teams utenti ospitati in diversi paesi o aree geografiche per organizzazioni multi-nazionali. Dati i prerequisiti necessari, è possibile abilitare in modo esplicito La chiamata per nome in un operatore automatico.

Chiama per interno è una caratteristica di un operatore automatico che fa anche parte della ricerca nella directory. Consente alle persone che chiamano l'operatore automatico di usare la voce (riconoscimento vocale) o le risposte del tastierino del telefono (DTMF) per immettere l'estensione del telefono dell'utente che sta cercando di raggiungere e quindi trasferire la chiamata. Gli utenti che si vogliono trovare e raggiungere usando Chiama per interno non devono avere un numero di telefono o avere piani di chiamata **assegnati,** ma devono essere abilitati VoIP aziendale per gli utenti Skype for Business Server chiamata . Sarà anche necessario disporre di un piano di chiamata configurato in modo appropriato per gli utenti. La chiamata per interno sarà anche in grado di trovare e trasferire chiamate a Microsoft Teams utenti ospitati in diversi paesi o aree geografiche per organizzazioni multi-nazionali. Dati i prerequisiti necessari, è possibile abilitare esplicitamente La chiamata per interno in un operatore automatico.

### <a name="maximum-directory-size"></a>Dimensione massima dell'elenco

Non ci sono limiti al numero di utenti di Active Directory che possono eseguire chiamate per nome e chiamate per interno quando un chiamante cerca una persona specifica. Un chiamante può immettere nomi parziali o completi (Nome + Cognome e anche Cognome + Nome), ma richiede il numero di interno completo. La dimensione massima dell'elenco dei nomi che un singolo operatore automatico può supportare con il riconoscimento vocale è di 80.000 utenti.
  
|Tipo di ingresso|Formato di ricerca|Numero massimo di utenti di un'organizzazione|
|:-----|:-----|:-----|
|DTMF (immissione con tastiera) |Parziale  <br/> Nome + Cognome  <br/> Cognome + Nome |Nessun limite  |
|Voce (ingresso vocale) |Nome  <br/> Cognome  <br/> Nome + Cognome  <br/> Cognome + Nome  | 80.000 utenti |

> [!NOTE]
> Se si usa Chiama per nome con il riconoscimento vocale, ma Active Directory dell'organizzazione è più grande di 80.000 utenti e non è stato limitato l'ambito di Chiamata per nome usando la funzionalità Ambito di chiamata, la funzione Chiama per nome continuerà a funzionare per i chiamanti usando un tastierino del telefono e gli input vocali saranno disponibili per tutti gli altri scenari. È possibile utilizzare la funzione Ambito di chiamata per limitare i nomi raggiungibili modificando l'ambito di Chiamata per nome per un particolare operatore automatico.
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>Chiamata per nome - Immissione con tastiera (DTMF)
Le persone che chiamano possono usare Chiama per nome per raggiungere gli utenti specificando il nome completo o parziale della persona che stanno cercando di raggiungere. Quando si digita il nome, è possibile usare diversi formati.

Durante la ricerca nell'elenco dell'organizzazione, le persone possono usare il tasto '0' (zero) per indicare uno spazio tra il nome e cognome o viceversa. Quando immettono il nome, gli verrà chiesto di terminare la voce del tastierino con il tasto #. Ad esempio: "Dopo aver immesso il nome della persona che state cercando di raggiungere, premete #". Se vengono trovati più nomi, al chiamante verrà dato un elenco di nomi tra cui scegliere.
  
Le persone possono cercare nomi nell'organizzazione utilizzando i seguenti formati di ricerca sulla tastiera del telefono.
  
|Formato del nome|Tipo di ricerca|Esempio|Risultato della ricerca|
|:-----|:-----|:-----|:-----|
|Nome + Cognome |Completa  |Amos0Marble# |Amos Marble |
|Cognome + Nome |Completa |Marble0Amos#  |Amos Marble |
|Nome  |Completa   |Amos#   |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus |
|Cognome |Completa |Marble#  |Premere 1 per Amos Marble  <br/> Premere 2 per Mary Marble |
|Nome o Cognome |Parziale |Mar# |Premere 1 per Mary Marble  <br/> Premere 2 per Mary Jones  <br/> Premere 3 per Amos Marcus |
|Nome + Cognome |Parziale |Amos0Mar # |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus |
|Cognome + Nome |Parziale |Mar0Am# |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus |

Ci sono diversi caratteri speciali che vengono utilizzati per la ricerca di persone con la tastiera del telefono. Ad esempio, alla persona verrà chiesto di usare il tasto cancelletto (#), mentre il tasto zero (0) viene usato per uno spazio tra i nomi. Premendo il tasto asterisco (*) verrà ripetuto l'elenco dei nomi corrispondenti.
  
|Carattere speciale della tastiera del telefono|Cosa significa|
|:-----|:-----|
|#   |Carattere terminale quando si immette un nome. |
|0   |Spazio tra i nomi. |
|*    |Ripete l'elenco dei nomi corrispondenti. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Chiamata per nome - Riconoscimento vocale del nome

Gli utenti possono cercare altri utenti nell'organizzazione con la voce (riconoscimento vocale). Possono anche raggiungere chiunque in Active Directory pronunciando il nome completo o parziale della persona che sta cercando di individuare. L'uso di input vocali consente di riconoscere i nomi in vari formati, tra cui Nome, Cognome, Nome + Cognome o Cognome + Nome.
  
È possibile abilitare il riconoscimento vocale per un operatore automatico, ma la voce del tastierino del telefono (DTMF) non è disabilitata. Telefono voce del tastierino numerico può essere usata in qualsiasi momento, anche se il riconoscimento vocale è abilitato sull'operatore automatico.
  
Come per la voce del tastierino del telefono, se vengono trovati più nomi, la persona che chiama sente un elenco di nomi tra cui selezionare.
  
I chiamanti possono pronunciare nomi nei formati seguenti:
  
|Nome con riconoscimento vocale|Tipo di ricerca|Esempio|Risultato della ricerca|
|:-----|:-----|:-----|:-----|
|Nome + Cognome |Completa |Amos Marble |Amos Marble |
|Cognome + Nome |Completa  |Marble Amos |Amos Marble |
|Nome |Completa |Amos |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Amos Jones |
|Cognome |Completa |Marble |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Ben Marble |
|Nome o Cognome |Parziale |Mar |Premere o pronunciare 1 per Mary Marble  <br/> Premere o pronunciare 2 per Mary Jones  <br/> Premere o pronunciare 3 per Amos Marcus |
|Nome + Cognome |Parziale |Amos Mar |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Amos Marcus |


> [!NOTE]
> Il nome di un nuovo utente potrebbe richiedere fino a 36 ore per essere elencato nella directory per Chiamata per nome con riconoscimento vocale a causa di un ritardo nella replica di Active Directory.
  
## <a name="language-support"></a>Supporto della lingua

Il supporto della lingua per la sintesi vocale e il riconoscimento vocale è disponibile in [queste lingue supportate.](create-a-phone-system-auto-attendant-languages.md)

Per il riconoscimento vocale sono disponibili i comandi vocali seguenti: 
  
|Comando vocale| Corrisponde a |
|:-----|:-----|
|Sì | Premere 1 per Sì. |
|No | Premere 2 per No. |
|Ripeti |Ripete l'elenco di opzioni. Premere * sul tastierino numerico per ripetere l'elenco di opzioni. |
|Operatore | Premere 0 per "Operatore" |
|Menu principale  |Porta il chiamante al menu principale dell'operatore automatico. |
|Zero | Premere 0 (per impostazione predefinita, uguale a "Operatore").|
|Uno | Premere 1. |
|Due | Premere 2. |
|Tre| Premere 3.|
|Quattro | Premere 4. |
|Cinque | Premere 5. |
|Sei  | Premere 6. |
|Sette | Premere 7.|
|Otto |Premere 8.|
|Nove  |Premere 9.|

## <a name="related-topics"></a>Argomenti correlati

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](./getting-service-phone-numbers.md)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
