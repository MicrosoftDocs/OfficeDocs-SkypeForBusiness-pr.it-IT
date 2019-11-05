---
title: Inserire un utente o un team di Microsoft teams in blocco legale
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Imparerai a inserire un utente o un team di Microsoft teams in blocco legale usando il centro conformità & sicurezza e scopri cosa richiede un blocco legale in base ai requisiti dei dati.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25bd8e235be79ed805a854cbda2b4947f1c1269b
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968037"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a><span data-ttu-id="ca520-103">Inserire un utente o un team di Microsoft teams in blocco legale</span><span class="sxs-lookup"><span data-stu-id="ca520-103">Place a Microsoft Teams user or team on legal hold</span></span>
==================================================

<span data-ttu-id="ca520-104">Per inserire un utente o un team in blocco legale, passare al [centro conformità & sicurezza](https://go.microsoft.com/fwlink/?linkid=854628).</span><span class="sxs-lookup"><span data-stu-id="ca520-104">To put a user or a team on Legal Hold, navigate to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=854628).</span></span> <span data-ttu-id="ca520-105">Quando si crea un nuovo caso, viene visualizzata l'opzione per posizionare le cassette postali o i siti in attesa.</span><span class="sxs-lookup"><span data-stu-id="ca520-105">When you create a new case, you are presented with the option to place mailboxes or sites on hold.</span></span>

> [!NOTE]
> <span data-ttu-id="ca520-106">L'immissione di un utente in blocco non inserisce automaticamente un gruppo in attesa o viceversa.</span><span class="sxs-lookup"><span data-stu-id="ca520-106">Placing a user on hold does not automatically place a group on hold or vice-versa.</span></span>

> [!NOTE]
> <span data-ttu-id="ca520-107">Non è ancora supportata la configurazione per l'esenzione legale dei messaggi del canale privato.</span><span class="sxs-lookup"><span data-stu-id="ca520-107">We don’t yet support configuration for legal hold of private channel messages.</span></span> <span data-ttu-id="ca520-108">È supportata la riserva legale dei file condivisi nei canali privati.</span><span class="sxs-lookup"><span data-stu-id="ca520-108">Legal hold of files shared in private channels is supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca520-109">Quando un utente o un gruppo viene messo in attesa, verranno mantenute tutte le copie del messaggio.</span><span class="sxs-lookup"><span data-stu-id="ca520-109">When a user or group is placed on hold, all message copies will be retained.</span></span> <span data-ttu-id="ca520-110">Esempio: Clay ha inviato un messaggio in un canale e quindi ha modificato il messaggio.</span><span class="sxs-lookup"><span data-stu-id="ca520-110">Example: Clay posted a message in a channel and then modified the message.</span></span> <span data-ttu-id="ca520-111">In uno scenario di blocco vengono mantenute entrambe le copie del messaggio.</span><span class="sxs-lookup"><span data-stu-id="ca520-111">In a hold scenario, both copies of the message are retained.</span></span> <span data-ttu-id="ca520-112">Senza blocco legale, viene mantenuto solo il messaggio più recente.</span><span class="sxs-lookup"><span data-stu-id="ca520-112">Without Legal Hold, only the latest message is retained.</span></span>

<span data-ttu-id="ca520-113">Nella figura seguente è presente un'indagine che prevede l'uso di argilla.</span><span class="sxs-lookup"><span data-stu-id="ca520-113">In the figure below, there is an investigation involving Clay.</span></span> <span data-ttu-id="ca520-114">Clay è un membro del team broker-dealer.</span><span class="sxs-lookup"><span data-stu-id="ca520-114">Clay is a member of the Brokers-Dealers team.</span></span>

<span data-ttu-id="ca520-115">Se avevamo bisogno di tenere legale tutte le posizioni che Clay avrebbe potuto discutere dei piani di brokeraggio, assicurati che il sito di SharePoint del team venga aggiunto all'elenco dei siti di blocco legale, oltre al sito di OneDrive for business di Clay.</span><span class="sxs-lookup"><span data-stu-id="ca520-115">If we needed to Legal Hold all the places Clay could have discussed Brokering plans, ensure that the team’s SharePoint site is added to the Legal Hold site list, as well as Clay’s OneDrive for Business site.</span></span>

![Screenshot della finestra di dialogo Crea un nuovo blocco.](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

<span data-ttu-id="ca520-117">Per ricapitolare, usare la tabella seguente per capire cosa occorre inserire in blocco legale in base ai requisiti dei dati:</span><span class="sxs-lookup"><span data-stu-id="ca520-117">To recap, use the table below to understand what needs to be placed on Legal Hold based on data requirements:</span></span>

|<span data-ttu-id="ca520-118">Scenario</span><span class="sxs-lookup"><span data-stu-id="ca520-118">Scenario</span></span>  |<span data-ttu-id="ca520-119">Cosa posizionare in blocco</span><span class="sxs-lookup"><span data-stu-id="ca520-119">What to place on hold</span></span>  |
|---------|---------|
|<span data-ttu-id="ca520-120">**Chat private di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="ca520-120">**Microsoft Teams Private Chats**</span></span>     |<span data-ttu-id="ca520-121">Cassetta postale dell'utente</span><span class="sxs-lookup"><span data-stu-id="ca520-121">User mailbox</span></span>         |
|<span data-ttu-id="ca520-122">**Chat di canale di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="ca520-122">**Microsoft Teams Channel Chats**</span></span>    |<span data-ttu-id="ca520-123">Cassetta postale del gruppo usata per il team</span><span class="sxs-lookup"><span data-stu-id="ca520-123">Group mailbox used for the team</span></span>         |
|<span data-ttu-id="ca520-124">**Contenuto di Microsoft Teams (ad esempio wiki, file)**</span><span class="sxs-lookup"><span data-stu-id="ca520-124">**Microsoft Teams Content (e.g. Wiki, Files)**</span></span>     |<span data-ttu-id="ca520-125">Sito di SharePoint usato dal team</span><span class="sxs-lookup"><span data-stu-id="ca520-125">SharePoint site used by the team</span></span>         |
|<span data-ttu-id="ca520-126">**Contenuto privato**</span><span class="sxs-lookup"><span data-stu-id="ca520-126">**Private Content**</span></span>     |<span data-ttu-id="ca520-127">Sito di OneDrive for business dell'utente</span><span class="sxs-lookup"><span data-stu-id="ca520-127">OneDrive for Business site of the user</span></span>         |
