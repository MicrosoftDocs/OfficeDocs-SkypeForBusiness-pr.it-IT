---
title: Gestire i criteri delle riunioni per la condivisione di contenuti
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: Informazioni su come gestire le impostazioni dei criteri delle riunioni in Teams per la condivisione del contenuto.
ms.openlocfilehash: 6fc70359c8ef2dc06c02b68ce35977e5e45ef686cd8b44de558a1868ce7cb47e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285825"
---
# <a name="meeting-policy-settings---content-sharing"></a>Impostazioni dei criteri di riunione - Condivisione di contenuti

<a name="bkcontentsharing"> </a>

Questo articolo descrive le impostazioni dei criteri di riunione seguenti relative alla condivisione del contenuto:

- [Modalità condivisione schermo](#screen-sharing-mode)
- [Consenti a un partecipante di fornire o richiedere il controllo](#allow-a-participant-to-give-or-request-control)
- [Consenti a un partecipante esterno di fornire o richiedere il controllo](#allow-an-external-participant-to-give-or-request-control)
- [Consenti la condivisione di PowerPoint](#allow-powerpoint-sharing)
- [Consenti la lavagna](#allow-whiteboard)
- [Consenti note condivise](#allow-shared-notes)

## <a name="screen-sharing-mode"></a>Modalità condivisione schermo

Questa impostazione è una combinazione di criteri per organizzatore e per utente. Questa impostazione controlla se la condivisione di desktop e finestre è consentita nella riunione dell'utente. I partecipanti alla riunione a cui non sono assegnati criteri, ad esempio i partecipanti anonimi, guest, B2B e federati, ereditano i criteri dell'organizzatore della riunione.

|Valore dell'impostazione |Comportamento  |
|---------|---------|
|**Schermo intero**    | È consentita la condivisione completa del desktop e delle applicazioni nella riunione |
|**Applicazione singola**   | È consentita la condivisione di applicazioni nella riunione        |
|**Disattiva**     |Condivisione dello schermo e delle applicazioni disattivata nella riunione.       |

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione |Modalità condivisione schermo |
|---------|---------|---------|
|Daniela  | Globale   | Schermo intero |
|Amanda   | CriterioRiunionePosizione1  | Disattiva |

Le riunioni ospitate da Daniela consentono ai partecipanti alla riunione di condividere l'intero schermo o una specifica applicazione. Se Amanda partecipa a una riunione di Daniela, non può condividere il suo schermo o una specifica applicazione, perché l'impostazione del suo criterio non lo consente. Nelle riunioni ospitate da Amanda nessuno può condividere lo schermo o una singola applicazione, indipendentemente dal criterio di condivisione dello schermo assegnati.  Di conseguenza, Daniela non può condividere lo schermo o una singola applicazione nelle riunioni di Amanda.  

Al momento, gli utenti non possono riprodurre video o condividere il proprio schermo in una riunione di Teams se usano Google Chrome.

## <a name="allow-a-participant-to-give-or-request-control"></a>Consenti a un partecipante di fornire o richiedere il controllo

Questa impostazione è un criterio per utente. Questa impostazione controlla se l'utente può assegnare il controllo del desktop o della finestra condivisa ad altri partecipanti della riunione. Per concedere il controllo, posizionare il puntatore del mouse nella parte superiore dello schermo.

Se questa impostazione è attivata per l'utente, nella barra superiore di una sessione di condivisione compare l'opzione **Concedi controllo**.

![Screenshot che mostra l'opzione Concedi controllo](media/meeting-policies-give-control.png)

Se l'impostazione è disattivata per l'utente, l'opzione **Concedi controllo** non è disponibile.

![Screenshot che mostra che l'opzione Concedi controllo non è disponibile](media/meeting-policies-give-control-not-available.png)

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti a un partecipante di fornire o richiedere il controllo |
|---------|---------|---------|
|Daniela   | Globale   | Attivato       |
|Pio    | CriterioRiunionePosizione1        | Disattivato   |

Daniela può dare il controllo del desktop o della finestra condivisa ad altri partecipanti a una riunione organizzata da Babek. Tuttavia, Babek non può dare il controllo ad altri partecipanti.

Per usare PowerShell per controllare gli utenti autorizzati a concedere il controllo o accettare richieste di controllo, usare il cmdlet AllowParticipantGiveRequestControl.

> [!NOTE]
> Per concedere e assumere il controllo del contenuto condiviso durante la condivisione, entrambe le parti devono usare il client desktop di Teams. Il controllo non è supportato se una delle parti esegue Teams in un browser. Ciò è dovuto a una limitazione tecnica che si prevede di risolvere.

## <a name="allow-an-external-participant-to-give-or-request-control"></a>Consenti a un partecipante esterno di fornire o richiedere il controllo

Questa impostazione è un criterio per utente. Se un'organizzazione ha impostato questo criterio per un utente, non controlla cosa possono fare i partecipanti esterni, indipendentemente da ciò che l'organizzatore della riunione ha impostato. Questo parametro controlla se i partecipanti esterni possono ricevere o richiedere il controllo dello schermo del relatore, a seconda delle impostazioni configurate dal relatore nei criteri di riunione dell'organizzazione. I partecipanti esterni nelle riunioni di Teams possono essere classificati come segue:  

- Utente anonimo
- Utenti guest  
- Utente B2B
- Utente federato  

La possibilità per gli utenti federati di concedere il controllo a utenti esterni durante la condivisione è controllata dall'impostazione **Consenti a un partecipante esterno di fornire o richiedere il controllo** della loro organizzazione.

Per usare PowerShell per controllare i partecipanti esterni autorizzati a concedere il controllo o accettare richieste di controllo, usare il cmdlet AllowExternalParticipantGiveRequestControl.

### <a name="allow-powerpoint-sharing"></a>Consenti la condivisione di PowerPoint

Questo è un criterio per utente. Questa impostazione controlla se l'utente può condividere le presentazioni di PowerPoint in una riunione. Gli utenti esterni, inclusi gli utenti anonimi, guest e federati, ereditano i criteri dell'organizzatore della riunione.

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti la condivisione di PowerPoint |
|---------|---------|---------|
|Daniela   | Globale   | Attivato       |
|Amanda   | CriterioRiunionePosizione1        | Disattivato   |

Amanda non può condividere le presentazioni di PowerPoint nelle riunioni, anche se è l'organizzatrice della riunione. Daniela può condividere le presentazioni di PowerPoint anche se la riunione è organizzata da Amanda. Amanda può visualizzare le presentazioni di PowerPoint condivise da altri nella riunione, anche se non può condividere presentazioni di PowerPoint.

## <a name="allow-whiteboard"></a>Consenti la lavagna

Questa impostazione è un criterio per utente. Questa impostazione controlla se un utente può condividere la lavagna in una riunione. Gli utenti esterni, inclusi gli utenti anonimi, B2B e federati, ereditano i criteri dell'organizzatore della riunione.

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti la lavagna|
|---------|---------|---------|
|Daniela   | Globale   | Attivato       |
|Amanda   | CriterioRiunionePosizione1        | Disattivato   |

Amanda non può condividere la lavagna in una riunione, anche se è l'organizzatrice della riunione. Daniela può condividere la lavagna anche se una riunione è organizzata da Amanda.  

## <a name="allow-shared-notes"></a>Consenti note condivise

Questa impostazione è un criterio per utente. Questa impostazione controlla se un utente può creare e condividere note in una riunione. Gli utenti esterni, inclusi gli utenti anonimi, B2B e federati, ereditano i criteri dell'organizzatore della riunione. La scheda **Note riunione** è attualmente supportata solo nelle riunioni con meno di 20 partecipanti.

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti note condivise |
|---------|---------|---------|
|Daniela   | Globale   | Attivato       |
|Amanda   | CriterioRiunionePosizione1 | Disattivato |

Daniela può creare note nelle riunioni di Amanda, mentre Amanda non può creare note in alcuna riunione.




## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare i criteri agli utenti in Teams](assign-policies.md)
- [Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams](meeting-policies-restricted-anonymous-access.md)
