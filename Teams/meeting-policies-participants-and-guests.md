---
title: Gestire i criteri delle riunioni per partecipanti e guest
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
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Informazioni su come gestire le impostazioni dei criteri delle riunioni in Teams per partecipanti e guest.
ms.openlocfilehash: 51d121ab9c537e6ba304045e47b6e875cd98afd6
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598724"
---
# <a name="meeting-policy-settings---participants--guests"></a>Impostazioni dei criteri di riunione - Partecipanti e ospiti

<a name="bkmeetingparticipants"> </a>

Queste impostazioni controllano i partecipanti che devono aspettare nella sala di attesa prima di essere ammessi alla riunione e il livello di partecipazione consentito in una riunione.

- [Consenti alle persone anonime di avviare una riunione](#let-anonymous-people-start-a-meeting)
- [Ammetti automaticamente le persone](#automatically-admit-people)
- [Consenti agli utenti che chiamano di ignorare la sala di attesa](#allow-dial-in-users-to-bypass-the-lobby)
- [Abilita i sottotitoli in tempo reale](#enable-live-captions)
- [Consenti l'uso della chat nelle riunioni](#allow-chat-in-meetings)

> [!NOTE]
>Le opzioni per partecipare a una riunione variano in base alle impostazioni di ogni gruppo di Teams e al metodo di connessione. Se il gruppo ha le funzionalità di audioconferenza e le usa per la connessione, vedere [Audioconferenza](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365). Se il gruppo di Teams non ha le funzionalità di audioconferenza, vedere [Partecipare a una riunione in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

## <a name="let-anonymous-people-start-a-meeting"></a>Consenti alle persone anonime di avviare una riunione

Questa impostazione è un criterio per organizzatore che consente riunioni di conferenza telefonica con accesso esterno senza leader. Questa impostazione controlla se gli utenti con accesso esterno possono partecipare alla riunione in assenza di un utente autenticato dell'organizzazione. Per impostazione predefinita, questa impostazione è disattivata, il che significa che gli utenti con accesso remoto attenderanno nella sala d'attesa finché un utente autenticato dell'organizzazione non partecipa alla riunione.

> [!NOTE]
> Se questa impostazione è disattivata e un utente con accesso esterno accede alla riunione e viene inserito nella sala di attesa, un utente dell'organizzazione deve partecipare alla riunione con un cliente di Teams per consentire l'accesso all'utente dalla sala di attesa. Non sono disponibili controlli di sala di attesa per gli utenti che hanno effettuato l'accesso.

## <a name="automatically-admit-people"></a>Ammetti automaticamente le persone

Questo è un criterio per organizzatore. Questa impostazione controlla se gli utenti si uniscono direttamente a una riunione o restano in sala di attesa finché non vengono ammessi da un utente autenticato. Questa impostazione non si applica agli utenti con accesso esterno.

![Screenshot che mostra una riunione con un utente in sala di attesa](media/meeting-policies-lobby.png)

 Gli organizzatori di riunioni possono fare clic **Opzioni riunione** nell'invito alla riunione per modificare questa impostazione per ogni riunione pianificata.

> [!NOTE]
> Questa opzione della riunione è denominata "Chi può evitare la sala di attesa?". Se si modifica l'impostazione predefinita per un utente, questa viene applicata a tutte le nuove riunioni organizzate da tale utente e alle riunioni precedenti in cui l'utente non ha modificato le opzioni per le riunioni.
  
|Valore dell'impostazione  |Comportamento di partecipazione |
|---------|---------|
|**Tutti**   |Tutti i partecipanti accedono direttamente alla riunione senza passare dalla sala di attesa. Sono inclusi utenti autenticati, utenti esterni di organizzazioni attendibili (federati), guest e utenti anonimi.     |
|**Tutti gli utenti dell'organizzazione e delle organizzazioni federate**     |Gli utenti autenticati all'interno dell'organizzazione, inclusi gli utenti guest e gli utenti di organizzazioni attendibili, accedono direttamente alla riunione senza passare dalla sala di attesa.  Gli utenti anonimi attendono nella sala di attesa.   |
|**Tutti gli utenti dell'organizzazione**    |Gli utenti autenticati all'interno dell'organizzazione, inclusi gli utenti guest, accedono direttamente alla riunione senza passare dalla sala di attesa.  Gli utenti di organizzazioni attendibili e gli utenti anonimi attendono nella sala di attesa. Questa è l'impostazione predefinita.           |
|**Solo organizzatore**    |Solo gli organizzatori possono accedere direttamente alla riunione senza passare dalla sala di attesa. Tutti gli altri utenti, inclusi quelli autenticati all'interno dell'organizzazione, gli utenti guest, gli utenti di organizzazioni attendibili e gli utenti anonimi devono attendere nella sala di attesa.           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Consenti agli utenti che chiamano di ignorare la sala di attesa

Questo è un criterio per organizzatore. Questa impostazione consente di controllare se le persone che effettuano l'accesso tramite telefono si uniscono direttamente alla riunione oppure aspettano in sala d'attesa, indipendentemente dall'impostazione **Ammetti automaticamente le persone**. Per impostazione predefinita, questa impostazione è disattivata. Quando questa impostazione è disattivata, gli utenti con accesso remoto attenderanno nella sala d'attesa finché un utente dell'organizzazione non partecipa alla riunione con un client teams e non li ammette. Quando questa impostazione è attivata, gli utenti con accesso esterno potranno accedere automaticamente alla riunione quando un utente dell'organizzazione accede alla riunione.

> [!NOTE]
> Se un utente con accesso esterno partecipa a una riunione prima che un utente dell'organizzazione acceda alla riunione, verrà inserito nella sala di attesa finché un utente dell'organizzazione non accede alla riunione usando un client di Teams e gli consente di accedere. Se si modifica l'impostazione predefinita per un utente, questa viene applicata a tutte le nuove riunioni organizzate da tale utente e alle riunioni precedenti in cui l'utente non ha modificato le opzioni per le riunioni.

## <a name="enable-live-captions"></a>Abilita i sottotitoli in tempo reale

Questa impostazione è un criterio per utente e si applica durante una riunione. Questa impostazione controlla se, l'opzione **Abilita i sottotitoli in tempo reale** è disponibile nelle riunioni a cui l'utente partecipa, per l'attivazione e la disattivazione dei sottotitoli in tempo reale.  

![Screenshot che mostra l'opzione Abilita i sottotitoli in tempo reale](media/meeting-policies-live-captions.png)

|Valore dell'impostazione |Comportamento  |
|---------|---------|
|**Disabilitato, ma l'organizzatore può eseguire l'override**     | I sottotitoli in tempo reale non sono attivati automaticamente per l'utente durante una riunione. L'utente vede l'opzione **Abilita i sottotitoli in tempo reale** nel menu di riversamento (**...**). Questa è l'impostazione predefinita. |
|**Disattiva**     | I sottotitoli in tempo reale sono disabilitati per l'utente durante le riunioni. L'utente non ha a disposizione l'opzione per attivarli.          |

<a name="bkcontentsharing"> </a>

## <a name="allow-chat-in-meetings"></a>Consenti l'uso della chat nelle riunioni 

Questa impostazione è un'impostazione per partecipante. Questa impostazione determina se la chat della riunione è consentita nella riunione dell'utente.

<a name="bkparticipantsandguests"> </a>






## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare i criteri agli utenti in Teams](assign-policies.md)
- [Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams](meeting-policies-restricted-anonymous-access.md)