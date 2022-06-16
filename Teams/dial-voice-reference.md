---
title: Comando radiale e riferimento per il riconoscimento vocale dell'operatore automatico e della coda di chiamata
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
description: Informazioni sulle opzioni operatore automatico e coda di chiamata e riconoscimento vocale in Teams.
ms.openlocfilehash: 784dcbf16c5122c165dc1a949fa237769c9837d3
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124191"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Comando radiale e riferimento per il riconoscimento vocale dell'operatore automatico e della coda di chiamata

Chiamata per nome o estensione è una funzione dell'operatore automatico che consente ai chiamanti di raggiungere Teams utenti dell'organizzazione. I chiamanti della tastiera del telefono o della voce possono pronunciare o immettere il nome completo o parziale o l'estensione della persona che vogliono raggiungere. L'operatore automatico cercherà nell'elenco aziendale, individua la persona e quindi trasferirà il chiamante a tale persona.  Chiamata per nome o Chiamata per estensione sono opzioni [configurate quando configuri le impostazioni del flusso delle chiamate in un operatore automatico](create-a-phone-system-auto-attendant.md?tabs=call-flow).

## <a name="searching-for-users"></a>Ricerca di utenti

Teams utenti raggiungibili tramite Chiamata per nome **non devono avere un numero di telefono o avere piani per chiamate assegnati, ma devono essere VoIP aziendale abilitati per Skype for Business Server utenti**. Per le organizzazioni multinazionali, Chiamata per nome troverà e trasferirà i chiamanti a Microsoft Teams utenti che si trovano in paesi o aree geografiche diverse.

Teams utenti raggiungibili tramite Chiamata per estensione **non devono avere un numero di telefono o avere piani per chiamate assegnati, ma devono essere VoIP aziendale abilitati per Skype for Business Server utenti**. È anche necessario disporre di un piano di chiamata configurato in modo appropriato per gli utenti. Per le organizzazioni multinazionali, Chiamata per estensione troverà e trasferirà i chiamanti a Microsoft Teams utenti che si trovano in paesi o aree geografiche diverse.

Considerando i prerequisiti coinvolti, Chiamata per nome o estensione deve essere abilitata esplicitamente quando si configura un operatore automatico.

### <a name="maximum-directory-size"></a>Dimensione massima dell'elenco

Non è previsto alcun limite per il numero di utenti di Active Directory Chiamata per nome e Chiamata per estensione può supportare quando un chiamante cerca una persona specifica. Un chiamante può immettere nomi parziali o completi (Nome + Cognome e anche Cognome + Nome), ma ha bisogno del numero di interno completo. La dimensione massima dell'elenco dei nomi che un operatore automatico può supportare usando il riconoscimento vocale è 80.000 utenti.
  
|Tipo di ingresso|Formato di ricerca|Numero massimo di utenti di un'organizzazione|
|:-----|:-----|:-----|
|DTMF (immissione con tastiera) |Parziale  <br/> Nome + Cognome  <br/> Cognome + Nome |Nessun limite  |
|Voce (ingresso vocale) |Firstname  <br/> Lastname  <br/> Nome + Cognome  <br/> Cognome + Nome  | 80.000 utenti |

> [!NOTE]
> Se si usa Chiamata per nome con il riconoscimento vocale, ma active directory dell'organizzazione ha più di 80.000 utenti e non è stato limitato l'ambito di Chiamata per nome con la funzionalità [Ambito](create-a-phone-system-auto-attendant.md?tabs=dial-scope) chiamata, Chiamata per nome continuerà a funzionare per i chiamanti che usano una tastiera del telefono e gli input vocali saranno disponibili per tutti gli altri scenari. È possibile utilizzare la funzione Ambito di chiamata per limitare i nomi raggiungibili modificando l'ambito di Chiamata per nome per un particolare operatore automatico.

### <a name="search-considerations"></a>Considerazioni sulla ricerca

Chiamata per nome esegue prima la ricerca nella directory dell'intera organizzazione prima di applicare gli elenchi Dial Scope Include o Exclude configurati. Se la ricerca iniziale nell'intera directory restituisce più di 100 utenti, gli elenchi Ambito di chiamata non verranno applicati, la ricerca non riuscirà e al chiamante verrà comunicato che sono stati trovati troppi nomi.

## <a name="dial-by-name---keypad-dtmf-entry"></a>Chiamata per nome - Immissione con tastiera (DTMF)

Le persone che chiamano possono usare Chiamata per nome per raggiungere gli utenti specificando il nome completo o parziale della persona che stanno cercando di raggiungere. Esistono vari formati che possono essere usati quando si immette il nome.

Durante la ricerca nell'elenco dell'organizzazione, le persone possono usare il tasto '0' (zero) per indicare uno spazio tra il nome e cognome o viceversa. Quando immettono il nome, gli verrà chiesto di terminare l'immissione sul tastierino numerico con il tasto #. Ad esempio: "Dopo aver immesso il nome della persona che state cercando di raggiungere, premete #". Se vengono trovati più nomi, al chiamante verrà dato un elenco di nomi tra cui scegliere.

