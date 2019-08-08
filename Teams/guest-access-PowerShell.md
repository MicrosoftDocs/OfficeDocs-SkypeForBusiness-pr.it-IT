---
title: Usare PowerShell per controllare l'accesso Guest a un team
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Usare PowerShell per consentire o bloccare l'accesso Guest ai team in Microsoft teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e106dc56f56b5e26dd56384931deeecdd889305
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235879"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="cc4a9-103">Usare PowerShell per controllare l'accesso Guest a un team</span><span class="sxs-lookup"><span data-stu-id="cc4a9-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="cc4a9-104">Oltre a usare l'interfaccia di amministrazione di Microsoft 365 e il portale di Azure Active Directory (Azure AD), è possibile usare Windows PowerShell per controllare l'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="cc4a9-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="cc4a9-105">Con PowerShell è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc4a9-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="cc4a9-106">Consentire o bloccare l'accesso Guest a tutti i team e gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="cc4a9-106">Allow or block guest access to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="cc4a9-107">Consentire l'aggiunta di Guest a tutti i team e gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="cc4a9-107">Allow guests to be added to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="cc4a9-108">Consentire o bloccare gli utenti Guest da un team specifico o da un gruppo di Office 365</span><span class="sxs-lookup"><span data-stu-id="cc4a9-108">Allow or block guest users from a specific team or Office 365 group</span></span>

<span data-ttu-id="cc4a9-109">Per informazioni dettagliate, vedere "usare PowerShell per controllare l'accesso guest" in [gestire l'accesso guest nei gruppi di Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span><span class="sxs-lookup"><span data-stu-id="cc4a9-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span></span>
  
<span data-ttu-id="cc4a9-110">È anche possibile usare PowerShell per consentire o bloccare un utente guest in base al proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="cc4a9-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="cc4a9-111">Ad esempio, supponiamo che la tua azienda (contoso) abbia una partnership con un'altra azienda (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="cc4a9-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="cc4a9-112">È possibile aggiungere Fabrikam all'elenco consentiti in modo che gli utenti possano aggiungere tali Guest ai rispettivi gruppi.</span><span class="sxs-lookup"><span data-stu-id="cc4a9-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="cc4a9-113">Per altre informazioni, vedere [consentire/bloccare l'accesso Guest ai gruppi di Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="cc4a9-113">For more information, see [Allow/Block guest access to Office 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="cc4a9-114">Se si vuole bloccare gli ospiti in teams e si vuole comunque consentire loro di accedere ai siti di SharePoint, è possibile usare i cmdlet di Azure AD PowerShell per disabilitare il parametro AllowGuestsToAccessGroups nell'oggetto società, presupponendo che la condivisione esterna sia attivata per i siti di SharePoint .</span><span class="sxs-lookup"><span data-stu-id="cc4a9-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="cc4a9-115">Accesso guest e accesso esterno</span><span class="sxs-lookup"><span data-stu-id="cc4a9-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
