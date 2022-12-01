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
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.guestaccess.overview
- chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: L'accesso guest in Microsoft Teams consente ai team dell'organizzazione di collaborare con persone esterne all'organizzazione concedendo loro l'accesso a team e canali.
ms.openlocfilehash: 399cd1c0aecb7377292810b26cd123873405f547
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198468"
---
# <a name="guest-access-in-microsoft-teams"></a>Accesso guest in Microsoft Teams

Tramite l’accesso guest, è possibile consentire l'accesso a team, documenti nei canali, risorse, chat e applicazioni alle persone esterne all’organizzazione, pur mantenendo il totale controllo dei dati aziendali. Vedere [Configurare la collaborazione sicura con Microsoft 365 e Microsoft Teams](/microsoft-365/solutions/setup-secure-collaboration-with-teams). L'accesso guest in Teams è un'impostazione a livello di organizzazione ed è attivato per impostazione predefinita. È possibile controllare l'accesso guest ai singoli team usando le [etichette di riservatezza](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!NOTE]
> Se si vuole semplicemente trovare, chiamare, chattare e configurare riunioni con persone di altre organizzazioni, usare l’[accesso esterno](manage-external-access.md).

Un guest è una persona che non ha un account aziendale o dell'istituto di istruzione con l'organizzazione. Ad esempio, gli utenti guest possono includere partner, fornitori o consulenti. Chiunque non faccia parte dell'organizzazione può essere aggiunto come guest in Teams. Questo significa che chiunque abbia un account aziendale, ossia un account Azure Active Directory, o un account di posta elettronica personale, con Outlook.com, Gmail.com o altri, può partecipare come guest in Teams, con accesso ai team e ai canali.

When you invite a guest to Teams, a guest account is created for them in Azure Active Directory and they are covered by the same compliance and auditing protection as other Microsoft 365 users. Guest access is subject to Azure AD and Microsoft 365 service limits.

The guest experience has limitations by design. For a full list of what a guest can and can't do in Teams, see [Guest access in Microsoft Teams](guest-experience.md).

> [!IMPORTANT]
> Guests follow Teams Org-wide settings for the coexistence Upgrade mode. This can't be changed.

Per confrontare l'accesso esterno (federazione) con l'accesso guest e decidere quale usare, leggere [Comunicare con utenti di altre organizzazioni in Teams](communicate-with-users-from-other-organizations.md).

Shared channels offer an alternative to guest access, allowing you to invite people outside your organization without requiring a guest account in Azure AD. To compare guest access with shared channels, see [Plan external collaboration](/microsoft-365/solutions/plan-external-collaboration).

Per configurare l'accesso guest, vedere [Collaborare con gli utenti guest in un team](/microsoft-365/solutions/collaborate-as-team). 

## <a name="set-up-guest-access"></a>Configurare l’accesso per gli utenti guest

L'accesso guest in Teams richiede la configurazione di altre impostazioni in Microsoft 365, tra cui le impostazioni in Azure AD, i Gruppi di Microsoft 365 e SharePoint. Quando si è pronti a invitare utenti guest a Teams, leggere una delle opzioni seguenti:

- Per configurare l'accesso degli utenti guest per l’uso generale di Teams, vedere [Collaborare con gli utenti guest in un team](/microsoft-365/solutions/collaborate-as-team).
- Per collaborare con un'organizzazione partner che usa Azure Active Directory e consentire agli utenti guest di iscriversi autonomamente per l'accesso a Teams, vedere [Creare una Extranet B2B con utenti guest gestiti](/microsoft-365/solutions/b2b-extranet).

