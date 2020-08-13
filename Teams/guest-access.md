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
description: L'accesso guest in Microsoft Teams consente ai team dell'organizzazione di collaborare con persone esterne all'organizzazione concedendo loro l'accesso a team e canali.
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67ddc045c04c1c3d8cb9bffa0ee15ebf71c70c2f
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656107"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="dd11e-103">Accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd11e-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="dd11e-104">L'accesso guest consente di aggiungere singoli utenti esterni all'organizzazione ai team e ai canali in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="dd11e-104">Guest access lets you add individual users from outside your organization to your teams and channels in Microsoft Teams.</span></span> 

<span data-ttu-id="dd11e-105">Per confrontare l'accesso esterno (federazione) con l'accesso guest e decidere quale usare, leggere [Comunicare con utenti di altre organizzazioni in Teams](communicate-with-users-from-other-organizations.md).</span><span class="sxs-lookup"><span data-stu-id="dd11e-105">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="dd11e-106">Se si vuole attivare l'accesso guest nell'organizzazione, iniziare con l'[Elenco di controllo dell’accesso guest](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="dd11e-106">If you're ready to turn on guest access in your organization, start with the [Guest access checklist](guest-access-checklist.md).</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="dd11e-107">Panoramica dell'accesso guest</span><span class="sxs-lookup"><span data-stu-id="dd11e-107">Guest access overview</span></span>

