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
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- seo-marvel-mar2020
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
description: Gli amministratori possono imparare ad aggiungere nuovi guest a un'organizzazione in Microsoft desktop e client Web di Teams e nel portale di collaborazione B2B di Azure Active Directory.
ms.openlocfilehash: 1427b523f2e9e8ec802a8e8d3459f9edadbb68ca
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199138"
---
# <a name="add-a-guest-to-a-team"></a>Aggiungere un utente guest a un team

Chiunque abbia un account di posta elettronica aziendale o personale, come Outlook, Gmail o altri, può partecipare come utente guest in Teams.

Gli amministratori possono aggiungere un nuovo guest all'organizzazione in due modi:

- Gli amministratori globali o di Teams e i proprietari dei team aggiungono un utente guest a un team nei client di Teams o nell'interfaccia di amministrazione di Teams. Per altre informazioni, leggere [Aggiungere utenti guest a un team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Se non hai ancora configurato l'accesso come ospite, seguire i passaggi in [Collaborare con gli ospiti in un team](/microsoft-365/solutions/collaborate-as-team).

- È possibile aggiungere utenti guest all'organizzazione con la collaborazione B2B di Azure Active Directory (Azure AD). Per informazioni dettagliate, vedere [Guida introduttiva: Aggiungere utenti guest alla directory nel portale di Azure](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

Gli amministratori possono anche delegare le autorizzazioni per aggiungere guest ad altri nella propria organizzazione assegnando il ruolo di persona che invita guest. Per altre informazioni, vedere [Abilitare la collaborazione esterna B2B e gestire gli utenti che possono invitare guest](/azure/active-directory/external-identities/delegate-invitations).

Con Collaborazione B2B di Azure AD, le organizzazioni possono applicare criteri di accesso condizionale e autenticazione a più fattori (MFA) per gli utenti B2B. Questi criteri possono essere applicati a livello di tenant, di app o di singolo utente, così come vengono abilitati per dipendenti a tempo pieno e membri dell'organizzazione. Tali criteri vengono applicati all'organizzazione delle risorse. Per altre informazioni, vedere [Accesso condizionale per gli utenti di Collaborazione B2B](/azure/active-directory/external-identities/conditional-access). I singoli ospiti non possono essere bloccati.

Gli utenti guest già aggiunti tramite Azure AD B2B, Gruppi di Microsoft 365 o SharePoint sono pronti all'uso. L'amministratore di Microsoft 365 o un proprietario del team può aggiungere tali guest ai rispettivi team. Se si aggiunge un guest direttamente al gruppo di Microsoft 365 associato a un team, il guest avrà accesso al team, ma il gruppo di Microsoft 365 non genera un messaggio di invito al guest, quindi qualcuno nel team dovrebbe avvisarlo.

> [!NOTE]
> Gli utenti guest sono soggetti ai limiti del servizio di [Microsoft 365 o Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) e [Azure Active Directory](/azure/active-directory/external-identities/current-limitations).

È possibile tenere traccia dei guest aggiunti in Azure AD o Centro sicurezza di Microsoft 365. L'aggiunta di un guest in Microsoft Teams è controllata e registrata come attività di amministrazione del gruppo di Azure AD "Membro aggiunto a gruppo". Per altre informazioni, vedere [Controllo e creazione di report per un utente di collaborazione B2B](/azure/active-directory/external-identities/auditing-and-reporting) ed [Eseguire ricerche nel log di controllo nel Centro conformità](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).


## <a name="related-topics"></a>Argomenti correlati

[Autorizzare l'accesso guest in Microsoft Teams](teams-dependencies.md)

[Attivare o disattivare l'accesso guest in Microsoft Teams](set-up-guests.md)