> [!NOTE]
> Se come amministratori si sperimentano problemi con l'accesso guest in Microsoft Teams, si può selezionare **Esegui test** in basso, per popolare la diagnostica di Accesso guest nell'interfaccia di Amministrazione Microsoft 365. Questi test verificheranno la configurazione e consiglieranno rapidamente i passaggi da intraprendere per abilitare l'accesso guest per il tenant.
>> [!div class="nextstepaction"]
>> [Esegui Test: accesso guest](https://aka.ms/TeamsGuestAccessDiagDMC)

## <a name="how-a-guest-gets-added-to-a-team"></a>Come viene aggiunto un guest a un team

1. Il proprietario di un team o un amministratore di Microsoft 365 [aggiunge un utente guest al team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Il guest riceve un messaggio di posta elettronica di benvenuto dal proprietario del team, con informazioni sul team e su cosa aspettarsi dopo l'aggiunta.
3. Il guest accetta l'invito.
  Gli utenti guest che hanno un account aziendale o dell'Istituto di istruzione per Azure Active Directory possono accettare l'invito e autenticarsi direttamente. Agli altri utenti viene inviato un passcode monouso per convalidare la propria identità (obbligatoria l’[autenticazione con passcode monouso](/azure/active-directory/external-identities/one-time-passcode))
4. Dopo aver accettato l'invito, il guest può [partecipare a team e canali](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), ricevere e rispondere ai messaggi del canale, [accedere ai file nei canali](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), partecipare alle chat, partecipare alle riunioni, collaborare ai documenti e altro ancora. 

In Teams, i guest vengono identificati in modo chiaro. Il nome di un utente guest include l'etichetta **(Guest)** e il canale include un'icona che indica la presenza di utenti guest nel team. Per maggiori dettagli, vedere [Informazioni sull'esperienza guest](guest-experience.md).
  
I guest possono abbandonare il team in qualsiasi momento tramite Teams. Per i dettagli, vedere [Come abbandonare un team](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> Abbandonare il team non implica la rimozione dell'account guest dalla directory dell'organizzazione. Questa operazione deve essere eseguita da un amministratore globale di Microsoft 365 o da un amministratore di Azure AD.

## <a name="licensing-for-guest-access"></a>Licenze per l'accesso guest

L'accesso guest può essere usato in tutti gli abbonamenti di Microsoft 365 Business Standard, Microsoft 365 Enterprise e Microsoft 365 Education. Non sono necessarie altre licenze di Microsoft 365. Il [modello di fatturazione per Azure AD per identità esterne](/azure/active-directory/b2b/licensing-guidance) si applica agli utenti guest in Microsoft 365. Solo le persone esterne all'organizzazione possono essere invitate come utenti guest.

> [!NOTE]
> La conversione di un account guest in un account Azure AD o la conversione di un account membro Azure AD in un account guest non è supportata da Teams.

## <a name="guest-access-reviews"></a>Verifiche di accesso per gli utenti guest

È possibile usare Azure AD per creare una verifica di accesso per gli utenti che sono in gruppi o sono stati assegnati a un'applicazione. La creazione di verifiche di accesso ricorrenti consente di risparmiare tempo. Se è necessario verificare regolarmente gli utenti che hanno accesso a un'applicazione, a un team o a un gruppo, è possibile definire la frequenza di tali revisioni. 

È possibile eseguire la verifica dell'accesso guest, chiedere ai guest di verificare il proprio accesso o chiedere a un proprietario dell'applicazione o a un responsabile delle decisioni aziendali di eseguire la verifica di accesso. Usare il portale di Azure per eseguire le verifiche di accesso degli utenti guest. Per altre informazioni, vedere [Gestire l'accesso guest con le verifiche di accesso di Azure AD](/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Argomenti correlati

[Collaborare con persone esterne all'organizzazione](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Bloccare gli utenti guest di un gruppo di Microsoft 365 specifico o di un team di Microsoft Teams](/microsoft-365/solutions/per-group-guest-access)

[Creare un ambiente di condivisione guest sicuro](/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Contattare il supporto tecnico per i prodotti per le aziende - Guida dell'amministratore](/microsoft-365/admin/contact-support-for-business-products)

[Configurare Teams con tre livelli di protezione](/microsoft-365/solutions/configure-teams-three-tiers-protection)
