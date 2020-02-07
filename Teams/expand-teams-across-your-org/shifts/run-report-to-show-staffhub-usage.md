---
title: Eseguire un report per mostrare l'utilizzo di StaffHub attivo
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Informazioni su come eseguire un report per ottenere un elenco di utenti attivi di StaffHub nell'organizzazione.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe7851e57cd6d812d0b8904668ca5fd67fd5999d
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826694"
---
# <a name="run-a-report-to-show-active-staffhub-usage"></a><span data-ttu-id="9ce62-103">Eseguire un report per mostrare l'utilizzo di StaffHub attivo</span><span class="sxs-lookup"><span data-stu-id="9ce62-103">Run a report to show active StaffHub usage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ce62-104">Efficace 31 dicembre 2019, Microsoft StaffHub sarà ritirato.</span><span class="sxs-lookup"><span data-stu-id="9ce62-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="9ce62-105">Stiamo costruendo funzionalità di StaffHub in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="9ce62-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="9ce62-106">Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo.</span><span class="sxs-lookup"><span data-stu-id="9ce62-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="9ce62-107">StaffHub smetterà di funzionare per tutti gli utenti il 31 dicembre 2019.</span><span class="sxs-lookup"><span data-stu-id="9ce62-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="9ce62-108">Chiunque tenti di aprire StaffHub verrà visualizzato un messaggio che li indirizza a scaricare teams.</span><span class="sxs-lookup"><span data-stu-id="9ce62-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="9ce62-109">Per altre informazioni, vedere [Microsoft StaffHub per ritirarsi](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="9ce62-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="9ce62-110">Seguire i passaggi di questo articolo per eseguire un report per ottenere un elenco di utenti attivi di StaffHub nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9ce62-110">Use the steps in this article to run a report to get a list of active StaffHub users in your organization.</span></span> <span data-ttu-id="9ce62-111">Queste informazioni possono essere utili quando si preparano a [trasferire i team di StaffHub a Microsoft teams](move-staffhub-teams-to-shifts-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9ce62-111">This information may come in handy when you prepare to [move your StaffHub teams to Microsoft Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span> <span data-ttu-id="9ce62-112">Nel report è necessario includere le comunicazioni quando si effettua il passaggio da StaffHub a teams.</span><span class="sxs-lookup"><span data-stu-id="9ce62-112">From the report, you'll know who you need to include in your communications when you make the switch from StaffHub to Teams.</span></span>

<span data-ttu-id="9ce62-113">Per eseguire la procedura descritta in questo articolo, è necessario avere Azure AD Premium.</span><span class="sxs-lookup"><span data-stu-id="9ce62-113">You need to have Azure AD Premium to perform the steps in this article.</span></span>

1. <span data-ttu-id="9ce62-114">Accedere a Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="9ce62-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="9ce62-115">Nel riquadro sinistro fare clic sulla risorsa di **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="9ce62-115">In the left pane, click the **Azure Active Directory** resource.</span></span>
3. <span data-ttu-id="9ce62-116">In **monitoraggio**fare clic su **sign-ins**.</span><span class="sxs-lookup"><span data-stu-id="9ce62-116">Under **Monitoring**, click **Sign-ins**.</span></span>
4. <span data-ttu-id="9ce62-117">In **applicazione**digitare **Microsoft StaffHub**.</span><span class="sxs-lookup"><span data-stu-id="9ce62-117">Under **Application**, type **Microsoft StaffHub**.</span></span>
5. <span data-ttu-id="9ce62-118">Impostare l'intervallo di date desiderato per il report e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="9ce62-118">Set the date range that you want for the report, and then click **Apply**.</span></span> 

    ![Schermata che mostra i passaggi per visualizzare l'uso di Active StaffHub](../../media/staffhub-active-usage-report.png)

## <a name="related-topics"></a><span data-ttu-id="9ce62-120">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9ce62-120">Related topics</span></span>

- [<span data-ttu-id="9ce62-121">Spostare i team di Microsoft StaffHub in turni in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9ce62-121">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
