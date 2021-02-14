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
description: Informazioni su come usare la ricerca nell'ambito di Microsoft Teams per fornire visualizzazioni personalizzate della directory.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4f478bba8c396f0f20b95f69f56c2ded556224d
ms.sourcegitcommit: 2300595db7779da7a127ae9ee16e474452df02d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49779930"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="ab5fa-103">Usare la ricerca nella directory con ambito di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ab5fa-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="ab5fa-104">La ricerca nell'ambito di Microsoft Teams consente alle organizzazioni di creare limiti virtuali che controllano come gli utenti possono trovare e comunicare con altri utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="ab5fa-105">Microsoft Teams consente alle organizzazioni di fornire visualizzazioni personalizzate della directory agli utenti.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="ab5fa-106">Microsoft Teams usa [criteri di protezione delle informazioni](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) per supportare queste visualizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="ab5fa-107">Una volta abilitati i criteri, l'ambito dei risultati restituiti dalle ricerche di altri utenti (ad esempio per avviare una chat o per aggiungere membri a un team) verrà rientrato nell'ambito in base ai criteri configurati.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="ab5fa-108">Gli utenti non saranno in grado di cercare o individuare i team quando è in vigore la ricerca con ambito.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="ab5fa-109">Negli ambienti ibridi di Exchange questa caratteristica funziona solo con le cassette postali di Exchange Online e non con le cassette postali locali.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="ab5fa-110">Quando usare le ricerche nella directory con ambito?</span><span class="sxs-lookup"><span data-stu-id="ab5fa-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="ab5fa-111">Gli scenari che traggono vantaggio dalle ricerche nella directory con ambito sono simili a quelli dei criteri della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="ab5fa-112">Ad esempio, è possibile usare la ricerca nella directory con ambito nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab5fa-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="ab5fa-113">L'organizzazione ha più società all'interno del tenant che si vogliono mantenere separate.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="ab5fa-114">L'istituto di istruzione vuole limitare le chat tra docenti e studenti.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="ab5fa-115">Per informazioni su come usare i criteri della rubrica, vedere Criteri per le [barriere linguistiche in Exchange Online.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="ab5fa-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab5fa-116">I criteri della rubrica forniscono solo una separazione virtuale degli utenti dal punto di vista della directory.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="ab5fa-117">È anche importante tenere presente che i dati utente già memorizzati nella cache prima dell'applicazione dei criteri della rubrica nuovi o aggiornati rimarranno disponibili per gli utenti fino a un massimo di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="ab5fa-118">Attivare la ricerca nella directory con ambito</span><span class="sxs-lookup"><span data-stu-id="ab5fa-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="ab5fa-119">Usare i criteri di protezione delle informazioni per configurare l'organizzazione in sottogruppi virtuali.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-119">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="ab5fa-120">Per altre informazioni, vedere [Definire i criteri di protezione delle informazioni.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="ab5fa-120">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="ab5fa-121">Nell'interfaccia di amministrazione di Microsoft Teams selezionare impostazioni di Teams **a livello di**  >  **organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="ab5fa-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="ab5fa-122">In **Cerca,** accanto a Ricerca nella directory di ambito in Teams usando i criteri della rubrica **di Exchange (ABP),** attiva **l'interruttore.**</span><span class="sxs-lookup"><span data-stu-id="ab5fa-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Ricerca directory con ambito nell'interfaccia di amministrazione di Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="ab5fa-124">Il replica di questa modifica può richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="ab5fa-124">This change can take a few hours to replicate.</span></span>
