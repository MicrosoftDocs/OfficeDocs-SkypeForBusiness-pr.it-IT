---
title: Usare la ricerca nella directory con ambito di Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
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
description: Informazioni su come usare la ricerca di directory con ambito Microsoft teams per creare visualizzazioni personalizzate della directory.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b06e675e93dd022847fc7af202045c3ecdebe63
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341778"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a><span data-ttu-id="f891c-103">Usare la ricerca nella directory con ambito di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f891c-103">Use Microsoft Teams scoped directory search</span></span>

<span data-ttu-id="f891c-104">La ricerca di directory con ambito Microsoft teams consente alle organizzazioni di creare confini virtuali che controllano in che modo gli utenti possono trovare e comunicare con altri utenti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f891c-104">Microsoft Teams scoped directory search allows organizations to create virtual boundaries that control how users can find and communicate with other users in their organization.</span></span> 

<span data-ttu-id="f891c-105">Microsoft teams consente alle organizzazioni di creare visualizzazioni personalizzate della directory per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f891c-105">Microsoft Teams lets organizations provide custom views of the directory to their users.</span></span> <span data-ttu-id="f891c-106">Microsoft teams USA i [criteri di barriera delle informazioni](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) per supportare queste visualizzazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="f891c-106">Microsoft Teams uses [Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) to support these custom views.</span></span> <span data-ttu-id="f891c-107">Dopo l'abilitazione dei criteri, i risultati restituiti dalle ricerche di altri utenti, ad esempio per avviare una chat o per aggiungere membri a un team, verranno assegnati a un ambito secondo i criteri configurati.</span><span class="sxs-lookup"><span data-stu-id="f891c-107">Once the policies are enabled, the results returned by searches for other users (for example, to initiate a chat or to add members to a team) will be scoped according to the configured policies.</span></span> <span data-ttu-id="f891c-108">Gli utenti non potranno cercare o individuare i team quando è attiva la ricerca con ambito.</span><span class="sxs-lookup"><span data-stu-id="f891c-108">Users will not be able to search or discover teams when scoped search is in effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="f891c-109">In ambienti ibridi di Exchange questa funzionalità funziona solo con le cassette postali di Exchange Online e non con le cassette postali locali.</span><span class="sxs-lookup"><span data-stu-id="f891c-109">In Exchange hybrid environments, this feature only works with Exchange Online mailboxes, and not with on-premises mailboxes.</span></span>

## <a name="when-should-you-use-scoped-directory-searches"></a><span data-ttu-id="f891c-110">Quando è consigliabile usare ricerche di directory con ambito?</span><span class="sxs-lookup"><span data-stu-id="f891c-110">When should you use scoped directory searches?</span></span>

<span data-ttu-id="f891c-111">Gli scenari che traggono vantaggio dalle ricerche di directory con ambito sono simili a quelli degli scenari dei criteri Rubrica.</span><span class="sxs-lookup"><span data-stu-id="f891c-111">Scenarios that benefit from scoped directory searches are similar to address book policy scenarios.</span></span> <span data-ttu-id="f891c-112">Ad esempio, potresti voler usare la ricerca di directory con ambito nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f891c-112">For example, you may want to use scoped directory search in the following situations:</span></span>

- <span data-ttu-id="f891c-113">L'organizzazione ha più società all'interno del tenant che si vogliono mantenere separate.</span><span class="sxs-lookup"><span data-stu-id="f891c-113">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="f891c-114">L'istituto di istruzione vuole limitare le chat tra docenti e studenti.</span><span class="sxs-lookup"><span data-stu-id="f891c-114">Your school wants to limit chats between faculty and students.</span></span> 
 
<span data-ttu-id="f891c-115">Per informazioni su come usare i criteri Rubrica, leggere i [criteri di barriera delle informazioni in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span><span class="sxs-lookup"><span data-stu-id="f891c-115">To learn how to use address book policies, read [Information Barrier policies in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/information-barriers).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f891c-116">I criteri della rubrica prevedono solo una separazione virtuale degli utenti dal punto di vista della directory.</span><span class="sxs-lookup"><span data-stu-id="f891c-116">Address book policies provide only a virtual separation of users from directory perspective.</span></span> <span data-ttu-id="f891c-117">Gli utenti possono comunque avviare comunicazioni con altre persone fornendo indirizzi di posta elettronica completi.</span><span class="sxs-lookup"><span data-stu-id="f891c-117">Users can still initiate communications with others by providing complete email addresses.</span></span> <span data-ttu-id="f891c-118">È anche importante notare che tutti i dati degli utenti già memorizzati nella cache, prima dell'applicazione di criteri per la rubrica nuovi o aggiornati, rimarranno disponibili per un massimo di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="f891c-118">It is also important to note that any user data that had already been cached, prior to the enforcement of new or updated address book policies, will remain available to users for up to 30 days.</span></span>

## <a name="turn-on-scoped-directory-search"></a><span data-ttu-id="f891c-119">Attivare la ricerca di directory con ambito</span><span class="sxs-lookup"><span data-stu-id="f891c-119">Turn on scoped directory search</span></span>

1. <span data-ttu-id="f891c-120">Usare i criteri di barriera delle informazioni per configurare l'organizzazione in sottogruppi virtuali.</span><span class="sxs-lookup"><span data-stu-id="f891c-120">Use Information Barrier policies to configure your organization into virtual subgroups.</span></span> <span data-ttu-id="f891c-121">Per altre informazioni, vedere [definire i criteri di barriera delle informazioni](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span><span class="sxs-lookup"><span data-stu-id="f891c-121">For more information, see [Define Information Barrier policies](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies).</span></span>

2. <span data-ttu-id="f891c-122">Nell'interfaccia di amministrazione di Microsoft teams selezionare impostazioni per i**Team**di **Impostazioni** > a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f891c-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams settings**.</span></span>

3. <span data-ttu-id="f891c-123">In **ricerca**, accanto a **ricerca directory ambito in teams con i criteri di Rubrica di Exchange (SOA)**, attivare l' **attivazione.**</span><span class="sxs-lookup"><span data-stu-id="f891c-123">Under **Search**, next to **Scope directory search in Teams using an Exchange address book policy (ABP)**, turn the toggle **On**.</span></span>

    ![Ricerca di directory con ambito nell'interfaccia di amministrazione di Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> <span data-ttu-id="f891c-125">Questa modifica può richiedere fino a 24 ore per la replica.</span><span class="sxs-lookup"><span data-stu-id="f891c-125">This change can take up to 24 hours to replicate.</span></span>
