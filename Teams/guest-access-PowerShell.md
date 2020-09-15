---
title: Usare PowerShell per controllare l'accesso guest a un team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni su come usare PowerShell per consentire o bloccare l'accesso Guest a tutti i team o a team specifici in Microsoft teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c8a2e23f5c03420c4b0ce644a80e0733f9f69a5
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814335"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="3e694-103">Usare PowerShell per controllare l'accesso guest a un team</span><span class="sxs-lookup"><span data-stu-id="3e694-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="3e694-104">Oltre a usare l'interfaccia di amministrazione di Microsoft 365 e il portale di Azure Active Directory (Azure AD), è possibile usare Windows PowerShell per controllare l'accesso guest.</span><span class="sxs-lookup"><span data-stu-id="3e694-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="3e694-105">Con PowerShell è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e694-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="3e694-106">Consentire o bloccare l'accesso Guest a tutti i team e ai gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3e694-106">Allow or block guest access to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="3e694-107">Consentire l'aggiunta di Guest a tutti i team e ai gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3e694-107">Allow guests to be added to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="3e694-108">Consentire o bloccare gli utenti Guest da un team specifico o da un gruppo di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3e694-108">Allow or block guest users from a specific team or Microsoft 365 group</span></span>

<span data-ttu-id="3e694-109">Per informazioni dettagliate, vedere "usare PowerShell per controllare l'accesso guest" in [gestire l'accesso guest nei gruppi di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span><span class="sxs-lookup"><span data-stu-id="3e694-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span>

  
<span data-ttu-id="3e694-110">È anche possibile usare PowerShell per consentire o bloccare un utente guest in base al proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="3e694-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="3e694-111">Ad esempio, supponiamo che la tua azienda (contoso) abbia una partnership con un'altra azienda (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="3e694-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="3e694-112">È possibile aggiungere Fabrikam all'elenco consentiti in modo che gli utenti possano aggiungere tali Guest ai rispettivi gruppi.</span><span class="sxs-lookup"><span data-stu-id="3e694-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="3e694-113">Per altre informazioni, vedere [consentire/bloccare l'accesso Guest ai gruppi di Microsoft 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="3e694-113">For more information, see [Allow/Block guest access to Microsoft 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="3e694-114">Se si vuole bloccare gli ospiti in teams e si vuole comunque consentire loro di accedere ai siti di SharePoint, è possibile usare i cmdlet di Azure AD PowerShell per disabilitare il parametro AllowGuestsToAccessGroups nell'oggetto società, presupponendo che la condivisione esterna sia attivata per i siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3e694-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD PowerShell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="3e694-115">Usare PowerShell per attivare o disattivare l'accesso Guest</span><span class="sxs-lookup"><span data-stu-id="3e694-115">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="3e694-116">Scaricare il modulo di PowerShell per Skype for business online da https://www.microsoft.com/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="3e694-116">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="3e694-117">Connettere una sessione di PowerShell all'endpoint di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="3e694-117">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="3e694-118">Skype for Business Online Connector fa attualmente parte del modulo di PowerShell più recente di teams.</span><span class="sxs-lookup"><span data-stu-id="3e694-118">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="3e694-119">Se si usa l'ultima [versione pubblica di PowerShell per Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/), non è necessario installare il connettore Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="3e694-119">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ```powershell
    Import-Module -Name MicrosoftTeams
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
    
3.  <span data-ttu-id="3e694-120">Controlla la configurazione e, se lo `AllowGuestUser` è `$False` , usa il cmdlet [set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) per impostarlo su `$True` .</span><span class="sxs-lookup"><span data-stu-id="3e694-120">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```powershell
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="3e694-121">È ora possibile avere utenti guest in teams per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3e694-121">You can now have guest users in Teams for your organization.</span></span>


## <a name="guest-access-vs-external-access"></a><span data-ttu-id="3e694-122">Accesso guest e accesso esterno</span><span class="sxs-lookup"><span data-stu-id="3e694-122">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
