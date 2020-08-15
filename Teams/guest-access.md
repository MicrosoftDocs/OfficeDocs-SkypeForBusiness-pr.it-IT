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
# <a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="704f9-103">Accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="704f9-103">Guest access in Microsoft Teams</span></span>

<span data-ttu-id="704f9-104">L'accesso guest consente ai team dell'organizzazione di collaborare con persone esterne all'organizzazione concedendo loro l'accesso a team esistenti e canali in Teams.</span><span class="sxs-lookup"><span data-stu-id="704f9-104">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="704f9-105">Chiunque disponga di un account di posta elettronica aziendale o consumer, ad esempio Microsoft 365, Outlook, Gmail o altri utenti, può partecipare come guest in teams con accesso completo alle chat, alle riunioni e ai file del team.</span><span class="sxs-lookup"><span data-stu-id="704f9-105">Anyone with a business or consumer email account, such as Microsoft 365, Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="704f9-106">L'amministratore di Teams controlla le funzionalità che gli utenti guest possono (e non possono) usare in Teams, vedere [Gestire l'accesso guest](manage-guests.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="704f9-106">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="704f9-107">Per confrontare l'accesso esterno (federazione) con l'accesso guest e decidere quale usare, leggere [Comunicare con utenti di altre organizzazioni in Teams](communicate-with-users-from-other-organizations.md).</span><span class="sxs-lookup"><span data-stu-id="704f9-107">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="704f9-108">L'accesso guest è un'impostazione a livello di organizzazione in Teams ed è disattivato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="704f9-108">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="704f9-109">Puoi controllare l'accesso Guest ai singoli team usando le [etichette di sensitività](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="704f9-109">(You can control guest access to individual teams by using [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)</span></span>

<span data-ttu-id="704f9-110">Se si è pronti per iniziare a invitare gli ospiti in teams, leggere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="704f9-110">If you're ready to start inviting guests to teams, read one of the following:</span></span>

- <span data-ttu-id="704f9-111">Per configurare l'accesso guest per i team per uso generale, vedere [collaborare con gli utenti in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="704f9-111">To configure guest access for Teams for general use, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>
- <span data-ttu-id="704f9-112">Per collaborare con un'organizzazione partner che usa Azure Active Directory e consentire agli utenti di iscriversi autonomamente per l'accesso al team, vedere [creare una rete Extranet B2B con Guest gestiti](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).</span><span class="sxs-lookup"><span data-stu-id="704f9-112">To collaborate with a partner organization that uses Azure Active Directory and allow guests to self-enroll for team access, see [Create a B2B extranet with managed guests](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).</span></span>

<span data-ttu-id="704f9-113">L'accesso guest è soggetto ai limiti di servizio di Azure AD e Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="704f9-113">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="704f9-114">Gli utenti guest sono inclusi nelle impostazioni a livello di organizzazione di Teams per la modalità di aggiornamento della coesistenza.</span><span class="sxs-lookup"><span data-stu-id="704f9-114">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="704f9-115">Questa impostazione non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="704f9-115">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="704f9-116">Licenze per l'accesso guest</span><span class="sxs-lookup"><span data-stu-id="704f9-116">Licensing for guest access</span></span>

<span data-ttu-id="704f9-117">L'accesso guest è incluso in tutti gli abbonamenti di Microsoft 365 Business Standard, Office 365 Enterprise e Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="704f9-117">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="704f9-118">Non sono necessarie altre licenze di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="704f9-118">No additional Microsoft 365 or Office 365 license is necessary.</span></span> <span data-ttu-id="704f9-119">Teams non impone un numero limite di utenti guest che è possibile aggiungere.</span><span class="sxs-lookup"><span data-stu-id="704f9-119">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="704f9-120">Tuttavia, il numero totale di guest che possono essere aggiunti al tenant possono essere limitati dalle funzionalità a pagamento di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="704f9-120">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="704f9-121">Per altre informazioni, vedere [Licenze di collaborazione B2B di Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="704f9-121">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="704f9-122">Gli utenti dell'organizzazione che hanno solo piani di abbonamento a Microsoft 365 o Office 365 autonomi, ad esempio Exchange Online piano 2, non possono essere invitati come utenti guest nell'organizzazione, perché Teams li considera come appartenenti alla stessa organizzazione.</span><span class="sxs-lookup"><span data-stu-id="704f9-122">Users in your organization who have standalone Microsoft 365 or Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="704f9-123">Affinché questi utenti possano usare Teams, è necessario assegnare loro un abbonamento a Microsoft 365 Business Standard, Office 365 Enterprise o Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="704f9-123">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="704f9-124">Chi è un guest?</span><span class="sxs-lookup"><span data-stu-id="704f9-124">Who is a guest?</span></span>

<span data-ttu-id="704f9-125">Un guest è una persona che non è né un dipendente, né uno studente, né un membro dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="704f9-125">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="704f9-126">e che non ha un account aziendale o dell'istituto di istruzione presso l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="704f9-126">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="704f9-127">Ad esempio, gli utenti guest possono includere partner, fornitori o consulenti.</span><span class="sxs-lookup"><span data-stu-id="704f9-127">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="704f9-128">Chiunque non faccia parte dell'organizzazione può essere aggiunto come guest in Teams.</span><span class="sxs-lookup"><span data-stu-id="704f9-128">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="704f9-129">Questo significa che chiunque abbia un account aziendale, ossia un account Azure Active Directory, o un account di posta elettronica personale, con Outlook.com, Gmail.com o altri, può partecipare come guest in Teams, con accesso completo ai team e ai canali.</span><span class="sxs-lookup"><span data-stu-id="704f9-129">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="704f9-130">Per altre informazioni su ciò che un guest può o non può fare, leggere [Autorizzare l'accesso guest in Microsoft Teams](teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="704f9-130">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="704f9-131">In alternativa, vedere la tabella di [confronto tra le funzionalità dei membri del team e degli utenti guest](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="704f9-131">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="704f9-132">Infine, tutti gli utenti di teams sono coperti dalla stessa protezione di conformità e controllo del resto di Microsoft 365 e possono essere gestiti in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="704f9-132">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365, and can be managed within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="704f9-133">Perché usare l'accesso guest?</span><span class="sxs-lookup"><span data-stu-id="704f9-133">Why use guest access?</span></span>

<span data-ttu-id="704f9-134">Con l’accesso guest, le organizzazioni che usano Teams possono consentire l'accesso a team, documenti nei canali, risorse, chat e applicazioni ai propri partner, pur mantenendo il totale controllo dei propri dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="704f9-134">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> 

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="704f9-135">Comprendere le limitazioni per gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="704f9-135">Understand the limitations for guests</span></span>

<span data-ttu-id="704f9-136">L'esperienza degli utenti guest presenta limitazioni nel design.</span><span class="sxs-lookup"><span data-stu-id="704f9-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="704f9-137">È importante assicurarsi di comprendere l'esperienza utente guest, in modo da evitare di provare a risolvere qualcosa che non è un problema.</span><span class="sxs-lookup"><span data-stu-id="704f9-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="704f9-138">Ecco un elenco di alcune delle funzionalità che non sono disponibili per un guest in Microsoft teams:</span><span class="sxs-lookup"><span data-stu-id="704f9-138">Here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="704f9-139">OneDrive</span><span class="sxs-lookup"><span data-stu-id="704f9-139">OneDrive</span></span>
- <span data-ttu-id="704f9-140">Ricerca utenti all'esterno di Teams</span><span class="sxs-lookup"><span data-stu-id="704f9-140">People search outside of Teams</span></span>
- <span data-ttu-id="704f9-141">Calendario, Riunioni pianificate o Dettagli riunione</span><span class="sxs-lookup"><span data-stu-id="704f9-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="704f9-142">PSTN</span><span class="sxs-lookup"><span data-stu-id="704f9-142">PSTN</span></span>
- <span data-ttu-id="704f9-143">Organigramma</span><span class="sxs-lookup"><span data-stu-id="704f9-143">Organization chart</span></span>
- <span data-ttu-id="704f9-144">Creare o aggiornare un team</span><span class="sxs-lookup"><span data-stu-id="704f9-144">Create or revise a team</span></span>
- <span data-ttu-id="704f9-145">Sfogliare i team</span><span class="sxs-lookup"><span data-stu-id="704f9-145">Browse for a team</span></span>
- <span data-ttu-id="704f9-146">Caricare file in una chat tra due persone</span><span class="sxs-lookup"><span data-stu-id="704f9-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="704f9-147">Attualmente, teams supporta solo [lo stato 1 e i due tipi di utenti Guest](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span><span class="sxs-lookup"><span data-stu-id="704f9-147">Currently, Teams supports only [State 1 and State 2 types of guest users](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="704f9-148">Per un elenco completo delle funzionalità di un utente guest in Teams, vedere la tabella di [confronto tra le funzionalità dei membri del team e degli utenti guest](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="704f9-148">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="704f9-149">Per altre informazioni sull'accesso Guest a livello di Microsoft 365, leggere la [collaborazione con persone esterne all'organizzazione](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization).</span><span class="sxs-lookup"><span data-stu-id="704f9-149">To learn more about guest access at the Microsoft 365 level, read [Collaborating with people outside your organization](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization).</span></span>


## <a name="related-topics"></a><span data-ttu-id="704f9-150">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="704f9-150">Related topics</span></span>

[<span data-ttu-id="704f9-151">Contattare il supporto tecnico per i prodotti per le aziende - Guida dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="704f9-151">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[<span data-ttu-id="704f9-152">Configurare Team con tre livelli di protezione</span><span class="sxs-lookup"><span data-stu-id="704f9-152">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
