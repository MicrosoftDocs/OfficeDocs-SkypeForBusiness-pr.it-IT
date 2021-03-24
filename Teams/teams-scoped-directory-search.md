---
title: Usare la ricerca nella directory con ambito di Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare la ricerca nella directory con ambito Microsoft Teams per fornire visualizzazioni personalizzate della directory.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ede4b60878dbdd44edf369b0a3c1bb861ffe366
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094026"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="cd473-103">Usare la ricerca nella directory con ambito di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd473-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="cd473-104">La ricerca nella directory con ambito Microsoft Teams consente alle organizzazioni di creare limiti virtuali che controllano il modo in cui gli utenti possono trovare e comunicare con altri utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cd473-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="cd473-105">Microsoft Teams consente alle organizzazioni di fornire visualizzazioni personalizzate della directory agli utenti.</span><span class="sxs-lookup"><span data-stu-id="cd473-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="cd473-106">Microsoft Teams usa i [criteri Information Barrier per](/microsoft-365/compliance/information-barriers) supportare queste visualizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="cd473-106">Microsoft Teams uses [Information Barrier policies](/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="cd473-107">Una volta abilitati i criteri, l'ambito dei risultati restituiti dalle ricerche di altri utenti, ad esempio per avviare una chat o per aggiungere membri a un team, sarà in base ai criteri configurati.</span><span class="sxs-lookup"><span data-stu-id="cd473-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="cd473-108">Gli utenti non saranno in grado di cercare o individuare alcun team quando è attiva la ricerca con ambito, ma i membri esistenti in questi team possono aggiungere utenti, come consentito dai criteri di Protezione delle informazioni attivi.</span><span class="sxs-lookup"><span data-stu-id="cd473-108">Users will not be able to search or discover any teams when scoped search is in effect, but existing members in those teams can add users, as allowed by active Information Barrier policies.</span></span>

> [!NOTE]
> <span data-ttu-id="cd473-109">Negli ambienti ibridi di Exchange questa caratteristica funziona solo con le cassette postali di Exchange Online e non con le cassette postali locali.</span><span class="sxs-lookup"><span data-stu-id="cd473-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="cd473-110">Quando usare le ricerche nella directory con ambito?</span><span class="sxs-lookup"><span data-stu-id="cd473-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="cd473-111">Gli scenari che traggono vantaggio dalle ricerche nella directory con ambito sono simili a quelli dei criteri della rubrica.</span><span class="sxs-lookup"><span data-stu-id="cd473-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="cd473-112">Ad esempio, è possibile usare la ricerca nella directory con ambito nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd473-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="cd473-113">L'organizzazione ha più società all'interno del tenant che si vogliono mantenere separate.</span><span class="sxs-lookup"><span data-stu-id="cd473-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="cd473-114">L'istituto di istruzione vuole limitare le chat tra docenti e studenti.</span><span class="sxs-lookup"><span data-stu-id="cd473-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="cd473-115">Per informazioni su come usare i criteri della rubrica, vedere Criteri [di Protezione delle informazioni in Exchange Online.](/microsoft-365/compliance/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="cd473-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd473-116">I criteri della rubrica offrono solo una separazione virtuale degli utenti dal punto di vista della directory.</span><span class="sxs-lookup"><span data-stu-id="cd473-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="cd473-117">È anche importante tenere presente che tutti i dati degli utenti già memorizzati nella cache, prima dell'applicazione dei criteri della rubrica nuovi o aggiornati, rimarranno disponibili per gli utenti per un massimo di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="cd473-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="cd473-118">Attivare la ricerca nella directory con ambito</span><span class="sxs-lookup"><span data-stu-id="cd473-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="cd473-119">Usare i criteri Information Barrier per configurare l'organizzazione in sottogruppi virtuali.</span><span class="sxs-lookup"><span data-stu-id="cd473-119">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="cd473-120">Per altre informazioni, vedere [Definire i criteri di protezione delle informazioni.](/microsoft-365/compliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="cd473-120">For more information, see [Define Information Barrier policies](/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="cd473-121">Nell'interfaccia di amministrazione di Microsoft Teams selezionare **Impostazioni di Teams a livello di**  >  **organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="cd473-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="cd473-122">In **Cerca**, accanto a Cerca nella directory ambito **in Teams con** un criterio rubrica di Exchange , attivare l'interruttore **.**</span><span class="sxs-lookup"><span data-stu-id="cd473-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Ricerca nella directory con ambito nell'interfaccia di amministrazione di Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="cd473-124">La replica di questa modifica può richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="cd473-124">This change can take a few hours to replicate.</span></span>