<span data-ttu-id="dd11e-108">L'accesso guest consente ai team dell'organizzazione di collaborare con persone esterne all'organizzazione concedendo loro l'accesso a team esistenti e canali in Teams.</span><span class="sxs-lookup"><span data-stu-id="dd11e-108">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="dd11e-109">Chiunque abbia un account di posta elettronica aziendale o personale, come Outlook, Gmail o altri, può partecipare come guest in Teams e avere accesso completo a chat, riunioni e file del team.</span><span class="sxs-lookup"><span data-stu-id="dd11e-109">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="dd11e-110">L'amministratore di Teams controlla le funzionalità che gli utenti guest possono (e non possono) usare in Teams, vedere [Gestire l'accesso guest](manage-guests.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="dd11e-110">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="dd11e-111">L'accesso guest è un'impostazione a livello di organizzazione in Teams ed è disattivato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="dd11e-111">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="dd11e-112">L'accesso guest è soggetto ai limiti di servizio di Azure AD e Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="dd11e-112">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="dd11e-113">Gli utenti guest sono inclusi nelle impostazioni a livello di organizzazione di Teams per la modalità di aggiornamento della coesistenza.</span><span class="sxs-lookup"><span data-stu-id="dd11e-113">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="dd11e-114">Questa impostazione non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="dd11e-114">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="dd11e-115">Licenze per l'accesso guest</span><span class="sxs-lookup"><span data-stu-id="dd11e-115">Licensing for guest access</span></span>

<span data-ttu-id="dd11e-116">L'accesso guest è incluso in tutti gli abbonamenti di Microsoft 365 Business Standard, Office 365 Enterprise e Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="dd11e-116">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="dd11e-117">Non sono necessarie altre licenze di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="dd11e-117">No additional Microsoft 365 or Office 365 license is necessary.</span></span> <span data-ttu-id="dd11e-118">Teams non impone un numero limite di utenti guest che è possibile aggiungere.</span><span class="sxs-lookup"><span data-stu-id="dd11e-118">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="dd11e-119">Tuttavia, il numero totale di guest che possono essere aggiunti al tenant possono essere limitati dalle funzionalità a pagamento di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dd11e-119">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="dd11e-120">Per altre informazioni, vedere [Licenze di collaborazione B2B di Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="dd11e-120">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="dd11e-121">Gli utenti dell'organizzazione che hanno solo piani di abbonamento a Microsoft 365 o Office 365 autonomi, ad esempio Exchange Online piano 2, non possono essere invitati come utenti guest nell'organizzazione, perché Teams li considera come appartenenti alla stessa organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd11e-121">Users in your organization who have standalone Microsoft 365 or Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="dd11e-122">Affinché questi utenti possano usare Teams, è necessario assegnare loro un abbonamento a Microsoft 365 Business Standard, Office 365 Enterprise o Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="dd11e-122">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="dd11e-123">Chi è un guest?</span><span class="sxs-lookup"><span data-stu-id="dd11e-123">Who is a guest?</span></span>

<span data-ttu-id="dd11e-124">Un guest è una persona che non è né un dipendente, né uno studente, né un membro dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="dd11e-124">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="dd11e-125">e che non ha un account aziendale o dell'istituto di istruzione presso l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="dd11e-125">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="dd11e-126">Ad esempio, gli utenti guest possono includere partner, fornitori o consulenti.</span><span class="sxs-lookup"><span data-stu-id="dd11e-126">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="dd11e-127">Chiunque non faccia parte dell'organizzazione può essere aggiunto come guest in Teams.</span><span class="sxs-lookup"><span data-stu-id="dd11e-127">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="dd11e-128">Questo significa che chiunque abbia un account aziendale, ossia un account Azure Active Directory, o un account di posta elettronica personale, con Outlook.com, Gmail.com o altri, può partecipare come guest in Teams, con accesso completo ai team e ai canali.</span><span class="sxs-lookup"><span data-stu-id="dd11e-128">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="dd11e-129">Per altre informazioni su ciò che un guest può o non può fare, leggere [Autorizzare l'accesso guest in Microsoft Teams](teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="dd11e-129">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="dd11e-130">In alternativa, vedere la tabella di [confronto tra le funzionalità dei membri del team e degli utenti guest](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="dd11e-130">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="dd11e-131">Infine, tutti gli utenti guest in Teams sono coperti dalla stessa protezione di conformità e controllo del resto di Microsoft 365 e Office 365 e possono essere gestiti in modo sicuro all'interno di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dd11e-131">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365 and Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="dd11e-132">Perché usare l'accesso guest?</span><span class="sxs-lookup"><span data-stu-id="dd11e-132">Why use guest access?</span></span>

<span data-ttu-id="dd11e-133">Con l’accesso guest, le organizzazioni che usano Teams possono consentire l'accesso a team, documenti nei canali, risorse, chat e applicazioni ai propri partner, pur mantenendo il totale controllo dei propri dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="dd11e-133">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="dd11e-134">Tutti gli utenti guest in Teams sono coperti dalla stessa protezione di conformità e controllo del resto di Microsoft 365 o Office 365 e possono essere gestiti in modo sicuro all'interno di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dd11e-134">All guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365 and Office 365, and guests can be managed securely within Azure AD.</span></span>  

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="dd11e-135">Comprendere le limitazioni per gli utenti guest</span><span class="sxs-lookup"><span data-stu-id="dd11e-135">Understand the limitations for guests</span></span>

<span data-ttu-id="dd11e-136">L'esperienza degli utenti guest presenta limitazioni nel design.</span><span class="sxs-lookup"><span data-stu-id="dd11e-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="dd11e-137">È importante assicurarsi di comprendere l'esperienza utente guest, in modo da evitare di provare a risolvere qualcosa che non è un problema.</span><span class="sxs-lookup"><span data-stu-id="dd11e-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="dd11e-138">Ad esempio, ecco un elenco di alcune funzionalità che non sono disponibili per gli utenti guest in Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="dd11e-138">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="dd11e-139">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="dd11e-139">OneDrive for Business</span></span>
- <span data-ttu-id="dd11e-140">Ricerca utenti all'esterno di Teams</span><span class="sxs-lookup"><span data-stu-id="dd11e-140">People search outside of Teams</span></span>
- <span data-ttu-id="dd11e-141">Calendario, Riunioni pianificate o Dettagli riunione</span><span class="sxs-lookup"><span data-stu-id="dd11e-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="dd11e-142">PSTN</span><span class="sxs-lookup"><span data-stu-id="dd11e-142">PSTN</span></span>
- <span data-ttu-id="dd11e-143">Organigramma</span><span class="sxs-lookup"><span data-stu-id="dd11e-143">Organization chart</span></span>
- <span data-ttu-id="dd11e-144">Creare o aggiornare un team</span><span class="sxs-lookup"><span data-stu-id="dd11e-144">Create or revise a team</span></span>
- <span data-ttu-id="dd11e-145">Sfogliare i team</span><span class="sxs-lookup"><span data-stu-id="dd11e-145">Browse for a team</span></span>
- <span data-ttu-id="dd11e-146">Caricare file in una chat tra due persone</span><span class="sxs-lookup"><span data-stu-id="dd11e-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="dd11e-147">Attualmente, Teams supporta solo i tipi di utenti guest Stato1 e Stato 2 [come definiti da Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span><span class="sxs-lookup"><span data-stu-id="dd11e-147">Currently, Teams supports only State 1 and State 2 types of guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="dd11e-148">Per un elenco completo delle funzionalità di un utente guest in Teams, vedere la tabella di [confronto tra le funzionalità dei membri del team e degli utenti guest](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="dd11e-148">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="dd11e-149">Per altre informazioni sull'accesso guest a livello di Microsoft 365 e Office 365, vedere [Aggiunta di utenti guest ai Gruppi di Microsoft 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="dd11e-149">To learn more about guest access at the Microsoft 365 and Office 365 levels, read [Adding guests to Microsoft 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>


## <a name="more-information"></a><span data-ttu-id="dd11e-150">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="dd11e-150">More information</span></span>

[<span data-ttu-id="dd11e-151">Contattare il supporto tecnico per i prodotti per le aziende - Guida dell'amministratore</span><span class="sxs-lookup"><span data-stu-id="dd11e-151">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)  
[<span data-ttu-id="dd11e-152">Accesso guest in Gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dd11e-152">Guest access in Microsoft 365 Groups</span></span>](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
