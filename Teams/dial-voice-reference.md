---
title: Operatore automatico e riferimento per la chiamata e il riconoscimento vocale delle code delle chiamate
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
description: Informazioni sulle opzioni per l'operatore automatico e la chiamata della coda di chiamate e il riconoscimento vocale in teams.
ms.openlocfilehash: 3e3e750ff28779fb8fe8765a088c5a65d2a9b1f0
ms.sourcegitcommit: 273f231098799975dc4cf609a68c9944b8072ce1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2020
ms.locfileid: "48818806"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Operatore automatico e riferimento per la chiamata e il riconoscimento vocale delle code delle chiamate

Chiamata per nome è una caratteristica di un operatore automatico noto anche come ricerca directory. Consente alle persone che chiamano l'operatore automatico di usare la voce (riconoscimento vocale) o le risposte del tastierino telefonico (DTMF) per immettere un nome completo o parziale nella directory della società, individuare la persona e quindi fare in modo che venga trasferita la chiamata. Configurare la chiamata per nome quando si [configurano le impostazioni di flusso delle chiamate in un operatore automatico](create-a-phone-system-auto-attendant.md#call-flow).

## <a name="searching-for-users"></a>Ricerca di utenti

Gli utenti che desiderano avere individuato e raggiunto tramite chiamata in base **al nome non devono avere un numero di telefono o avere piani di chiamata assegnati, ma devono avere una licenza per il sistema telefonico se sono utenti online o VoIP aziendale abilitato per gli utenti di Skype for Business Server** . Il comando componi per nome sarà anche in grado di trovare e trasferire le chiamate agli utenti di Microsoft teams ospitati in paesi o aree geografiche diverse per organizzazioni multinazionali. In base ai prerequisiti implicati, è possibile abilitare esplicitamente la chiamata per nome in un operatore automatico.

Dial by Extension è una caratteristica di un operatore automatico che fa anche parte della ricerca nella directory. Consente alle persone che chiamano l'operatore automatico di usare la voce (riconoscimento vocale) o le risposte della tastiera del telefono (DTMF) per immettere l'estensione del telefono dell'utente che sta provando a raggiungere e quindi la chiamata viene trasferita. Gli utenti che desiderano avere individuato e raggiunto tramite dial by Extension  **non devono avere un numero di telefono o avere piani di chiamata assegnati, ma devono avere una licenza per il sistema telefonico se sono utenti online o VoIP aziendale abilitato per gli utenti di Skype for Business Server** . Sarà inoltre necessario disporre di un piano di chiamata configurato in modo appropriato per gli utenti. Dial by Extension sarà anche in grado di trovare e trasferire le chiamate agli utenti di Microsoft teams ospitati in paesi o aree geografiche diverse per organizzazioni multinazionali. In base ai prerequisiti in questione, è possibile abilitare esplicitamente dial by Extension in un operatore automatico.

### <a name="maximum-directory-size"></a>Dimensione massima dell'elenco

Il numero di utenti di Active Directory per nome e dial by Extension può essere supportato quando un chiamante cerca una persona specifica. Un chiamante può immettere nomi parziali o completi (nome + cognome e cognome + nome), ma richiede il numero di interno completo. Le dimensioni massime degli elenchi di nomi che un singolo operatore automatico può supportare con il riconoscimento vocale sono gli utenti di 80.000.
  
|Tipo di ingresso|Formato di ricerca|Numero massimo di utenti di un'organizzazione|
|:-----|:-----|:-----|
|DTMF (immissione con tastiera) |Parziale  <br/> Nome + Cognome  <br/> Cognome + Nome |Nessun limite  |
|Voce (ingresso vocale) |FirstName  <br/> LastName  <br/> Nome + Cognome  <br/> Cognome + Nome  | utenti di 80.000 |

> [!NOTE]
> Se si usa dial by Name con il riconoscimento vocale, ma Active Directory dell'organizzazione è più grande degli utenti di 80.000 e non è stato limitato l'ambito della chiamata per nome tramite la caratteristica ambito di chiamata, dial by Name continuerà a funzionare per i chiamanti usando una tastiera del telefono e gli input vocali saranno disponibili per tutti gli altri scenari. È possibile utilizzare la funzione Ambito di chiamata per limitare i nomi raggiungibili modificando l'ambito di Chiamata per nome per un particolare operatore automatico.
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>Chiamata per nome - Immissione con tastiera (DTMF)
Le persone che chiamano in può usare la chiamata in base al nome per raggiungere gli utenti specificando il nome completo o parziale della persona che sta cercando di raggiungere. Sono disponibili vari formati che possono essere usati quando viene immesso il nome.

