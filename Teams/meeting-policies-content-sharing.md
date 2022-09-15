---
title: Gestire i criteri delle riunioni per la condivisione del contenuto
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
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
description: Informazioni su come gestire le impostazioni dei criteri riunione in Teams per la condivisione di contenuti.
ms.openlocfilehash: d3ae689ceb2c864f3f70da91728b8607aaa1e0e2
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706693"
---
# <a name="meeting-policy-settings---content-sharing"></a>Impostazioni dei criteri di riunione - Condivisione di contenuti

<a name="bkcontentsharing"> </a>

Questo articolo descrive le impostazioni dei criteri di riunione seguenti relative alla condivisione del contenuto:

- [Modalità condivisione schermo](#screen-sharing-mode)
- [Consenti a un partecipante di fornire o richiedere il controllo](#allow-a-participant-to-give-or-request-control)
- [I partecipanti esterni possono concedere o richiedere il controllo](#external-participants-can-give-or-request-control)
- [PowerPoint Live](#powerpoint-live)
- [Whiteboard](#whiteboard)
- [Note condivise](#shared-notes)

## <a name="screen-sharing-mode"></a>Modalità condivisione schermo

Questa impostazione è una combinazione di criteri per organizzatore e per utente. Questa impostazione controlla se la condivisione di desktop e finestre è consentita nella riunione dell'utente. I partecipanti alla riunione a cui non sono assegnati criteri, ad esempio i partecipanti esterni, ereditano i criteri dell'organizzatore della riunione.

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

Le riunioni ospitate da Daniela consentono ai partecipanti alla riunione di condividere l'intero schermo o una specifica applicazione. Se Amanda partecipa a una riunione di Daniela, non può condividere il suo schermo o una specifica applicazione, perché l'impostazione del suo criterio non lo consente. Nelle riunioni ospitate da Amanda nessuno può condividere lo schermo o una singola applicazione, indipendentemente dal criterio di condivisione dello schermo assegnati.  Di conseguenza, Daniela non può condividere il suo schermo o una singola applicazione nelle riunioni di Amanda.  

Al momento, gli utenti non possono riprodurre video o condividere il proprio schermo in una riunione di Teams se usano Google Chrome.

## <a name="allow-a-participant-to-give-or-request-control"></a>Consenti a un partecipante di fornire o richiedere il controllo

Questa impostazione è un criterio per utente. Questa impostazione controlla se l'utente può assegnare il controllo del desktop o della finestra condivisa ad altri partecipanti della riunione. Per concedere il controllo, posizionare il puntatore del mouse nella parte superiore dello schermo.

Se questa impostazione è attivata per l'utente, nella barra superiore di una sessione di condivisione compare l'opzione **Concedi controllo**.

![Screenshot che mostra l'opzione Concedi controllo.](media/meeting-policies-give-control.png)

Se l'impostazione è disattivata per l'utente, l'opzione **Concedi controllo** non è disponibile.

![Screenshot che mostra che l'opzione Concedi controllo non è disponibile.](media/meeting-policies-give-control-not-available.png)

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti a un partecipante di fornire o richiedere il controllo |
|---------|---------|---------|
|Daniela   | Globale   | Attivato       |
|Pio    | CriterioRiunionePosizione1        | Disattivato   |

Daniela può dare il controllo del desktop condiviso o della finestra ad altri partecipanti a una riunione organizzata da Babek. Tuttavia, Babek non può dare il controllo ad altri partecipanti.

Per usare PowerShell per controllare gli utenti autorizzati a concedere il controllo o accettare richieste di controllo, usare il cmdlet AllowParticipantGiveRequestControl.

> [!NOTE]
> Per concedere e assumere il controllo del contenuto condiviso durante la condivisione, entrambe le parti devono usare il client desktop di Teams. Il controllo non è supportato se una delle parti esegue Teams in un browser. Ciò è dovuto a una limitazione tecnica che si prevede di risolvere.

## <a name="external-participants-can-give-or-request-control"></a>I partecipanti esterni possono concedere o richiedere il controllo

Questa impostazione è un criterio per utente. Se un'organizzazione ha impostato questo criterio per un utente, non controlla le operazioni consentite ai partecipanti esterni, indipendentemente da ciò che l'organizzatore della riunione ha impostato. Questo parametro controlla se i partecipanti esterni possono ricevere o richiedere il controllo dello schermo del relatore, a seconda delle impostazioni configurate dal relatore nei criteri di riunione dell'organizzazione. I partecipanti esterni nelle riunioni di Teams possono essere classificati come segue:  

- Partecipante anonimo
- Utenti guest
- Utenti con accesso esterno

Se gli utenti con accesso esterno possono concedere il controllo ad altri partecipanti esterni mentre la condivisione è controllata dai **partecipanti esterni possono concedere o richiedere** l'impostazione di controllo nella propria organizzazione.

Per usare PowerShell per controllare i partecipanti esterni autorizzati a concedere il controllo o accettare richieste di controllo, usare il cmdlet AllowExternalParticipantGiveRequestControl.

### <a name="powerpoint-live"></a>PowerPoint Live

Questo è un criterio per utente. Questa impostazione controlla se l'utente può condividere le presentazioni di PowerPoint in una riunione. I partecipanti esterni, inclusi gli utenti anonimi, guest e di accesso esterno, ereditano i criteri dell'organizzatore della riunione.

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |PowerPoint Live |
|---------|---------|---------|
|Daniela   | Globale   | Attivato       |
|Amanda   | CriterioRiunionePosizione1        | Disattivato   |

Amanda non può condividere le presentazioni di PowerPoint nelle riunioni, anche se è l'organizzatrice della riunione. Daniela può condividere le presentazioni di PowerPoint anche se la riunione è organizzata da Amanda. Amanda può visualizzare le presentazioni di PowerPoint condivise da altri nella riunione, anche se non può condividere presentazioni di PowerPoint.

## <a name="whiteboard"></a>Whiteboard

Questa impostazione è un criterio per utente. Questa impostazione controlla se un utente può condividere la lavagna in una riunione. I partecipanti esterni, inclusi gli utenti anonimi, guest e di accesso esterno, ereditano i criteri dell'organizzatore della riunione.

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Whiteboard|
|---------|---------|---------|
|Daniela   | Globale   | Attivato       |
|Amanda   | CriterioRiunionePosizione1        | Disattivato   |

Amanda non può condividere la lavagna in una riunione, anche se è l'organizzatrice della riunione. Daniela può condividere la lavagna anche se una riunione è organizzata da Amanda.

Per abilitare Whiteboard con PowerShell, impostare il cmdlet IsWBFluidEnabled su $true da [Set-SPOTenant.](/powershell/module/sharepoint-online/set-spotenant)

### <a name="annotation"></a>Annotazione

Quando la lavagna è abilitata, gli utenti avranno la possibilità di usare [l'annotazione](/office/use-annotation-while-sharing-your-screen-in-teams), una funzionalità che consente ai partecipanti di collaborare durante la condivisione dello schermo in una riunione di Teams. Se la lavagna è disabilitata, gli utenti non avranno accesso all'annotazione.

## <a name="shared-notes"></a>Note condivise

Questa impostazione è un criterio per utente. Questa impostazione controlla se un utente può creare e condividere note in una riunione. I partecipanti esterni, inclusi utenti anonimi, guest e accesso esterno, ereditano i criteri dell'organizzatore della riunione. La scheda **Note riunione** è attualmente supportata solo nelle riunioni con meno di 20 partecipanti.

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Note condivise |
|---------|---------|---------|
|Daniela   | Globale   | Attivato       |
|Amanda   | CriterioRiunionePosizione1 | Disattivato |

Daniela può creare note nelle riunioni di Amanda, mentre Amanda non può creare note in alcuna riunione.




## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)
- [Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams](meeting-policies-restricted-anonymous-access.md)
