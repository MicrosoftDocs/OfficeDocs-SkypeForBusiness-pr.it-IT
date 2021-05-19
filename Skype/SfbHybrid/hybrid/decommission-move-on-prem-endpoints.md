---
title: Spostare gli endpoint dell'applicazione ibrida nel cloud
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
description: Spostare gli endpoint dell'applicazione hyrid prima di rimuovere le autorizzazioni Skype for Business'ambiente locale.
ms.openlocfilehash: 562da9e8e83684ab3ff532be68190161ffc412b5
ms.sourcegitcommit: 02703e8f9a512848e158a3a4f38d84501ad5f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52526719"
---
# <a name="move-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="8fc44-103">Spostare gli endpoint dell'applicazione ibrida prima di rimuovere le autorizzazioni dell'ambiente locale</span><span class="sxs-lookup"><span data-stu-id="8fc44-103">Move hybrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="8fc44-104">In questo articolo viene descritto come spostare gli endpoint dell'applicazione ibrida necessari nel cloud Microsoft prima di rimuovere le autorizzazioni dell'ambiente Skype for Business locale.</span><span class="sxs-lookup"><span data-stu-id="8fc44-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="8fc44-105">Questo è il passaggio 3 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:</span><span class="sxs-lookup"><span data-stu-id="8fc44-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="8fc44-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="8fc44-106">Step 1.</span></span> [<span data-ttu-id="8fc44-107">Spostare tutti gli utenti necessari da locale a online</span><span class="sxs-lookup"><span data-stu-id="8fc44-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="8fc44-108">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="8fc44-108">Step 2.</span></span> <span data-ttu-id="8fc44-109">[Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="8fc44-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="8fc44-110">**Passaggio 3. Spostare gli endpoint dell'applicazione ibrida da locale a online.**</span><span class="sxs-lookup"><span data-stu-id="8fc44-110">**Step 3. Move hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="8fc44-111">(Questo articolo)</span><span class="sxs-lookup"><span data-stu-id="8fc44-111">(This article)</span></span>

- <span data-ttu-id="8fc44-112">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="8fc44-112">Step 4.</span></span> <span data-ttu-id="8fc44-113">[Rimuovere la distribuzione locale Skype for Business .](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="8fc44-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="8fc44-114">Spostare tutti gli endpoint dell'applicazione ibrida necessari da locale a online</span><span class="sxs-lookup"><span data-stu-id="8fc44-114">Move all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="8fc44-115">Prima di poter spostare questi endpoint in linea, è necessario assicurarsi di aver aggiornato i record DNS in modo che puntino a Microsoft 365 per tutti i domini sip utilizzati dagli endpoint.</span><span class="sxs-lookup"><span data-stu-id="8fc44-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="8fc44-116">Non è possibile creare account di risorse online se i record DNS puntano a locali.</span><span class="sxs-lookup"><span data-stu-id="8fc44-116">It is not possible to create online Resource Accounts if DNS records point to on-premises.</span></span> <span data-ttu-id="8fc44-117">Per ulteriori informazioni, vedere [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="8fc44-117">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="8fc44-118">Recuperare ed esportare le impostazioni degli endpoint dell'applicazione ibrida locale eseguendo il comando di PowerShell Skype for Business Server locale seguente:</span><span class="sxs-lookup"><span data-stu-id="8fc44-118">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="8fc44-119">Creare e creare nuove [licenze per](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) i nuovi account Microsoft 365 per sostituire gli endpoint dell'applicazione ibrida locale esistenti.</span><span class="sxs-lookup"><span data-stu-id="8fc44-119">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="8fc44-120">Associare i nuovi account delle risorse agli endpoint dell'applicazione ibrida esistenti.</span><span class="sxs-lookup"><span data-stu-id="8fc44-120">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="8fc44-121">Rimuovere i numeri di telefono definiti negli endpoint dell'applicazione ibrida locale eseguendo il comando di PowerShell Skype for Business Server locale seguente:</span><span class="sxs-lookup"><span data-stu-id="8fc44-121">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="8fc44-122">Poiché è possibile che i numeri di telefono per questi account sono stati gestiti in Microsoft 365 anziché in locale, eseguire il comando seguente in Skype for Business PowerShell online:</span><span class="sxs-lookup"><span data-stu-id="8fc44-122">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="8fc44-123">Assegnare numeri di telefono ai nuovi account delle risorse creati nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="8fc44-123">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="8fc44-124">Per ulteriori informazioni su come assegnare un numero di telefono a un account della risorsa, vedere l'articolo seguente: [Assegnare un numero di servizio](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span><span class="sxs-lookup"><span data-stu-id="8fc44-124">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="8fc44-125">Eliminare gli endpoint locali eseguendo il comando di PowerShell Skype for Business Server locale seguente:</span><span class="sxs-lookup"><span data-stu-id="8fc44-125">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="8fc44-126">A questo punto è possibile rimuovere la distribuzione locale [Skype for Business distribuzione](decommission-remove-on-prem.md).</span><span class="sxs-lookup"><span data-stu-id="8fc44-126">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8fc44-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fc44-127">See also</span></span>

- [<span data-ttu-id="8fc44-128">Rimuovi le autorizzazioni dell'ambiente locale Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8fc44-128">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="8fc44-129">Spostare tutti gli utenti necessari da locale a online</span><span class="sxs-lookup"><span data-stu-id="8fc44-129">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="8fc44-130">Disabilitare la configurazione ibrida</span><span class="sxs-lookup"><span data-stu-id="8fc44-130">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="8fc44-131">Rimuovere la distribuzione locale di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8fc44-131">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




