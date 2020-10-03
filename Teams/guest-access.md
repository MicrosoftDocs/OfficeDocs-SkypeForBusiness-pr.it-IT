---
title: Accesso guest in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
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
ms.openlocfilehash: 388fb68196a6e68c13066b7b94a1b24a31834b37
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346167"
---
# <a name="guest-access-in-microsoft-teams"></a>Accesso guest in Microsoft Teams

Con l'accesso guest, è possibile consentire l'accesso a team, documenti in canali, risorse, chat e applicazioni a persone esterne all'organizzazione, mantenendo il controllo dei dati aziendali.

Un guest è una persona che non è né un dipendente, né uno studente, né un membro dell'organizzazione e che non ha un account aziendale o dell'istituto di istruzione presso l'organizzazione. Ad esempio, gli utenti guest possono includere partner, fornitori o consulenti. Chiunque non faccia parte dell'organizzazione può essere aggiunto come guest in Teams. Ciò significa che chiunque disponga di un account aziendale, ovvero di un account di Azure Active Directory o di un account di posta elettronica consumer (con Outlook.com, Gmail.com o altri), può partecipare come guest in teams, con l'accesso a team e a esperienze di canale.

L'amministratore di teams [Controlla quali funzionalità gli utenti possono (e non possono) usare in teams](manage-guests.md). Gli utenti di teams sono coperti dalla stessa protezione di conformità e controllo del resto di Microsoft 365 e possono essere gestiti in Azure AD. L'accesso guest è soggetto ai limiti di servizio di Azure AD e Microsoft 365 o Office 365.

L'esperienza degli utenti guest presenta limitazioni nel design. Per un elenco completo delle funzionalità di un guest che può e non è possibile eseguire in teams, vedere[confronto tra le caratteristiche di membro del team e Guest](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

> [!IMPORTANT]
> Gli utenti guest sono inclusi nelle impostazioni a livello di organizzazione di Teams per la modalità di aggiornamento della coesistenza. Questa impostazione non può essere modificata.

Per confrontare l'accesso esterno (federazione) con l'accesso guest e decidere quale usare, leggere [Comunicare con utenti di altre organizzazioni in Teams](communicate-with-users-from-other-organizations.md).

## <a name="set-up-guest-access"></a>Configurare l'accesso Guest

L'accesso guest in teams richiede la configurazione di altre impostazioni in Microsoft 365, incluse le impostazioni in Azure AD, Microsoft 365 Groups e SharePoint. Se si è pronti per iniziare a invitare gli ospiti in teams, leggere una delle opzioni seguenti:

- Per configurare l'accesso guest per i team per uso generale, vedere [collaborare con gli utenti in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).
- Per collaborare con un'organizzazione partner che usa Azure Active Directory e consentire agli utenti di iscriversi autonomamente per l'accesso al team, vedere [creare una rete Extranet B2B con Guest gestiti](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).

L'accesso guest in teams è un'impostazione a livello di organizzazione ed è disattivato per impostazione predefinita. Puoi controllare l'accesso Guest ai singoli team usando le [etichette di sensitività](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>Come diventare un membro di un team da guest

1. Un proprietario del team o un amministratore di Microsoft 365 [aggiunge un Guest a un team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Il guest riceve un'e-mail di benvenuto dal proprietario del team, contenente informazioni sul team e sulle funzionalità disponibili in quanto nuovo membro.
3. Il guest accetta l'invito.
  Gli utenti guest che hanno un account aziendale o dell'Istituto di istruzione in Azure Active Directory possono accettare l'invito e eseguire l'autenticazione direttamente. Ad altri utenti viene inviato un codice di passata unica per convalidare la propria identità (necessaria[l'autenticazione di un codice di sola volta](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) ).
4. Dopo aver accettato l'invito, il guest può [partecipare a team e canali](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), ricevere e rispondere ai messaggi del canale, [accedere ai file nei canali](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), partecipare alle chat, partecipare alle riunioni, collaborare ai documenti e altro ancora. 

In Teams, i guest vengono identificati in modo chiaro. Il nome di un utente guest include l'etichetta **(Guest)** e il canale include un'icona che indica la presenza di guest nel team. Per maggiori dettagli, vedere [Informazioni sull'esperienza guest](guest-experience.md).
  
I guest possono abbandonare il team in qualsiasi momento tramite Teams. Per i dettagli, vedere [Come abbandonare un team](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> Lasciando il team non viene rimosso l'account Guest dalla directory dell'organizzazione. Questa operazione deve essere eseguita da un amministratore globale di Microsoft 365 o da un amministratore di Azure AD.

## <a name="licensing-for-guest-access"></a>Licenze per l'accesso guest

L'accesso Guest è incluso in tutti gli abbonamenti Microsoft 365 business standard, Microsoft 365 Enterprise e Microsoft 365 Education. Non è necessaria alcuna licenza Microsoft 365 aggiuntiva. Teams non impone un numero limite di utenti guest che è possibile aggiungere. Tuttavia, il numero totale di guest che possono essere aggiunti al tenant possono essere limitati dalle funzionalità a pagamento di Azure AD. Per altre informazioni, vedere [Licenze di collaborazione B2B di Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

> [!NOTE]
> Gli utenti dell'organizzazione che hanno solo piani di abbonamento a Microsoft 365 autonomi, ad esempio Exchange Online piano 2, non possono essere invitati come Guest all'organizzazione perché i team considerano questi utenti come appartenenti alla stessa organizzazione. Affinché questi utenti possano usare Teams, è necessario assegnare loro un abbonamento a Microsoft 365 Business Standard, Office 365 Enterprise o Office 365 Education. 

## <a name="guest-access-reviews"></a>Recensioni di Access Guest

Puoi usare Azure AD per creare una revisione di Access per i membri del gruppo o gli utenti assegnati a un'applicazione. La creazione di recensioni di Access periodiche consente di risparmiare tempo. Se è necessario rivedere in modo sistematico gli utenti che hanno accesso a un'applicazione, un team o membri di un gruppo, è possibile definire la frequenza di tali revisioni. 

È possibile eseguire una revisione dell'accesso guest, chiedere agli ospiti di rivedere la propria appartenenza o chiedere a un proprietario dell'applicazione o a un decisore aziendale di eseguire la revisione di Access. Usare il portale di Azure per eseguire le recensioni di accesso guest. Per altre informazioni, vedere [gestire l'accesso guest con le recensioni di Access di Azure ad](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Argomenti correlati

[Collaborare con persone esterne all'organizzazione](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Bloccare gli utenti Guest da un gruppo Microsoft 365 o Microsoft teams specifico](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Creare un ambiente di condivisione Guest sicuro](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Contattare il supporto tecnico per i prodotti per le aziende - Guida dell'amministratore](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[Configurare Team con tre livelli di protezione](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
