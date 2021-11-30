---
title: Gestire i criteri delle riunioni per partecipanti e guest
author: CarolynRowe
ms.author: crowe
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
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Informazioni su come gestire le impostazioni dei criteri delle riunioni in Teams per partecipanti e guest.
ms.openlocfilehash: ebbb13d4d0430aee6fadba10b825a6c0cb8ec3b0
ms.sourcegitcommit: 3e724a57e946550f2f61002c8e2de1ec20c9755a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2021
ms.locfileid: "61234304"
---
# <a name="meeting-policy-settings---participants--guests"></a>Impostazioni dei criteri di riunione - Partecipanti e ospiti

<a name="bkmeetingparticipants"> </a>

Queste impostazioni controllano i partecipanti che devono aspettare nella sala di attesa prima di essere ammessi alla riunione e il livello di partecipazione consentito in una riunione.

- [Consenti alle persone anonime di avviare una riunione](#let-anonymous-people-start-a-meeting)
- [Ammetti automaticamente le persone](#automatically-admit-people)
- [Consenti agli utenti che chiamano di ignorare la sala di attesa](#allow-dial-in-users-to-bypass-the-lobby)
- [Didascalie in tempo reale](#live-captions)
- [Chattare nelle riunioni](#chat-in-meetings)

> [!NOTE]
>Le opzioni per partecipare a una riunione variano in base alle impostazioni di ogni gruppo di Teams e al metodo di connessione. Se il gruppo ha le funzionalità di audioconferenza e le usa per la connessione, vedere [Audioconferenza](/microsoftteams/audio-conferencing-in-office-365). Se il gruppo di Teams non ha le funzionalità di audioconferenza, vedere [Partecipare a una riunione in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).


## <a name="let-anonymous-people-start-a-meeting"></a>Consenti alle persone anonime di avviare una riunione

Questa impostazione è un criterio per organizzatore che consente riunioni di conferenza telefonica con accesso esterno senza leader. Questa impostazione controlla se gli utenti con accesso esterno possono partecipare alla riunione in assenza di un utente autenticato dell'organizzazione. Per impostazione predefinita, questa impostazione è disattivata, il che significa che gli utenti con accesso remoto attenderanno nella sala d'attesa finché un utente autenticato dell'organizzazione non partecipa alla riunione.

> [!NOTE]
> Se questa impostazione è disattivata e un utente con accesso esterno accede alla riunione e viene inserito nella sala di attesa, un utente dell'organizzazione deve partecipare alla riunione con un cliente di Teams per consentire l'accesso all'utente dalla sala di attesa. Non sono disponibili controlli di sala di attesa per gli utenti che hanno effettuato l'accesso.

## <a name="automatically-admit-people"></a>Ammetti automaticamente le persone

Questo è un criterio per organizzatore. Questa impostazione controlla se gli utenti si uniscono direttamente a una riunione o restano in sala di attesa finché non vengono ammessi da un utente autenticato. Questa impostazione non si applica agli utenti con accesso esterno.

![Screenshot che mostra una riunione con un utente in sala di attesa.](media/meeting-policies-lobby.png)

 Gli organizzatori di riunioni possono fare clic **Opzioni riunione** nell'invito alla riunione per modificare questa impostazione per ogni riunione pianificata.

> [!NOTE]
> Nelle opzioni della riunione l'impostazione è contrassegnata da "Chi può ignorare la sala di attesa". Se si modifica l'impostazione predefinita per un utente, questa viene applicata a tutte le nuove riunioni organizzate da tale utente e alle riunioni precedenti in cui l'utente non ha modificato le opzioni per le riunioni.
  
|Valore dell'impostazione  |Comportamento di partecipazione |
|---------|---------|
|**Tutti**   |Tutti i partecipanti accedono direttamente alla riunione senza passare dalla sala di attesa. Sono inclusi utenti autenticati, utenti esterni di organizzazioni attendibili (federati), guest e utenti anonimi.     |
|**Utenti dell’organizzazione e guest**     |Gli utenti autenticati all'interno dell'organizzazione, inclusi gli utenti guest, aderiscono direttamente alla riunione senza aspettare nella sala d'attesa. Gli utenti di organizzazioni attendibili e gli utenti anonimi aspettano nella sala d'attesa. Questa è l'impostazione predefinita.    |
|**Utenti dell'organizzazione, organizzazioni attendibili e guest**     |Gli utenti autenticati all'interno dell'organizzazione, inclusi gli utenti guest e gli utenti di organizzazioni attendibili, accedono direttamente alla riunione senza passare dalla sala di attesa.  Gli utenti anonimi attendono nella sala di attesa.   |
|**Utenti dell’organizzazione**    |Gli utenti autenticati dall'interno dell'organizzazione aderiscono alla riunione direttamente senza aspettare nella sala d'attesa.  Gli utenti di organizzazioni attendibili, utenti guest e utenti anonimi aspettano nella sala d'attesa.          |
|**Solo organizzatore**    |Solo gli organizzatori possono accedere direttamente alla riunione senza passare dalla sala di attesa. Tutti gli altri utenti, inclusi gli utenti autenticati all'interno dell'organizzazione, gli utenti guest, gli utenti di organizzazioni attendibili e gli utenti anonimi devono attendere nella sala d'attesa. Nella pagina Teams opzioni della riunione del cliente viene visualizzato come "Solo io".          |
|**Solo utenti invitati**    |Solo gli utenti invitati e gli organizzatori della riunione possono partecipare alla riunione direttamente senza aspettare nella sala d'attesa. Tutti gli altri utenti, inclusi gli utenti autenticati all'interno dell'organizzazione, gli utenti guest, gli utenti di organizzazioni attendibili e gli utenti anonimi devono attendere nella sala d'attesa. Nella pagina Teams opzioni per le riunioni del cliente viene visualizzato come "Persone invitate". Gli utenti aggiunti come parte di un gruppo di distribuzione doranno passare attraverso la sala d'attesa.      |

 > [!NOTE]
> Le organizzazioni attendibili sono domini con cui è consentita la comunicazione federata Teams. Se si abilita **Consenti l'accesso** esterno a tutti i domini esterni nell'interfaccia di amministrazione di Teams, qualsiasi utente autenticato all'interno di Teams dell'organizzazione verrà considerato attendibile. Se si sceglie di specificare domini esterni consentiti e bloccare tutti gli altri, i domini consentiti diventano organizzazioni attendibili. Qualsiasi dominio bloccato viene considerato non un'organizzazione attendibile.

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Consenti agli utenti che chiamano di ignorare la sala di attesa

Questo è un criterio per organizzatore. Questa impostazione consente di controllare se le persone che effettuano l'accesso tramite telefono si uniscono direttamente alla riunione oppure aspettano in sala d'attesa, indipendentemente dall'impostazione **Ammetti automaticamente le persone**. Per impostazione predefinita, questa impostazione è disattivata. Se questa impostazione è disattivata, gli utenti con accesso esterno attenderanno nella sala di attesa finché un utente dell'organizzazione non accede alla riunione con un client di Teams e consente loro di accedere. Quando questa impostazione è attivata, gli utenti con accesso esterno potranno accedere automaticamente alla riunione quando un utente dell'organizzazione accede alla riunione.

> [!NOTE]
> Se un utente con accesso esterno partecipa a una riunione prima che un utente dell'organizzazione acceda alla riunione, verrà inserito nella sala di attesa finché un utente dell'organizzazione non accede alla riunione usando un client di Teams e gli consente di accedere. Se si modifica l'impostazione predefinita per un utente, questa viene applicata a tutte le nuove riunioni organizzate da tale utente e alle riunioni precedenti in cui l'utente non ha modificato le opzioni per le riunioni.

## <a name="live-captions"></a>Didascalie in tempo reale

Questa impostazione è un criterio per utente e si applica durante una riunione. Questa impostazione controlla se, l'opzione **Abilita i sottotitoli in tempo reale** è disponibile nelle riunioni a cui l'utente partecipa, per l'attivazione e la disattivazione dei sottotitoli in tempo reale.  

![Screenshot che mostra l'opzione Abilita i sottotitoli in tempo reale.](media/meeting-policies-live-captions.png)

|Valore dell'impostazione |Comportamento  |
|---------|---------|
|**Disabilitato, ma l'organizzatore può eseguire l'override**     | I sottotitoli in tempo reale non sono attivati automaticamente per l'utente durante una riunione. L'utente vede l'opzione **Abilita i sottotitoli in tempo reale** nel menu di riversamento (**...**). Questa è l'impostazione predefinita. |
|**Disattiva**     | I sottotitoli in tempo reale sono disabilitati per l'utente durante le riunioni. L'utente non ha a disposizione l'opzione per attivarli.          |

<a name="bkcontentsharing"> </a>

## <a name="chat-in-meetings"></a>Chattare nelle riunioni

Questa impostazione è un'impostazione per partecipante. Questa impostazione determina se la chat della riunione è consentita nella riunione dell'utente.

<a name="bkparticipantsandguests"> </a>



## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)
- [Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams](meeting-policies-restricted-anonymous-access.md)
