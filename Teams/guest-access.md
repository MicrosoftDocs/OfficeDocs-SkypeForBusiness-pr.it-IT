---
title: Accesso guest in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
description: L'accesso guest in Microsoft Teams consente ai team dell'organizzazione di collaborare con persone esterne all'organizzazione concedendo loro l'accesso a team e canali.
ms.openlocfilehash: f04fce7f75df32111b2577119c12b14eadf963b9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761242"
---
# <a name="guest-access-in-microsoft-teams"></a>Accesso guest in Microsoft Teams

L'accesso guest consente ai team dell'organizzazione di collaborare con persone esterne all'organizzazione concedendo loro l'accesso a team esistenti e canali in Teams. Chiunque disponga di un account di posta elettronica aziendale o consumer, ad esempio Microsoft 365, Outlook, Gmail o altri utenti, può partecipare come guest in teams con accesso completo alle chat, alle riunioni e ai file del team. L'amministratore di Teams controlla le funzionalità che gli utenti guest possono (e non possono) usare in Teams, vedere [Gestire l'accesso guest](manage-guests.md) per altre informazioni.

Per confrontare l'accesso esterno (federazione) con l'accesso guest e decidere quale usare, leggere [Comunicare con utenti di altre organizzazioni in Teams](communicate-with-users-from-other-organizations.md).

L'accesso guest è un'impostazione a livello di organizzazione in Teams ed è disattivato per impostazione predefinita. Puoi controllare l'accesso Guest ai singoli team usando le [etichette di sensitività](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

Se si è pronti per iniziare a invitare gli ospiti in teams, leggere una delle opzioni seguenti:

- Per configurare l'accesso guest per i team per uso generale, vedere [collaborare con gli utenti in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).
- Per collaborare con un'organizzazione partner che usa Azure Active Directory e consentire agli utenti di iscriversi autonomamente per l'accesso al team, vedere [creare una rete Extranet B2B con Guest gestiti](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).

L'accesso guest è soggetto ai limiti di servizio di Azure AD e Microsoft 365 o Office 365.

> [!IMPORTANT]
> Gli utenti guest sono inclusi nelle impostazioni a livello di organizzazione di Teams per la modalità di aggiornamento della coesistenza. Questa impostazione non può essere modificata.

## <a name="licensing-for-guest-access"></a>Licenze per l'accesso guest

L'accesso guest è incluso in tutti gli abbonamenti di Microsoft 365 Business Standard, Office 365 Enterprise e Office 365 Education. Non sono necessarie altre licenze di Microsoft 365 o Office 365. Teams non impone un numero limite di utenti guest che è possibile aggiungere. Tuttavia, il numero totale di guest che possono essere aggiunti al tenant possono essere limitati dalle funzionalità a pagamento di Azure AD. Per altre informazioni, vedere [Licenze di collaborazione B2B di Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).


> [!NOTE]
> Gli utenti dell'organizzazione che hanno solo piani di abbonamento a Microsoft 365 o Office 365 autonomi, ad esempio Exchange Online piano 2, non possono essere invitati come utenti guest nell'organizzazione, perché Teams li considera come appartenenti alla stessa organizzazione. Affinché questi utenti possano usare Teams, è necessario assegnare loro un abbonamento a Microsoft 365 Business Standard, Office 365 Enterprise o Office 365 Education. 

## <a name="who-is-a-guest"></a>Chi è un guest?

Un guest è una persona che non è né un dipendente, né uno studente, né un membro dell'organizzazione e che non ha un account aziendale o dell'istituto di istruzione presso l'organizzazione. Ad esempio, gli utenti guest possono includere partner, fornitori o consulenti. Chiunque non faccia parte dell'organizzazione può essere aggiunto come guest in Teams. Questo significa che chiunque abbia un account aziendale, ossia un account Azure Active Directory, o un account di posta elettronica personale, con Outlook.com, Gmail.com o altri, può partecipare come guest in Teams, con accesso completo ai team e ai canali.

Per altre informazioni su ciò che un guest può o non può fare, leggere [Autorizzare l'accesso guest in Microsoft Teams](teams-dependencies.md). In alternativa, vedere la tabella di [confronto tra le funzionalità dei membri del team e degli utenti guest](guest-experience.md#comparison-of-team-member-and-guest-capabilities). 

Infine, tutti gli utenti di teams sono coperti dalla stessa protezione di conformità e controllo del resto di Microsoft 365 e possono essere gestiti in Azure AD.

## <a name="why-use-guest-access"></a>Perché usare l'accesso guest?

Con l’accesso guest, le organizzazioni che usano Teams possono consentire l'accesso a team, documenti nei canali, risorse, chat e applicazioni ai propri partner, pur mantenendo il totale controllo dei propri dati aziendali. 

## <a name="understand-the-limitations-for-guests"></a>Comprendere le limitazioni per gli utenti guest

L'esperienza degli utenti guest presenta limitazioni nel design. È importante assicurarsi di comprendere l'esperienza utente guest, in modo da evitare di provare a risolvere qualcosa che non è un problema. Ecco un elenco di alcune delle funzionalità che non sono disponibili per un guest in Microsoft teams:

- OneDrive
- Ricerca utenti all'esterno di Teams
- Calendario, Riunioni pianificate o Dettagli riunione
- PSTN
- Organigramma
- Creare o aggiornare un team
- Sfogliare i team
- Caricare file in una chat tra due persone
- Attualmente, teams supporta solo [lo stato 1 e i due tipi di utenti Guest](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)

Per un elenco completo delle funzionalità di un utente guest in Teams, vedere la tabella di [confronto tra le funzionalità dei membri del team e degli utenti guest](guest-experience.md#comparison-of-team-member-and-guest-capabilities). Per altre informazioni sull'accesso Guest a livello di Microsoft 365, leggere la [collaborazione con persone esterne all'organizzazione](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization).


## <a name="related-topics"></a>Argomenti correlati

[Contattare il supporto tecnico per i prodotti per le aziende - Guida dell'amministratore](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[Configurare Team con tre livelli di protezione](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
