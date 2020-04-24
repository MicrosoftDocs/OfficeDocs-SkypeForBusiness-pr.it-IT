---
title: Aggiungere un utente guest a un team
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
f1.keywords:
- NOCSH
localization_priority: Priority
description: Gli amministratori possono imparare ad aggiungere nuovi utenti guest a un'organizzazione nei client desktop e Web di Microsoft Teams e nel portale di collaborazione B2B di Azure Active Directory.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 026fa191dffa160980bfb00e7031490f01ddc6cc
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778221"
---
<a name="add-a-guest-to-a-team"></a>Aggiungere un utente guest a un team
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Chiunque abbia un account di posta elettronica aziendale o personale, come Outlook, Gmail o altri, può partecipare come utente guest in Teams.

Gli amministratori possono aggiungere un nuovo utente guest all'organizzazione in diversi modi:
- Gli amministratori globali o di Teams e i proprietari dei team aggiungono un utente guest a un team nei client di Teams o nell'interfaccia di amministrazione di Teams. Per altre informazioni, leggere [Aggiungere utenti guest a un team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Se non è stato ancora configurato l'accesso guest, seguire i passaggi nell'[elenco di controllo di accesso guest](guest-access-checklist.md).

> [!NOTE] 
> Questo non si applica quando l'opzione **Amministratori e utenti nel ruolo mittente dell'invito guest possono invitare** è abilitata. Il motivo è che il ruolo mittente dell'invito non è supportato in Teams.

- È possibile aggiungere utenti guest all'organizzazione con la collaborazione B2B di Azure Active Directory (Azure AD). Collaborazione B2B di Azure AD consente a un amministratore globale di invitare e autorizzare un gruppo di utenti esterni caricando un file con valori delimitati da virgole (CSV) di non più di 2000 righe sul portale di collaborazione B2B. Per ulteriori dettagli, consultare [Collaborazione B2B di Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=826383).

Con Collaborazione B2B di Azure AD, le organizzazioni possono applicare criteri di accesso condizionale e autenticazione a più fattori (MFA) per gli utenti B2B. Questi criteri possono essere applicati a livello di tenant, di app o di singolo utente, così come vengono abilitati per dipendenti a tempo pieno e membri dell'organizzazione. Tali criteri vengono applicati all'organizzazione delle risorse. Per altre informazioni, vedere [Accesso condizionale per gli utenti di Collaborazione B2B](https://go.microsoft.com/fwlink/?linkid=857454). Non è possibile bloccare singoli utenti guest.

Gli utenti guest che sono stati già aggiunti tramite B2B di Azure AD, Gruppi di Microsoft 365 o SharePoint Online sono pronti. L'amministratore di Office 365 o un proprietario dei team può aggiungere questi utenti guest ai rispettivi team. Se un team è già presente in un gruppo di Office 365 e viene aggiunto un utente guest al gruppo, il guest otterrà l'accesso al team. L'aggiunta di un guest tramite il gruppo di Office 365 non genera un messaggio di posta elettronica di invito per il guest, pertanto una persona del team deve informarlo.

> [!NOTE]
> Gli utenti guest sono soggetti ai limiti del servizio di [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

È possibile tenere traccia dei guest aggiunti in Azure AD o Centro sicurezza &amp; conformità di Office 365. L'aggiunta di un guest in Microsoft Teams è controllata e registrata come attività di amministrazione del gruppo di Azure AD "Membro aggiunto a gruppo". Per ulteriori dettagli, vedere [Controllo e creazione di report per un utente di Collaborazione B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) e [Eseguire una ricerca nel log di controllo nel Centro sicurezza &amp; conformità di Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).


## <a name="more-information"></a>Altre informazioni

[Autorizzare l'accesso guest in Microsoft Teams](teams-dependencies.md)</br>
[Attivare o disattivare l'accesso guest in Microsoft Teams](set-up-guests.md)</br>
[Usare PowerShell per controllare l'accesso guest a un team](guest-access-powershell.md)
