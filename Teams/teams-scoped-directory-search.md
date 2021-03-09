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
ms.openlocfilehash: b1ba7de8cea23efc23f1eaa6c568d87b0d3ec750
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558325"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="59bc1-103">Usare la ricerca nella directory con ambito di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="59bc1-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="59bc1-104">La ricerca nell'ambito di Microsoft Teams consente alle organizzazioni di creare limiti virtuali che controllano come gli utenti possono trovare e comunicare con altri utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="59bc1-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="59bc1-105">Microsoft Teams consente alle organizzazioni di fornire visualizzazioni personalizzate della directory agli utenti.</span><span class="sxs-lookup"><span data-stu-id="59bc1-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="59bc1-106">Microsoft Teams usa [criteri di protezione delle informazioni](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) per supportare queste visualizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="59bc1-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="59bc1-107">Una volta abilitati i criteri, l'ambito dei risultati restituiti dalle ricerche di altri utenti (ad esempio per avviare una chat o per aggiungere membri a un team) verrà rientrato nell'ambito in base ai criteri configurati.</span><span class="sxs-lookup"><span data-stu-id="59bc1-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="59bc1-108">Gli utenti non saranno in grado di cercare o individuare alcun team quando è attivo l'ambito di ricerca, ma i membri esistenti in questi team possono aggiungere utenti, come consentito dai criteri di protezione delle informazioni attive.</span><span class="sxs-lookup"><span data-stu-id="59bc1-108">Users will not be able to search or discover any teams when scoped search is in effect, but existing members in those teams can add users, as allowed by active Information Barrier policies.</span></span>

> [!NOTE]
> <span data-ttu-id="59bc1-109">Negli ambienti ibridi di Exchange questa caratteristica funziona solo con le cassette postali di Exchange Online e non con le cassette postali locali.</span><span class="sxs-lookup"><span data-stu-id="59bc1-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="59bc1-110">Quando usare le ricerche nella directory con ambito?</span><span class="sxs-lookup"><span data-stu-id="59bc1-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="59bc1-111">Gli scenari che traggono vantaggio dalle ricerche nella directory con ambito sono simili a quelli dei criteri della Rubrica.</span><span class="sxs-lookup"><span data-stu-id="59bc1-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="59bc1-112">Ad esempio, è possibile usare la ricerca nella directory con ambito nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="59bc1-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="59bc1-113">L'organizzazione ha più società all'interno del tenant che si vogliono mantenere separate.</span><span class="sxs-lookup"><span data-stu-id="59bc1-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="59bc1-114">L'istituto di istruzione vuole limitare le chat tra docenti e studenti.</span><span class="sxs-lookup"><span data-stu-id="59bc1-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="59bc1-115">Per informazioni su come usare i criteri della rubrica, vedere Criteri per le [barriere linguistiche in Exchange Online.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)</span><span class="sxs-lookup"><span data-stu-id="59bc1-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59bc1-116">I criteri della rubrica forniscono solo una separazione virtuale degli utenti dal punto di vista della directory.</span><span class="sxs-lookup"><span data-stu-id="59bc1-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="59bc1-117">È anche importante tenere presente che i dati utente già memorizzati nella cache prima dell'applicazione dei criteri della rubrica nuovi o aggiornati rimarranno disponibili per gli utenti per un massimo di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="59bc1-117">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="59bc1-118">Attivare la ricerca nella directory con ambito</span><span class="sxs-lookup"><span data-stu-id="59bc1-118">Turn on scoped directory search</span></span>

1. <span data-ttu-id="59bc1-119">Usare i criteri di protezione delle informazioni per configurare l'organizzazione in sottogruppi virtuali.</span><span class="sxs-lookup"><span data-stu-id="59bc1-119">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="59bc1-120">Per altre informazioni, vedere [Definire i criteri di protezione delle informazioni.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)</span><span class="sxs-lookup"><span data-stu-id="59bc1-120">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="59bc1-121">Nell'interfaccia di amministrazione di Microsoft Teams, selezionare Impostazioni di Teams **a livello di**  >  **organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="59bc1-121">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="59bc1-122">In **Cerca,** accanto a Ricerca nella directory di ambito in Teams usando i criteri della rubrica **di Exchange (ABP),** attiva **l'interruttore.**</span><span class="sxs-lookup"><span data-stu-id="59bc1-122">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Ricerca nella directory con ambito nell'interfaccia di amministrazione di Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="59bc1-124">Il replica di questa modifica può richiedere alcune ore.</span><span class="sxs-lookup"><span data-stu-id="59bc1-124">This change can take a few hours to replicate.</span></span>