Durante la ricerca nell'elenco dell'organizzazione, le persone possono usare il tasto '0' (zero) per indicare uno spazio tra il nome e cognome o viceversa. Quando si immette il nome, verrà chiesto di terminare l'immissione del tastierino numerico con il tasto #. Ad esempio: "Dopo aver immesso il nome della persona che state cercando di raggiungere, premete #". Se vengono trovati più nomi, al chiamante verrà dato un elenco di nomi tra cui scegliere.
  
Le persone possono cercare nomi nell'organizzazione utilizzando i seguenti formati di ricerca sulla tastiera del telefono.
  
|Formato del nome|Tipo di ricerca|Esempio|Risultato della ricerca|
|:-----|:-----|:-----|:-----|
|Nome + Cognome |Completa  |Amos0Marble# |Amos Marble |
|Cognome + Nome |Completa |Marble0Amos#  |Amos Marble |
|FirstName  |Completa   |Amos#   |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus |
|LastName |Completa |Marble#  |Premere 1 per Amos Marble  <br/> Premere 2 per Mary Marble |
|Nome o Cognome |Parziale |Mar# |Premere 1 per Mary Marble  <br/> Premere 2 per Mary Jones  <br/> Premere 3 per Amos Marcus |
|Nome + Cognome |Parziale |Amos0Mar # |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus |
|Cognome + Nome |Parziale |Mar0Am# |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus |

Ci sono diversi caratteri speciali che vengono utilizzati per la ricerca di persone con la tastiera del telefono. Ad esempio, alla persona verrà richiesto di usare il tasto cancelletto (#), mentre il tasto zero (0) viene usato per uno spazio tra i nomi. Premendo il tasto asterisco (*) verrà ripetuto l'elenco dei nomi corrispondenti.
  
|Carattere speciale della tastiera del telefono|Cosa significa|
|:-----|:-----|
|#   |Carattere terminale quando si immette un nome. |
|0   |Spazio tra i nomi. |
|*    |Ripete l'elenco dei nomi corrispondenti. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Chiamata per nome - Riconoscimento vocale del nome

Gli utenti possono cercare altri utenti nella propria organizzazione con la propria voce (riconoscimento vocale). Possono anche raggiungere chiunque in Active Directory dicendo il nome della persona che sta tentando di individuare. L'uso di input vocali può riconoscere i nomi in diversi formati, tra cui nome, cognome, nome + cognome o cognome + nome.
  
È possibile abilitare il riconoscimento vocale per un operatore automatico, ma la voce del tastierino telefonico (DTMF) non è disabilitata. La voce della tastiera del telefono può essere usata in qualsiasi momento anche se il riconoscimento vocale è abilitato per l'operatore automatico.
  
Come per l'immissione della tastiera del telefono, se vengono trovati più nomi, la persona che chiama sente un elenco di nomi da cui selezionare.
  
I chiamanti possono pronunciare i nomi nei formati seguenti:
  
|Nome con il riconoscimento vocale|Tipo di ricerca|Esempio|Risultato della ricerca|
|:-----|:-----|:-----|:-----|
|Nome + Cognome |Completa |Amos Marble |Amos Marble |
|Cognome + Nome |Completa  |Marble Amos |Amos Marble |
|FirstName |Completa |Amos |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Amos Jones |
|LastName |Completa |Marble |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Ben Marble |

> [!NOTE]
> Per un nuovo utente possono essere necessarie fino a 36 ore per avere il nome elencato nella directory per il nome della chiamata tramite il riconoscimento vocale a causa del ritardo di replica di Active Directory.
  
## <a name="language-support"></a>Supporto per le lingue

Le lingue seguenti sono disponibili per la sintesi vocale usata con le istruzioni in uscita:
  
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

L'input di riconoscimento vocale per gli operatori automatici è disponibile nelle lingue seguenti:
  
|-|-|
|:-----|:-----|
|Cinese (ZH)  |Francese (FR)  |
|Inglese (AU)  |Tedesco (DE)  |
|Inglese (CA)  |Italiano (IT)  |
|Inglese (IN)  |Giapponese (JP)  |
|Inglese (UK)  |Portoghese (BR)  |
|Inglese (US)  |Spagnolo (ES)  |
|Francese (CA)   |Spagnolo (MX)  |

I comandi vocali seguenti sono disponibili nelle 14 lingue supportate per il riconoscimento vocale:
  
|Comando vocale| Corrisponde a |
|:-----|:-----|
|Sì | Premere 1 per Sì. |
|No | Premere 2 per No. |
|Ripeti |Ripete l'elenco di opzioni. Premere * sul tastierino per ripetere l'elenco di opzioni. |
|Operatore | Premere 0 per "operator" |
|Menu principale  |Porta il chiamante al menu principale dell'operatore automatico. |
|Zero | Premere 0 (per impostazione predefinita, uguale a "operator").|
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

[Esempio per piccole imprese - Impostare un operatore automatico](/microsoftteams/tutorial-org-aa)
