---
title: Eseguire un report per mostrare l'utilizzo di Active StaffHub
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Informazioni su come eseguire un report per ottenere un elenco di utenti attivi di StaffHub nell'organizzazione.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1d13052751a43f3dba3e17c12d8e66d9afaf9dd
ms.sourcegitcommit: 6d5f09acdcdc8d5a36f7ac785349209e7496f17d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2019
ms.locfileid: "36184045"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="6f36f-103">Eseguire un report per mostrare l'utilizzo di Active StaffHub</span><span class="sxs-lookup"><span data-stu-id="6f36f-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f36f-104">Efficace il 1 ° ottobre 2019, Microsoft StaffHub sarà ritirato.</span><span class="sxs-lookup"><span data-stu-id="6f36f-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="6f36f-105">Stiamo costruendo funzionalità di StaffHub in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="6f36f-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="6f36f-106">Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo.</span><span class="sxs-lookup"><span data-stu-id="6f36f-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="6f36f-107">StaffHub smetterà di funzionare per tutti gli utenti il 1 ° ottobre 2019.</span><span class="sxs-lookup"><span data-stu-id="6f36f-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="6f36f-108">Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams.</span><span class="sxs-lookup"><span data-stu-id="6f36f-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="6f36f-109">Per altre informazioni, vedere [Microsoft StaffHub per](microsoft-staffhub-to-be-retired.md)ritirarsi.</span><span class="sxs-lookup"><span data-stu-id="6f36f-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="6f36f-110">Seguire i passaggi di questo articolo per eseguire un report per ottenere un elenco di utenti attivi di StaffHub nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6f36f-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="6f36f-111">Queste informazioni possono essere utili quando si preparano a [trasferire i team di StaffHub a Microsoft teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6f36f-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="6f36f-112">Nel report è necessario includere le comunicazioni quando si effettua il passaggio da StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="6f36f-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="6f36f-113">Per eseguire la procedura descritta in questo articolo, è necessario avere Azure AD Premium.</span><span class="sxs-lookup"><span data-stu-id="6f36f-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="6f36f-114">Accedere a Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="6f36f-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="6f36f-115">Nel riquadro sinistro fare clic sulla risorsa di **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="6f36f-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="6f36f-116">In **monitoraggio**fare clic su **sign-ins**.</span><span class="sxs-lookup"><span data-stu-id="6f36f-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="6f36f-117">In **applicazione**digitare **Microsoft StaffHub**.</span><span class="sxs-lookup"><span data-stu-id="6f36f-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="6f36f-118">Impostare l'intervallo di date desiderato per il report e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="6f36f-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![Schermata che mostra i passaggi per visualizzare l'uso di StaffHub attivo](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="6f36f-120">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6f36f-120">Related topics</span></span>

- [<span data-ttu-id="6f36f-121">Spostare i team di Microsoft StaffHub in turni in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6f36f-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
