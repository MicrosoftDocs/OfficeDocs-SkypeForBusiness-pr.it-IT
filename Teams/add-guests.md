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
localization_priority: Priority
description: Informazioni sugli strumenti che consentono a un amministratore di aggiungere nuovi utenti guest a un'organizzazione, inclusi i client desktop e Web di Microsoft Teams e il portale di collaborazione B2B di Azure Active Directory.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78f495b10e953a8e416c8cadd755a098c8c948a7
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753251"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="093b8-103">Aggiungere un utente guest a un team</span><span class="sxs-lookup"><span data-stu-id="093b8-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="093b8-104">Chiunque abbia un account di posta elettronica aziendale o personale, come Outlook, Gmail o altri, può partecipare come utente guest in Teams.</span><span class="sxs-lookup"><span data-stu-id="093b8-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="093b8-105">Gli amministratori possono aggiungere un nuovo utente guest all'organizzazione in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="093b8-105">As an admin, you can add a new guest user to the organization in a couple of ways:</span></span>
- <span data-ttu-id="093b8-106">Gli amministratori globali o di Teams e i proprietari dei team aggiungono un utente guest a un team nei client di Teams o nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="093b8-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="093b8-107">Per altre informazioni, leggere [Aggiungere utenti guest a un team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="093b8-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="093b8-108">Se non è stato ancora configurato l'accesso guest, seguire i passaggi nell'[elenco di controllo di accesso guest](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="093b8-108">If you haven't set up guest access yet, go through the steps in the [Guest access checklist](guest-access-checklist.md).</span></span>

> [!NOTE] 
> <span data-ttu-id="093b8-109">Questo non si applica quando l'opzione **Amministratori e utenti nel ruolo mittente dell'invito guest possono invitare** è abilitata.</span><span class="sxs-lookup"><span data-stu-id="093b8-109">This does not apply when **Admins and users in the guest inviter role can invite** is enabled.</span></span> <span data-ttu-id="093b8-110">Il motivo è che il ruolo mittente dell'invito non è supportato in Teams.</span><span class="sxs-lookup"><span data-stu-id="093b8-110">This is because the guest inviter role isn't supported in Teams.</span></span>

- <span data-ttu-id="093b8-111">È possibile aggiungere utenti guest all'organizzazione con la collaborazione B2B di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="093b8-111">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="093b8-112">Collaborazione B2B di Azure AD consente a un amministratore globale di invitare e autorizzare un gruppo di utenti esterni caricando un file con valori delimitati da virgole (CSV) di non più di 2000 righe sul portale di collaborazione B2B.</span><span class="sxs-lookup"><span data-stu-id="093b8-112">Azure AD B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="093b8-113">Per ulteriori dettagli, consultare [Collaborazione B2B di Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="093b8-113">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="093b8-114">Con Collaborazione B2B di Azure AD, le organizzazioni possono applicare criteri di accesso condizionale e autenticazione a più fattori (MFA) per gli utenti B2B.</span><span class="sxs-lookup"><span data-stu-id="093b8-114">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="093b8-115">Questi criteri possono essere applicati a livello di tenant, di app o di singolo utente, così come vengono abilitati per dipendenti a tempo pieno e membri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="093b8-115">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="093b8-116">Tali criteri vengono applicati all'organizzazione delle risorse.</span><span class="sxs-lookup"><span data-stu-id="093b8-116">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="093b8-117">Per altre informazioni, vedere [Accesso condizionale per gli utenti di Collaborazione B2B](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="093b8-117">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="093b8-118">Non è possibile bloccare singoli utenti guest.</span><span class="sxs-lookup"><span data-stu-id="093b8-118">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="093b8-119">Gli utenti guest che sono stati già aggiunti tramite B2B di Azure AD, Gruppi di Office 365 o SharePoint Online sono pronti.</span><span class="sxs-lookup"><span data-stu-id="093b8-119">Guest users you have already added via Azure AD B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="093b8-120">L'amministratore di Office 365 o un proprietario dei team può aggiungere questi utenti guest ai rispettivi team.</span><span class="sxs-lookup"><span data-stu-id="093b8-120">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="093b8-121">Se un team è già presente in un gruppo di Office 365 e viene aggiunto un utente guest al gruppo, il guest otterrà l'accesso al team.</span><span class="sxs-lookup"><span data-stu-id="093b8-121">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="093b8-122">L'aggiunta di un guest tramite il gruppo di Office 365 non genera un messaggio di posta elettronica di invito per il guest, pertanto una persona del team deve informarlo.</span><span class="sxs-lookup"><span data-stu-id="093b8-122">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="093b8-123">Gli utenti guest sono soggetti ai limiti del servizio di [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="093b8-123">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="093b8-124">È possibile tenere traccia dei guest aggiunti in Azure AD o Centro sicurezza &amp; conformità di Office 365.</span><span class="sxs-lookup"><span data-stu-id="093b8-124">You can track guest additions in Azure AD or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="093b8-125">L'aggiunta di un guest in Microsoft Teams è controllata e registrata come attività di amministrazione del gruppo di Azure AD "Membro aggiunto a gruppo".</span><span class="sxs-lookup"><span data-stu-id="093b8-125">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="093b8-126">Per ulteriori dettagli, vedere [Controllo e creazione di report per un utente di Collaborazione B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) e [Eseguire una ricerca nel log di controllo nel Centro sicurezza &amp; conformità di Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="093b8-126">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>


## <a name="more-information"></a><span data-ttu-id="093b8-127">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="093b8-127">More information</span></span>

[<span data-ttu-id="093b8-128">Autorizzare l'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="093b8-128">Authorize guest access in Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="093b8-129">Attivare o disattivare l'accesso guest in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="093b8-129">Turn on or turn off guest access in Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="093b8-130">Usare PowerShell per controllare l'accesso guest a un team</span><span class="sxs-lookup"><span data-stu-id="093b8-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
