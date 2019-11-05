---
title: Eseguire una ricerca nel log di controllo per gli eventi in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Informazioni su come recuperare i dati di Microsoft teams dal log di controllo di Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 96197e7acf067675f3468b122c6fcc8c0386c010
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968017"
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="323cb-103">Eseguire una ricerca nel log di controllo per gli eventi in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="323cb-103">Search the audit log for events in Microsoft Teams</span></span>
==================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="323cb-104">Il log di controllo consente di analizzare attività specifiche in tutti i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="323cb-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="323cb-105">Per i team, Ecco alcune delle attività che vengono controllate:</span><span class="sxs-lookup"><span data-stu-id="323cb-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="323cb-106">Creazione di Team</span><span class="sxs-lookup"><span data-stu-id="323cb-106">Team creation</span></span>

- <span data-ttu-id="323cb-107">Eliminazione del team</span><span class="sxs-lookup"><span data-stu-id="323cb-107">Team deletion</span></span>

- <span data-ttu-id="323cb-108">Canale aggiunto</span><span class="sxs-lookup"><span data-stu-id="323cb-108">Added channel</span></span>

- <span data-ttu-id="323cb-109">Impostazione modificata</span><span class="sxs-lookup"><span data-stu-id="323cb-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="323cb-110">Gli eventi di controllo dei canali privati vengono registrati anche per i team e i canali standard.</span><span class="sxs-lookup"><span data-stu-id="323cb-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="323cb-111">Per visualizzare l'elenco completo delle attività controllate in Office 365, vedere [cercare il log di controllo nel centro conformità & sicurezza di office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="323cb-111">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="323cb-112">Attivare il controllo in teams</span><span class="sxs-lookup"><span data-stu-id="323cb-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="323cb-113">Prima di poter esaminare i dati di controllo, è necessario attivare prima di tutto il controllo nel [centro conformità & sicurezza](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="323cb-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="323cb-114">Per assistenza durante l'attivazione del controllo, leggere [attivare o disattivare la ricerca nel log di controllo di Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="323cb-114">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="323cb-115">I dati di controllo sono disponibili solo dal momento in cui è stato attivato il controllo.</span><span class="sxs-lookup"><span data-stu-id="323cb-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="323cb-116">Recuperare i dati di teams dal log di controllo</span><span class="sxs-lookup"><span data-stu-id="323cb-116">Retrieve Teams data from the audit log</span></span>

1. <span data-ttu-id="323cb-117">Per recuperare i log di controllo, accedere al [centro conformità & sicurezza](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="323cb-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="323cb-118">In **ricerca &** selezionare **Ricerca log di controllo**.</span><span class="sxs-lookup"><span data-stu-id="323cb-118">Under **Search & Investigation**, select **Audit log search**.</span></span>

2. <span data-ttu-id="323cb-119">Usare la **ricerca** per filtrare in base alle attività, alle date e agli utenti che si desidera controllare.</span><span class="sxs-lookup"><span data-stu-id="323cb-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>

3. <span data-ttu-id="323cb-120">Esportare i risultati in Excel per un'ulteriore analisi.</span><span class="sxs-lookup"><span data-stu-id="323cb-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="323cb-121">I dati di controllo sono visibili solo nel log di controllo se è attivato il controllo.</span><span class="sxs-lookup"><span data-stu-id="323cb-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="323cb-122">Video: TechTip: uso della ricerca nel log di controllo in teams</span><span class="sxs-lookup"><span data-stu-id="323cb-122">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="323cb-123">Partecipare a un responsabile del programma per Teams, che illustra come eseguire la ricerca di un log di controllo per i team nel centro conformità & sicurezza di Office 365.</span><span class="sxs-lookup"><span data-stu-id="323cb-123">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span> 

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
