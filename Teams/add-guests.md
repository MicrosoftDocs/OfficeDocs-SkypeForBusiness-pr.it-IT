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
description: Gli amministratori possono imparare ad aggiungere nuovi guest a un'organizzazione in Microsoft Teams client desktop e Web Azure Active Directory portale di collaborazione B2B.
ms.openlocfilehash: 1d44aff9b62a5ba6de7c22499f5a20f187d7781b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109082"
---
# <a name="add-a-guest-to-a-team"></a><span data-ttu-id="66277-103">Aggiungere un utente guest a un team</span><span class="sxs-lookup"><span data-stu-id="66277-103">Add a guest to a team</span></span>

<span data-ttu-id="66277-104">Chiunque abbia un account di posta elettronica aziendale o personale, come Outlook, Gmail o altri, può partecipare come utente guest in Teams.</span><span class="sxs-lookup"><span data-stu-id="66277-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="66277-105">Gli amministratori possono aggiungere un nuovo guest all'organizzazione in un paio di modi:</span><span class="sxs-lookup"><span data-stu-id="66277-105">As an admin, you can add a new guest to the organization in a couple of ways:</span></span>

- <span data-ttu-id="66277-106">Gli amministratori globali o di Teams e i proprietari dei team aggiungono un utente guest a un team nei client di Teams o nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="66277-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="66277-107">Per altre informazioni, leggere [Aggiungere utenti guest a un team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="66277-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="66277-108">Se non hai ancora configurato l'accesso come ospite, seguire i passaggi in [Collaborare con gli ospiti in un team](/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="66277-108">If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](/microsoft-365/solutions/collaborate-as-team).</span></span>

- <span data-ttu-id="66277-109">È possibile aggiungere utenti guest all'organizzazione con la collaborazione B2B di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="66277-109">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="66277-110">Per informazioni dettagliate, [vedere Guida introduttiva: Aggiungere guest alla directory nel portale di Azure.](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)</span><span class="sxs-lookup"><span data-stu-id="66277-110">For details, check out [Quickstart: Add guests to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

<span data-ttu-id="66277-111">Gli amministratori possono anche delegare le autorizzazioni per aggiungere guest ad altri nella propria organizzazione assegnando il ruolo di persona che invita guest.</span><span class="sxs-lookup"><span data-stu-id="66277-111">Admins can also delegate permissions to add guests to others in their organization by assigning the Guest Inviter role.</span></span> <span data-ttu-id="66277-112">Per altre informazioni, vedere [Abilitare la collaborazione esterna B2B e gestire gli utenti che possono invitare guest](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="66277-112">For more information, see [Enable B2B external collaboration and manage who can invite guests](/azure/active-directory/external-identities/delegate-invitations).</span></span>

<span data-ttu-id="66277-113">Con Collaborazione B2B di Azure AD, le organizzazioni possono applicare criteri di accesso condizionale e autenticazione a più fattori (MFA) per gli utenti B2B.</span><span class="sxs-lookup"><span data-stu-id="66277-113">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="66277-114">Questi criteri possono essere applicati a livello di tenant, di app o di singolo utente, così come vengono abilitati per dipendenti a tempo pieno e membri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="66277-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="66277-115">Tali criteri vengono applicati all'organizzazione delle risorse.</span><span class="sxs-lookup"><span data-stu-id="66277-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="66277-116">Per altre informazioni, vedere [Accesso condizionale per gli utenti di Collaborazione B2B](/azure/active-directory/external-identities/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="66277-116">For more information, see  [Conditional access for B2B collaboration users](/azure/active-directory/external-identities/conditional-access).</span></span> <span data-ttu-id="66277-117">I singoli guest non possono essere bloccati.</span><span class="sxs-lookup"><span data-stu-id="66277-117">Individual guests can't be blocked.</span></span>

<span data-ttu-id="66277-118">Gli utenti guest già aggiunti tramite Azure AD B2B, Microsoft 365 gruppi o SharePoint sono pronti per iniziare.</span><span class="sxs-lookup"><span data-stu-id="66277-118">Guests you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint are ready to go.</span></span> <span data-ttu-id="66277-119">L Microsoft 365 o il proprietario del team può aggiungere tali guest ai rispettivi team.</span><span class="sxs-lookup"><span data-stu-id="66277-119">The Microsoft 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="66277-120">Se si aggiunge un guest direttamente al gruppo Microsoft 365 associato a un team, il guest avrà accesso al team, ma il gruppo di Microsoft 365 non genera un messaggio di posta elettronica di invito al guest, quindi un membro del team dovrebbe informare il guest.</span><span class="sxs-lookup"><span data-stu-id="66277-120">If you add a guest directly to the Microsoft 365 group associated with a team, the guest will get access to the team but the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="66277-121">Gli utenti guest sono soggetti ai limiti del servizio di [Microsoft 365 o Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) e [Azure Active Directory](/azure/active-directory/external-identities/current-limitations).</span><span class="sxs-lookup"><span data-stu-id="66277-121">Guests are subject to  [Microsoft 365 or Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) and [Azure Active Directory](/azure/active-directory/external-identities/current-limitations) service limits.</span></span>

<span data-ttu-id="66277-122">È possibile tenere traccia dei guest aggiunti in Azure AD o Centro sicurezza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="66277-122">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="66277-123">L'aggiunta di un guest in Microsoft Teams è controllata e registrata come attività di amministrazione del gruppo di Azure AD "Membro aggiunto a gruppo".</span><span class="sxs-lookup"><span data-stu-id="66277-123">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="66277-124">Per altre informazioni, vedere Controllo e segnalazione di un utente di collaborazione [B2B](/azure/active-directory/external-identities/auditing-and-reporting) e Ricerca nel [log di controllo nel Centro conformità.](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)</span><span class="sxs-lookup"><span data-stu-id="66277-124">For more details, see [Auditing and reporting a B2B collaboration user](/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log in the compliance Center](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>


## <a name="related-topics"></a><span data-ttu-id="66277-125">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="66277-125">Related topics</span></span>

[<span data-ttu-id="66277-126">Autorizzare l'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66277-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)

[<span data-ttu-id="66277-127">Attivare o disattivare l'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66277-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)