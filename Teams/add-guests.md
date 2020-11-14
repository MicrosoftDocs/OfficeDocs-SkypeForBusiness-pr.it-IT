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
description: Gli amministratori possono imparare ad aggiungere nuovi utenti guest a un'organizzazione nei client desktop e Web di Microsoft Teams e nel portale di collaborazione B2B di Azure Active Directory.
ms.openlocfilehash: 21f8e733a87474888f2b33f8a23a063fa00b4b11
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030812"
---
# <a name="add-a-guest-to-a-team"></a><span data-ttu-id="38324-103">Aggiungere un utente guest a un team</span><span class="sxs-lookup"><span data-stu-id="38324-103">Add a guest to a team</span></span>

<span data-ttu-id="38324-104">Chiunque abbia un account di posta elettronica aziendale o personale, come Outlook, Gmail o altri, può partecipare come utente guest in Teams.</span><span class="sxs-lookup"><span data-stu-id="38324-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="38324-105">Gli amministratori possono aggiungere un nuovo utente guest all'organizzazione in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="38324-105">As an admin, you can add a new guest user to the organization in a couple of ways:</span></span>

- <span data-ttu-id="38324-106">Gli amministratori globali o di Teams e i proprietari dei team aggiungono un utente guest a un team nei client di Teams o nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="38324-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="38324-107">Per altre informazioni, leggere [Aggiungere utenti guest a un team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="38324-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="38324-108">Se non hai ancora configurato l'accesso come ospite, seguire i passaggi in [Collaborare con gli ospiti in un team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="38324-108">If you haven't set up guest access yet, go through the steps in the [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

- <span data-ttu-id="38324-109">È possibile aggiungere utenti guest all'organizzazione con la collaborazione B2B di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="38324-109">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="38324-110">Per informazioni dettagliate, vedere [Guida introduttiva: aggiungere utenti guest alla directory in Azure Portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="38324-110">For details, check out [Quickstart: Add guest users to your directory in the Azure portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

<span data-ttu-id="38324-111">Gli amministratori possono anche delegare le autorizzazioni per aggiungere guest ad altri nella propria organizzazione assegnando il ruolo di persona che invita guest.</span><span class="sxs-lookup"><span data-stu-id="38324-111">Admins can also delegate permissions to add guests to others in their organization by assigning the Guest Inviter role.</span></span> <span data-ttu-id="38324-112">Per altre informazioni, vedere [Abilitare la collaborazione esterna B2B e gestire gli utenti che possono invitare guest](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="38324-112">For more information, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span>

<span data-ttu-id="38324-113">Con Collaborazione B2B di Azure AD, le organizzazioni possono applicare criteri di accesso condizionale e autenticazione a più fattori (MFA) per gli utenti B2B.</span><span class="sxs-lookup"><span data-stu-id="38324-113">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="38324-114">Questi criteri possono essere applicati a livello di tenant, di app o di singolo utente, così come vengono abilitati per dipendenti a tempo pieno e membri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="38324-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="38324-115">Tali criteri vengono applicati all'organizzazione delle risorse.</span><span class="sxs-lookup"><span data-stu-id="38324-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="38324-116">Per altre informazioni, vedere [Accesso condizionale per gli utenti di Collaborazione B2B](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="38324-116">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="38324-117">Non è possibile bloccare singoli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="38324-117">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="38324-118">Gli utenti Guest già aggiunti tramite Azure AD B2B, Microsoft 365 groups o SharePoint sono pronti per l'invio.</span><span class="sxs-lookup"><span data-stu-id="38324-118">Guest users you have already added via Azure AD B2B, Microsoft 365 Groups, or SharePoint are ready to go.</span></span> <span data-ttu-id="38324-119">L'amministratore di Microsoft 365 o un proprietario del team può aggiungere tali Guest ai rispettivi team.</span><span class="sxs-lookup"><span data-stu-id="38324-119">The Microsoft 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="38324-120">Se Aggiungi un Guest direttamente al gruppo Microsoft 365 associato a un team, l'ospite otterrà l'accesso al team, ma il gruppo Microsoft 365 non genera un messaggio di invito per il cliente, quindi qualcuno del team deve avvisare l'ospite.</span><span class="sxs-lookup"><span data-stu-id="38324-120">If add a guest directly to the Microsoft 365 group associated with a team, the guest will get access to the team but the Microsoft 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="38324-121">Gli utenti guest sono soggetti ai limiti del servizio di [Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="38324-121">Guests are subject to  [Microsoft 365 or Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="38324-122">È possibile tenere traccia dei guest aggiunti in Azure AD o Centro sicurezza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="38324-122">You can track guest additions in Azure AD or the Microsoft 365 security center.</span></span> <span data-ttu-id="38324-123">L'aggiunta di un guest in Microsoft Teams è controllata e registrata come attività di amministrazione del gruppo di Azure AD "Membro aggiunto a gruppo".</span><span class="sxs-lookup"><span data-stu-id="38324-123">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="38324-124">Per altre informazioni, vedere [controllo e segnalazione di un utente di collaborazione B2B](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) e [ricerca nel log di controllo nel centro conformità](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span><span class="sxs-lookup"><span data-stu-id="38324-124">For more details, see [Auditing and reporting a B2B collaboration user](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) and [Search the audit log in the compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>


## <a name="related-topics"></a><span data-ttu-id="38324-125">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="38324-125">Related topics</span></span>

[<span data-ttu-id="38324-126">Autorizzare l'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38324-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)

[<span data-ttu-id="38324-127">Attivare o disattivare l'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38324-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)
