---
title: Spostare utenti ed endpoint nel cloud
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Spostare utenti ed endpoint prima di rimuovere le autorizzazioni di un ambiente locale di Skype for Business.
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593909"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="e8873-103">Spostare gli utenti e gli endpoint necessari prima di rimuovere le autorizzazioni dell'ambiente locale</span><span class="sxs-lookup"><span data-stu-id="e8873-103">Move required users and endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="e8873-104">Questo articolo descrive come spostare gli utenti e gli endpoint dell'applicazione necessari nel cloud Microsoft prima di rimuovere le autorizzazioni dell'ambiente Skype for Business locale.</span><span class="sxs-lookup"><span data-stu-id="e8873-104">This article describes how to move required users and application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="e8873-105">Questo è il passaggio 1 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:</span><span class="sxs-lookup"><span data-stu-id="e8873-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="e8873-106">**Passaggio 1. Spostare tutti gli utenti e gli endpoint dell'applicazione necessari da locale a online.**</span><span class="sxs-lookup"><span data-stu-id="e8873-106">**Step 1. Move all required users and application endpoints from on-premises to online.**</span></span> <span data-ttu-id="e8873-107">(Questo articolo.</span><span class="sxs-lookup"><span data-stu-id="e8873-107">(This article.)</span></span>

- <span data-ttu-id="e8873-108">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="e8873-108">Step 2.</span></span> <span data-ttu-id="e8873-109">[Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="e8873-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="e8873-110">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="e8873-110">Step 3.</span></span> <span data-ttu-id="e8873-111">Rimuovere la distribuzione locale di [Skype for Business.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="e8873-111">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="e8873-112">Spostare tutti gli utenti necessari dall'ambiente locale al cloud</span><span class="sxs-lookup"><span data-stu-id="e8873-112">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="e8873-113">Tutti gli utenti che continueranno a utilizzare dopo aver completato la migrazione devono prima essere spostati dall'ambiente locale al cloud.</span><span class="sxs-lookup"><span data-stu-id="e8873-113">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="e8873-114">Gli utenti vengono spostati utilizzando gli strumenti di amministrazione locali.</span><span class="sxs-lookup"><span data-stu-id="e8873-114">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="e8873-115">Per informazioni dettagliate, vedere [Move users between on-premises and cloud.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="e8873-115">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="e8873-116">Sebbene sia possibile per gli utenti con account Skype for Business Server locali utilizzare Teams, questi utenti non dispongono delle funzionalità complete di Teams.</span><span class="sxs-lookup"><span data-stu-id="e8873-116">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="e8873-117">Questi utenti non possono interagire o federatire con altri utenti che usano ancora Skype for Business (online o locale).</span><span class="sxs-lookup"><span data-stu-id="e8873-117">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="e8873-118">Né questi utenti possono ricevere chiamate PSTN nel client Teams.</span><span class="sxs-lookup"><span data-stu-id="e8873-118">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="e8873-119">Pertanto, è necessario spostare questi utenti online.</span><span class="sxs-lookup"><span data-stu-id="e8873-119">Therefore, you must move these users to online.</span></span> <span data-ttu-id="e8873-120">Questo passaggio garantisce inoltre che tutti i contatti o le riunioni creati in Skype for Business Server siano migrati in Teams.</span><span class="sxs-lookup"><span data-stu-id="e8873-120">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="e8873-121">Per verificare se nella distribuzione locale sono presenti utenti rimanenti, eseguire il cmdlet seguente in una finestra di PowerShell di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e8873-121">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="e8873-122">Se vengono restituiti utenti, esaminare l'output per determinare se gli account devono essere spostati nel cloud e, per tali utenti, attenersi alla procedura [riportata di seguito.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="e8873-122">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="e8873-123">Per gli account utente che non sono più necessari, eseguire il cmdlet di PowerShell di Skype for Business Server seguente:</span><span class="sxs-lookup"><span data-stu-id="e8873-123">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="e8873-124">L'Disable-CsUser rimuoverà tutti gli attributi di Skype for Business per tutti gli utenti che soddisfano i criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="e8873-124">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="e8873-125">Prima di procedere, verificare che questi account non siano più necessari in futuro.</span><span class="sxs-lookup"><span data-stu-id="e8873-125">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a><span data-ttu-id="e8873-126">Spostare gli endpoint dell'applicazione ibrida locale in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8873-126">Move on-premises hybrid application endpoints to Microsoft 365</span></span>

1. <span data-ttu-id="e8873-127">Recuperare ed esportare le impostazioni dell'endpoint dell'applicazione ibrida locale eseguendo il comando di PowerShell di Skype for Business Server locale seguente:</span><span class="sxs-lookup"><span data-stu-id="e8873-127">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="e8873-128">Creare e creare nuove [licenze per i](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) nuovi account delle risorse in Microsoft 365 per sostituire gli endpoint dell'applicazione ibrida locale esistenti.</span><span class="sxs-lookup"><span data-stu-id="e8873-128">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="e8873-129">Associare i nuovi account delle risorse agli endpoint dell'applicazione ibrida esistenti.</span><span class="sxs-lookup"><span data-stu-id="e8873-129">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="e8873-130">Rimuovere i numeri di telefono definiti negli endpoint dell'applicazione ibrida locale eseguendo il comando di PowerShell di Skype for Business Server locale seguente:</span><span class="sxs-lookup"><span data-stu-id="e8873-130">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="e8873-131">Poiché è possibile che i numeri di telefono per questi account sono stati gestiti in Microsoft 365 anziché in locale, eseguire il comando seguente in PowerShell di Skype for Business online:</span><span class="sxs-lookup"><span data-stu-id="e8873-131">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. <span data-ttu-id="e8873-132">Assegnare numeri di telefono ai nuovi account delle risorse creati nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="e8873-132">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="e8873-133">Per ulteriori informazioni su come assegnare un numero di telefono a un account della risorsa, vedere l'articolo seguente: [Assegnare un numero di servizio](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span><span class="sxs-lookup"><span data-stu-id="e8873-133">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="e8873-134">Eliminare gli endpoint locali eseguendo il seguente comando di PowerShell di Skype for Business Server locale:</span><span class="sxs-lookup"><span data-stu-id="e8873-134">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="e8873-135">A questo punto è possibile [disabilitare la configurazione ibrida.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="e8873-135">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e8873-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8873-136">See also</span></span>

- [<span data-ttu-id="e8873-137">Rimuovere le autorizzazioni dell'ambiente Skype for Business locale</span><span class="sxs-lookup"><span data-stu-id="e8873-137">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="e8873-138">Disabilitare la configurazione ibrida</span><span class="sxs-lookup"><span data-stu-id="e8873-138">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="e8873-139">Rimuovere la distribuzione locale di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="e8873-139">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




