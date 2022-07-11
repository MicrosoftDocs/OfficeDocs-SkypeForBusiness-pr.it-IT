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
description: Informazioni su come gestire le impostazioni dei criteri riunione in Teams per partecipanti e guest.
ms.openlocfilehash: 7f9cb76e12671425ee2b7b0543263195796e04d5
ms.sourcegitcommit: 8d7a926758971bee491d24f23b1ad14f5e5c6f7f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2022
ms.locfileid: "66713354"
---
# <a name="meeting-policy-settings---participants--guests"></a>Impostazioni dei criteri di riunione - Partecipanti e ospiti

<a name="bkmeetingparticipants"> </a>

Queste impostazioni controllano quali partecipanti alla riunione devono attendere nella sala di attesa prima di essere ammessi alla riunione e il livello di partecipazione consentito a una riunione.

- [Consentire a persone anonime di partecipare a una riunione](#let-anonymous-people-join-a-meeting)
- [Consenti alle persone anonime di avviare una riunione](#let-anonymous-people-start-a-meeting)
- [Ammetti automaticamente le persone](#automatically-admit-people)
- [Consenti agli utenti che chiamano di ignorare la sala di attesa](#allow-dial-in-users-to-bypass-the-lobby)
- [Sottotitoli in tempo reale](#live-captions)
- [Chattare nelle riunioni](#chat-in-meetings)

> [!NOTE]
>Le opzioni per partecipare a una riunione variano in base alle impostazioni di ogni gruppo di Teams e al metodo di connessione. Se il gruppo ha le funzionalità di audioconferenza e le usa per la connessione, vedere [Audioconferenza](/microsoftteams/audio-conferencing-in-office-365). Se il gruppo di Teams non ha le funzionalità di audioconferenza, vedere [Partecipare a una riunione in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).

## <a name="let-anonymous-people-join-a-meeting"></a>Consentire a persone anonime di partecipare a una riunione

Questa impostazione per organizzatore consente a chiunque di partecipare alle riunioni come utente anonimo selezionando il collegamento nell'invito alla riunione. Per altre informazioni, vedere [Partecipare a una riunione senza un account di Teams](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508). La possibilità per gli utenti anonimi di partecipare alle riunioni è controllata anche a livello di organizzazione, l'impostazione più restrittiva sarà efficace. Per altre informazioni, vedere [Uso dell'interfaccia di amministrazione di Microsoft Teams per configurare i criteri a livello di organizzazione](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings).

## <a name="let-anonymous-people-start-a-meeting"></a>Consenti alle persone anonime di avviare una riunione

Questa impostazione è un criterio per organizzatore che consente le riunioni di conferenza telefonica con accesso esterno senza leader. Questa impostazione controlla se gli utenti con accesso esterno possono partecipare alla riunione in assenza di un utente autenticato dell'organizzazione. Per impostazione predefinita, questa impostazione è disattivata, il che significa che gli utenti con accesso esterno aspetteranno nella sala di attesa finché un utente autenticato dell'organizzazione non accede alla riunione.

> [!NOTE]
> Se questa impostazione è disattivata e un utente con accesso esterno accede alla riunione e viene inserito nella sala di attesa, un utente dell'organizzazione deve partecipare alla riunione con un cliente di Teams per consentire l'accesso all'utente dalla sala di attesa. Non sono disponibili controlli di sala di attesa per gli utenti che hanno effettuato l'accesso.

## <a name="automatically-admit-people"></a>Ammetti automaticamente le persone

Questo è un criterio per organizzatore. Questa impostazione controlla se le persone accedono direttamente a una riunione o aspettano nella sala di attesa finché non vengono ammesse da un utente autenticato. Questa impostazione non è valida per gli utenti con accesso aperto.

![Screenshot che mostra una riunione con un utente in sala di attesa.](media/meeting-policies-lobby.png)

 Gli organizzatori di riunioni possono fare clic **Opzioni riunione** nell'invito alla riunione per modificare questa impostazione per ogni riunione pianificata.

> [!NOTE]
> Nelle opzioni della riunione l'impostazione è contrassegnata da "Chi può ignorare la sala di attesa". Se si modifica l'impostazione predefinita per un utente, questa viene applicata a tutte le nuove riunioni organizzate da tale utente e alle riunioni precedenti in cui l'utente non ha modificato le opzioni per le riunioni.
  
|Valore dell'impostazione  |Comportamento di partecipazione |
|---------|---------|
|**Tutti**   |Tutti i partecipanti accedono direttamente alla riunione senza passare dalla sala di attesa. Sono inclusi gli utenti autenticati, gli utenti di organizzazioni attendibili, guest e utenti anonimi.     |
|**Utenti dell’organizzazione e guest**     |Gli utenti autenticati all'interno dell'organizzazione, inclusi gli utenti guest, partecipano alla riunione direttamente senza attendere nella sala d'attesa. Gli utenti di organizzazioni attendibili e gli utenti anonimi attendono nella sala di attesa. Questa è l'impostazione predefinita.    |
|**Utenti dell'organizzazione, organizzazioni attendibili e guest**     |Gli utenti autenticati all'interno dell'organizzazione, inclusi gli utenti guest e quelli di organizzazioni attendibili, partecipano alla riunione direttamente senza attendere nella sala di attesa.  Gli utenti anonimi attendono nella sala di attesa.   |
|**Utenti dell’organizzazione**    |Gli utenti autenticati all'interno dell'organizzazione accedono alla riunione direttamente senza attendere nella sala d'attesa.  Gli utenti di organizzazioni attendibili, guest e utenti anonimi aspettano nella sala di attesa.          |
|**Solo organizzatore**    |Solo gli organizzatori possono accedere direttamente alla riunione senza passare dalla sala di attesa. Tutti gli altri utenti, inclusi gli utenti autenticati all'interno dell'organizzazione, gli utenti guest, gli utenti di organizzazioni attendibili e gli utenti anonimi devono attendere nella sala di attesa. Nella pagina delle opzioni delle riunioni client di Teams, viene visualizzato come "Solo io".          |
|**Solo utenti invitati**    |Solo gli utenti invitati e gli organizzatori della riunione possono partecipare alla riunione direttamente senza attendere nella sala d'attesa. Tutti gli altri utenti, inclusi gli utenti autenticati all'interno dell'organizzazione, gli utenti guest, gli utenti di organizzazioni attendibili e gli utenti anonimi devono attendere nella sala di attesa. Nella pagina delle opzioni delle riunioni client di Teams, viene visualizzato come "Persone invitate". Gli utenti aggiunti come parte di un gruppo di distribuzione dovranno passare attraverso la sala di attesa.      |

 > [!NOTE]
> Le organizzazioni attendibili sono domini con cui si consentono comunicazioni federate in Teams. Se si abilita **Consenti tutti i domini esterni** per l'accesso esterno nell'interfaccia di amministrazione di Teams, qualsiasi utente autenticato all'interno di qualsiasi organizzazione teams verrà considerato attendibile. Se si sceglie di specificare domini esterni consentiti e bloccarne tutti gli altri, i domini consentiti diventano organizzazioni attendibili. Qualsiasi dominio bloccato è considerato non un'organizzazione attendibile.

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a>Consenti agli utenti che chiamano di ignorare la sala di attesa

Questo è un criterio per organizzatore. Questa impostazione consente di controllare se le persone che effettuano l'accesso tramite telefono si uniscono direttamente alla riunione oppure aspettano in sala d'attesa, indipendentemente dall'impostazione **Ammetti automaticamente le persone**. Per impostazione predefinita, questa impostazione è disattivata. Se questa impostazione è disattivata, gli utenti con accesso esterno attenderanno nella sala di attesa finché un utente dell'organizzazione non accede alla riunione con un client di Teams e consente loro di accedere. Quando questa impostazione è attivata, gli utenti connessi con accesso automatico parteciperanno alla riunione quando un utente dell'organizzazione partecipa alla riunione con un client di Teams.

> [!NOTE]
> Se un utente con accesso esterno partecipa a una riunione prima che un utente dell'organizzazione acceda alla riunione, verrà inserito nella sala di attesa finché un utente dell'organizzazione non accede alla riunione usando un client di Teams e gli consente di accedere. Se si modifica l'impostazione predefinita per un utente, questa viene applicata a tutte le nuove riunioni organizzate da tale utente e alle riunioni precedenti in cui l'utente non ha modificato le opzioni per le riunioni.

## <a name="live-captions"></a>Sottotitoli in tempo reale

Questa impostazione è un criterio per utente e si applica durante una riunione. Questa impostazione controlla se, l'opzione **Abilita i sottotitoli in tempo reale** è disponibile nelle riunioni a cui l'utente partecipa, per l'attivazione e la disattivazione dei sottotitoli in tempo reale.  

![Screenshot che mostra l'opzione Abilita i sottotitoli in tempo reale.](media/meeting-policies-live-captions.png)

|Valore dell'impostazione |Comportamento  |
|---------|---------|
|**Disabilitato, ma l'organizzatore può eseguire l'override**     | I sottotitoli in tempo reale non sono attivati automaticamente per l'utente durante una riunione. L'utente vede l'opzione **Abilita i sottotitoli in tempo reale** nel menu di riversamento (**...**). Questa è l'impostazione predefinita. |
|**Non abilitato**     | I sottotitoli in tempo reale sono disabilitati per l'utente durante le riunioni. L'utente non ha a disposizione l'opzione per attivarli.          |

<a name="bkcontentsharing"> </a>

## <a name="chat-in-meetings"></a>Chattare nelle riunioni

Questa impostazione è un'impostazione per partecipante. Questa impostazione determina se la chat della riunione è consentita nella riunione dell'utente.

Questa impostazione non si applica alle riunioni del canale. Dopo aver applicato questo criterio di chat della riunione agli utenti, un organizzatore non può eseguire l'override di questo criterio tramite le opzioni della riunione.

|Valore dell'impostazione |Comportamento  |
|---------|---------|
|**Attivala per tutti gli utenti**     | Tutti i partecipanti possono scrivere e visualizzare messaggi di chat. |
|**Disattivala per tutti gli utenti**     | La chat della riunione è disattivata per tutti i partecipanti.  |
|**Attivarlo per tutti gli utenti tranne gli utenti anonimi**     | L'accesso in scrittura alla chat della riunione è disattivato solo per i partecipanti anonimi.  |

<a name="bkparticipantsandguests"> </a>

## <a name="qa-in-meetings"></a>Q&A nelle riunioni

Questo è un criterio per organizzatore. Questa impostazione consente agli amministratori del tenant di Microsoft 365 di abilitare o disabilitare l'esperienza Domande & Risposte (Q&A).

L'impostazione viene applicata quando una riunione viene creata o aggiornata dagli organizzatori. Per impostazione predefinita, questa impostazione è disattivata. Altre informazioni su Q&A [sono disponibili qui](/manage-qna-for-meetings).

Il parametro QnAEngagementMode controlla questo criterio in PowerShell. Q&A possono essere modificati anche all'interno del portale di amministrazione.

|Valore dell'impostazione |Comportamento  |
|---------|---------|
|**Abilitato**     | Gli organizzatori possono aggiungere domande&A durante la creazione di riunioni. |
|**Disattiva**     | Gli organizzatori non avranno la possibilità di aggiungere Q&A durante la creazione di riunioni.  |

## <a name="enable-meeting-policy-settings"></a>Abilitare le impostazioni dei criteri riunione

Per abilitare le impostazioni dei criteri di riunione, è possibile utilizzare [l'interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com/policies/meetings) (**Criteri riunione** > **Modifica un criterio** > **Partecipanti & guest**) o il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) in PowerShell di Teams. 

In questo esempio viene usato PowerShell per modificare i criteri globali per le riunioni e consentire a chiunque di avviare o partecipare a una riunione.

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AutoAdmittedUsers "Everyone" -AllowAnonymousUsersToStartMeeting $True -AllowPSTNUsersToBypassLobby $True
```

Dopo aver configurato un criterio, è necessario applicarlo agli utenti. Se è stato modificato il criterio globale (impostazione predefinita a livello di organizzazione), verrà applicato automaticamente agli utenti. Per applicare le modifiche ai criteri è necessario attendere almeno 4 ore, ma possono essere necessarie fino a 24 ore.


## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)
- [Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams](meeting-policies-restricted-anonymous-access.md)
