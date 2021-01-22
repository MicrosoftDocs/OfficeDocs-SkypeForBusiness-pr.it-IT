---
title: Chiamata in coda di chiamata e operatore automatico e riferimento per il riconoscimento vocale
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Informazioni sulle opzioni di composizione e riconoscimento vocale dell'operatore automatico e della coda di chiamata in Teams.
ms.openlocfilehash: 1cb8da2d2e6625de5a1471d1051c1ca51f11bbae
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918962"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Chiamata in coda di chiamata e operatore automatico e riferimento per il riconoscimento vocale

Chiamata per nome è una funzione di un operatore automatico, nota anche come ricerca in elenco. Consente alle persone che chiamano l'operatore automatico di usare le risposte vocali (riconoscimento vocale) o la tastiera del telefono (DTMF) per immettere un nome completo o parziale per cercare nell'elenco aziendale, individuare la persona e poi trasferirla a quella persona. Puoi impostare chiamata per nome quando configura le impostazioni del flusso [delle chiamate in un operatore automatico.](create-a-phone-system-auto-attendant.md#call-flow)

## <a name="searching-for-users"></a>Ricerca di utenti

Gli utenti che si desidera trovare e raggiungere utilizzando Chiamata per nome non sono tenuti ad avere un numero di telefono o disporre di Piani per chiamate assegnati, ma devono essere VoIP aziendale abilitati per gli utenti **di Skype for Business Server.** Chiamata per nome sarà anche in grado di trovare e trasferire le chiamate a utenti di Microsoft Teams ospitati in paesi o aree geografiche diverse per organizzazioni multi-nazionali. Considerando i prerequisiti necessari, abiliti esplicitamente Chiamata per nome in un operatore automatico.

Chiamata per interno è una caratteristica di un operatore automatico che fa anche parte della ricerca in elenco. Consente alle persone che chiamano l'operatore automatico di usare le risposte vocali (riconoscimento vocale) o la tastiera del telefono (DTMF) per immettere l'interno del telefono dell'utente che sta cercando di raggiungere e quindi far trasferire la chiamata a quel operatore. Gli utenti che desideri trovare e raggiungere utilizzando Chiamata per interno non sono tenuti ad avere un numero di telefono o ad avere piani per chiamate assegnati, ma devono essere VoIP aziendale abilitati per gli utenti **di Skype for Business Server.** È inoltre necessario disporre di un piano di chiamata configurato in modo appropriato per gli utenti. Chiamata per interno sarà anche in grado di trovare e trasferire le chiamate a utenti di Microsoft Teams ospitati in diversi paesi o aree geografiche per organizzazioni multi-nazionali. Considerando i prerequisiti necessari, abiliti esplicitamente Chiamata per interno in un operatore automatico.

### <a name="maximum-directory-size"></a>Dimensione massima dell'elenco

Non ci sono limiti al numero di utenti Active Directory che Chiamata per nome e Chiamata per interno possono supportare quando un chiamante cerca una persona specifica. Un chiamante può immettere nomi parziali o completi (Nome + Cognome, e anche Cognome + Nome), ma richiede il numero di interno completo. La dimensione massima dell'elenco nomi che un operatore automatico può supportare utilizzando il riconoscimento vocale è di 80.000 utenti.
  
|Tipo di ingresso|Formato di ricerca|Numero massimo di utenti di un'organizzazione|
|:-----|:-----|:-----|
|DTMF (immissione con tastiera) |Parziale  <br/> Nome + Cognome  <br/> Cognome + Nome |Nessun limite  |
|Voce (ingresso vocale) |Nome  <br/> Cognome  <br/> Nome + Cognome  <br/> Cognome + Nome  | 80.000 utenti |

> [!NOTE]
> Se si utilizza Chiamata per nome con il riconoscimento vocale, ma l'elenco Active Directory dell'organizzazione è più grande di 80.000 utenti e non hai limitato l'ambito di Chiamata per nome utilizzando la funzione Ambito di chiamata, Chiamata per nome continuerà a funzionare per i chiamanti utilizzando una tastiera del telefono e gli input vocali saranno disponibili per tutti gli altri scenari. È possibile utilizzare la funzione Ambito di chiamata per limitare i nomi raggiungibili modificando l'ambito di Chiamata per nome per un particolare operatore automatico.
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>Chiamata per nome - Immissione con tastiera (DTMF)
Le persone che chiamano possono utilizzare Chiamata per nome per raggiungere gli utenti specificando il nome completo o parziale della persona che stanno cercando di raggiungere. Al momento dell'immissione del nome è possibile usare diversi formati.

Durante la ricerca nell'elenco dell'organizzazione, le persone possono usare il tasto '0' (zero) per indicare uno spazio tra il nome e cognome o viceversa. Quando immettono il nome, verrà chiesto di terminare l'immissione da tastiera con il tasto #. Ad esempio: "Dopo aver immesso il nome della persona che state cercando di raggiungere, premete #". Se vengono trovati più nomi, al chiamante verrà dato un elenco di nomi tra cui scegliere.
  
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

Gli utenti possono cercare altre persone nell'organizzazione con la voce (riconoscimento vocale). Possono anche raggiungere chiunque in Active Directory pronunciando il nome completo o parziale della persona che stanno cercando. L'uso di input vocali consente di riconoscere i nomi in vari formati, tra cui Nome, Cognome, Nome + Cognome o Cognome + Nome.
  
Puoi abilitare il riconoscimento vocale per un operatore automatico, ma l'immissione da tastiera del telefono (DTMF) non è disabilitata. L'immissione da tastiera del telefono può essere usata in qualsiasi momento, anche se il riconoscimento vocale è abilitato per l'operatore automatico.
  
Come per l'immissione da tastiera del telefono, se vengono trovati più nomi, la persona che chiama sente un elenco di nomi tra cui selezionare.
  
I chiamanti possono pronunciare i nomi nei seguenti formati:
  
|Nome con riconoscimento vocale|Tipo di ricerca|Esempio|Risultato della ricerca|
|:-----|:-----|:-----|:-----|
|Nome + Cognome |Completa |Amos Marble |Amos Marble |
|Cognome + Nome |Completa  |Marble Amos |Amos Marble |
|Nome |Completa |Amos |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Amos Jones |
|Cognome |Completa |Marble |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Ben Marble |
|Nome o Cognome |Parziale |Mar |Premere o pronunciare 1 per Mary Marble  <br/> Premere o pronunciare 2 per Mary Jones  <br/> Premere o pronunciare 3 per Amos Lordo |
|Nome + Cognome |Parziale |Amos Mar |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Amos Lordo |


> [!NOTE]
> Possono essere necessario fino a 36 ore prima che un nuovo utente abbia il nome elencato nell'elenco Chiamata per nome con riconoscimento vocale a causa di un ritardo di replica di Active Directory.
  
## <a name="language-support"></a>Lingue supportate

Per la sintesi vocale usata con le richieste in uscita sono disponibili le lingue seguenti:
  
|-|-|-|
|:-----|:-----|:-----|
|Arabo (EG)  |Inglese (NZ)  |Coreano (KO)  |
|Cinese (HK)  |Inglese (UK) |Norvegese (NO)  |
|Cinese (TW) |Inglese (US) |Polacco (PL)  |
|Cinese (ZH) |Finlandese (FI) |Portoghese (BR) |
|Danese (DA)  |Francese (CA)  |Portoghese (PT) |
|Olandese (NL)   |Francese (FR)  |Russo (RU) |
|Inglese (AU)  |Tedesco (DE) |Spagnolo (ES)  |
|Inglese (CA)  |Italiano (IT) |Spagnolo (MX)|
|Inglese (IN)  |Giapponese (JP) |Svedese (SV)|

L'input di riconoscimento vocale per gli operatori automatici è disponibile nelle seguenti lingue:
  
|-|-|
|:-----|:-----|
|Cinese (ZH)  |Francese (FR)  |
|Inglese (AU)  |Tedesco (DE)  |
|Inglese (CA)  |Italiano (IT)  |
|Inglese (IN)  |Giapponese (JP)  |
|Inglese (UK)  |Portoghese (BR)  |
|Inglese (US)  |Spagnolo (ES)  |
|Francese (CA)   |Spagnolo (MX)  |

I seguenti comandi vocali sono disponibili nelle 14 lingue supportate per il riconoscimento vocale:
  
|Comando vocale| Corrisponde a |
|:-----|:-----|
|Sì | Premere 1 per Sì. |
|No | Premere 2 per No. |
|Ripeti |Ripete l'elenco di opzioni. Premere * sulla tastiera per ripetere l'elenco di opzioni. |
|Operatore | Premere 0 per "Operatore" |
|Menu principale  |Porta il chiamante al menu principale dell'operatore automatico. |
|Zero | Premere 0 (per impostazione predefinita, come "Operatore").|
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

[Vantaggi offerti dal Sistema telefonico](here-s-what-you-get-with-phone-system.md)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