> [!NOTE]
> Se dopo l'applicazione di un elenco Includi o Escludi ambito di chiamata rimangono più di 5 nomi, la ricerca non riuscirà e al chiamante verrà comunicato che sono stati trovati troppi nomi.
  
Le persone possono cercare nomi nell'organizzazione utilizzando i seguenti formati di ricerca sulla tastiera del telefono.
  
|Formato del nome|Tipo di ricerca|Esempio|Risultato della ricerca|
|:-----|:-----|:-----|:-----|
|Nome + Cognome |Completa  |Amos0Marble# |Amos Marble |
|Cognome + Nome |Completa |Marble0Amos#  |Amos Marble |
|Firstname  |Completa   |Amos#   |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus |
|Lastname |Completa |Marble#  |Premere 1 per Amos Marble  <br/> Premere 2 per Mary Marble |
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

Le persone possono cercare altre persone nella propria organizzazione con la propria voce (riconoscimento vocale). Possono anche raggiungere chiunque in Active Directory pronunciando il nome completo o parziale della persona che stanno cercando. L'uso degli input vocali riconosce i nomi in vari formati, tra cui Nome, Cognome, Nome + Cognome o Cognome + Nome.
  
Puoi abilitare il riconoscimento vocale per un operatore automatico, ma l'immissione da tastiera del telefono (DTMF) non è disabilitata. Telefono voce della tastiera può essere usata in qualsiasi momento, anche se il riconoscimento vocale è abilitato sull'operatore automatico.
  
Come per l'immissione della tastiera del telefono, se vengono trovati più nomi, la persona che chiama sente un elenco di nomi tra cui selezionare.

> [!NOTE]
> Se dopo l'applicazione di un elenco Includi o Escludi ambito di chiamata rimangono più di 5 nomi, la ricerca non riuscirà e al chiamante verrà comunicato che sono stati trovati troppi nomi.
  
I chiamanti possono pronunciare i nomi nei seguenti formati:
  
|Nome con riconoscimento vocale|Tipo di ricerca|Esempio|Risultato della ricerca|
|:-----|:-----|:-----|:-----|
|Nome + Cognome |Completa |Amos Marble |Amos Marble |
|Cognome + Nome |Completa  |Marble Amos |Amos Marble |
|Firstname |Completa |Amos |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Amos Jones |
|Lastname |Completa |Marble |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Ben Marble |
|Nome o Cognome |Parziale |Mar |Premere o pronunciare 1 per Mary Marble  <br/> Premere o pronunciare 2 per Mary Jones  <br/> Premere o pronunciare 3 per Amos Marcus |
|Nome + Cognome |Parziale |Amos Mar |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Amos Marcus |

> [!NOTE]
> Potrebbero essere richieste fino a 36 ore perché il nome di un nuovo utente sia elencato nella directory per Chiamata per nome con riconoscimento vocale a causa del ritardo della replica di Active Directory.

### <a name="dial-by-extension"></a>Chiamata per estensione

Gli utenti che si desidera rendere disponibili per **Chiamata per estensione** devono avere un'estensione specificata come parte di uno dei seguenti attributi telefonici definiti in Active Directory (e sincronizzati tramite Azure AD Connessione) o Azure Active Directory. Per altre informazioni, vedere [Aggiungere utenti singolarmente o in blocco](/microsoft-365/admin/add-users/add-users) .

- OfficePhone/TelephoneNumber (AD e Azure AD)
- HomePhone (AD)
- Mobile/MobilePhone (AD e Azure AD)
- Altrotelefono (AD)

Il formato richiesto per immettere l'estensione nel campo del numero di telefono dell'utente può essere uno dei formati seguenti:

- *+\<phone number>;estensione=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- Esempio 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- Esempio 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678x5678"
- Esempio 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

È possibile impostare l'estensione nel [interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/) o [nell'interfaccia di amministrazione di Azure Active Directory](https://aad.portal.azure.com). Possono essere necessarie fino a 12 ore prima che le modifiche siano disponibili per gli operatori automatici e le code di chiamata.

## <a name="language-support"></a>Supporto per le lingue

Il supporto delle lingue per la sintesi vocale e il riconoscimento vocale è disponibile in queste [lingue supportate](create-a-phone-system-auto-attendant-languages.md).

Per il riconoscimento vocale sono disponibili i comandi vocali seguenti:
  
|Comando vocale| Corrisponde a |
|:-----|:-----|
|Sì | Premere 1 per Sì. |
|No | Premere 2 per No. |
|Ripeti |Ripete l'elenco di opzioni. Premere * sul tastierino numerico per ripetere l'elenco di opzioni. |
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

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](./getting-service-phone-numbers.md)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
