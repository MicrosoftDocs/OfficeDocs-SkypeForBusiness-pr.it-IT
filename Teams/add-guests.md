---
title: Aggiungere un utente guest a un team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: Gli amministratori possono imparare ad aggiungere nuovi Guest a un'organizzazione in Microsoft teams desktop e client Web e nel portale di collaborazione B2B di Azure Active Directory.
ms.openlocfilehash: 7f75589c5252998fb0389c743b951c0fe88e613b
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662441"
---
# <a name="add-a-guest-to-a-team"></a>Aggiungere un utente guest a un team

Chiunque abbia un account di posta elettronica aziendale o personale, come Outlook, Gmail o altri, può partecipare come utente guest in Teams.

Come amministratore, puoi aggiungere un nuovo Guest all'organizzazione in un paio di modi:

- Gli amministratori globali o di Teams e i proprietari dei team aggiungono un utente guest a un team nei client di Teams o nell'interfaccia di amministrazione di Teams. Per altre informazioni, leggere [Aggiungere utenti guest a un team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Se non hai ancora configurato l'accesso come ospite, seguire i passaggi in [Collaborare con gli ospiti in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

- È possibile aggiungere utenti guest all'organizzazione con la collaborazione B2B di Azure Active Directory (Azure AD). Per informazioni dettagliate, vedere [Guida introduttiva: aggiungere Guest alla directory in Azure Portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

Gli amministratori possono anche delegare le autorizzazioni per aggiungere guest ad altri nella propria organizzazione assegnando il ruolo di persona che invita guest. Per altre informazioni, vedere [Abilitare la collaborazione esterna B2B e gestire gli utenti che possono invitare guest](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).

Con Collaborazione B2B di Azure AD, le organizzazioni possono applicare criteri di accesso condizionale e autenticazione a più fattori (MFA) per gli utenti B2B. Questi criteri possono essere applicati a livello di tenant, di app o di singolo utente, così come vengono abilitati per dipendenti a tempo pieno e membri dell'organizzazione. Tali criteri vengono applicati all'organizzazione delle risorse. Per altre informazioni, vedere [Accesso condizionale per gli utenti di Collaborazione B2B](https://go.microsoft.com/fwlink/?linkid=857454). I singoli ospiti non possono essere bloccati.

Gli utenti già aggiunti tramite Azure AD B2B, Microsoft 365 groups o SharePoint sono pronti per l'invio. L'amministratore di Microsoft 365 o un proprietario del team può aggiungere tali Guest ai rispettivi team. Se si aggiunge un Guest direttamente al gruppo Microsoft 365 associato a un team, l'ospite otterrà l'accesso al team, ma il gruppo Microsoft 365 non genera un messaggio di invito per il cliente, quindi qualcuno del team deve avvisare l'ospite.

> [!NOTE]
> Gli utenti guest sono soggetti ai limiti del servizio di [Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

È possibile tenere traccia dei guest aggiunti in Azure AD o Centro sicurezza di Microsoft 365. L'aggiunta di un guest in Microsoft Teams è controllata e registrata come attività di amministrazione del gruppo di Azure AD "Membro aggiunto a gruppo". Per altre informazioni, vedere [controllo e segnalazione di un utente di collaborazione B2B](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) e [ricerca nel log di controllo nel centro conformità](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).


## <a name="related-topics"></a>Argomenti correlati

[Autorizzare l'accesso guest in Microsoft Teams](teams-dependencies.md)

[Attivare o disattivare l'accesso guest in Microsoft Teams](set-up-guests.md)
