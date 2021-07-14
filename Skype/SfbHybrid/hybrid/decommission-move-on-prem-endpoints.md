---
title: Eseguire la migrazione degli endpoint dell'applicazione ibrida nel cloud
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
description: Eseguire la migrazione degli endpoint dell'applicazione hyrid prima di rimuovere le autorizzazioni Skype for Business'ambiente locale.
ms.openlocfilehash: 7315ee807bb79b9186cd92ccc19074021b2fcfa1
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420801"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="3230b-103">Eseguire la migrazione degli endpoint dell'applicazione ibrida prima di rimuovere le autorizzazioni dell'ambiente locale</span><span class="sxs-lookup"><span data-stu-id="3230b-103">Migrate hybrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="3230b-104">In questo articolo viene descritto come spostare gli endpoint dell'applicazione ibrida necessari nel cloud Microsoft prima di rimuovere le autorizzazioni dell'ambiente Skype for Business locale.</span><span class="sxs-lookup"><span data-stu-id="3230b-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="3230b-105">Questo è il passaggio 3 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:</span><span class="sxs-lookup"><span data-stu-id="3230b-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="3230b-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="3230b-106">Step 1.</span></span> [<span data-ttu-id="3230b-107">Spostare tutti gli utenti necessari da locale a online</span><span class="sxs-lookup"><span data-stu-id="3230b-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="3230b-108">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="3230b-108">Step 2.</span></span> <span data-ttu-id="3230b-109">[Disabilitare la configurazione ibrida](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="3230b-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="3230b-110">**Passaggio 3. Eseguire la migrazione degli endpoint dell'applicazione ibrida da locale a online.**</span><span class="sxs-lookup"><span data-stu-id="3230b-110">**Step 3. Migrate hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="3230b-111">(Questo articolo)</span><span class="sxs-lookup"><span data-stu-id="3230b-111">(This article)</span></span>

- <span data-ttu-id="3230b-112">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="3230b-112">Step 4.</span></span> <span data-ttu-id="3230b-113">[Rimuovere la distribuzione locale Skype for Business .](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="3230b-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="3230b-114">Eseguire la migrazione di tutti gli endpoint dell'applicazione ibrida necessari da locale a online</span><span class="sxs-lookup"><span data-stu-id="3230b-114">Migrate all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="3230b-115">Prima di poter spostare questi endpoint in linea, è necessario assicurarsi di aver aggiornato i record DNS in modo che puntino a Microsoft 365 per tutti i domini sip utilizzati dagli endpoint.</span><span class="sxs-lookup"><span data-stu-id="3230b-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="3230b-116">Tenere presente che una volta aggiornato IL DNS in modo che punti a Microsoft 365, tutti gli endpoint dell'applicazione ibrida esistenti non saranno più individuabili fino al completamento di questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="3230b-116">Be aware that once you update DNS to point to Microsoft 365, any existing hybrid application endpoints will no longer be discoverable until you complete this step.</span></span> <span data-ttu-id="3230b-117">Poiché questo passaggio (creazione di account delle risorse online) non è possibile se i record DNS puntano a locali, è consigliabile pianificare entrambi i passaggi 2 e 3 nella stessa finestra di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="3230b-117">Since this step (creating online Resource Accounts) is not possible if DNS records point to on-premises you should plan to do both steps 2 and 3 in the same maintenance window.</span></span> <span data-ttu-id="3230b-118">Per ulteriori informazioni, vedere [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span><span class="sxs-lookup"><span data-stu-id="3230b-118">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="3230b-119">Recuperare ed esportare le impostazioni degli endpoint dell'applicazione ibrida locale eseguendo il comando di PowerShell Skype for Business Server locale seguente:</span><span class="sxs-lookup"><span data-stu-id="3230b-119">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="3230b-120">Creare e creare nuove [licenze per](/microsoftteams/manage-resource-accounts) i nuovi account Microsoft 365 per sostituire gli endpoint dell'applicazione ibrida locale esistenti.</span><span class="sxs-lookup"><span data-stu-id="3230b-120">Create and license new [Resource Accounts](/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="3230b-121">Associare i nuovi account delle risorse agli endpoint dell'applicazione ibrida esistenti.</span><span class="sxs-lookup"><span data-stu-id="3230b-121">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="3230b-122">Rimuovere i numeri di telefono definiti negli endpoint dell'applicazione ibrida locale eseguendo il comando di PowerShell Skype for Business Server locale seguente:</span><span class="sxs-lookup"><span data-stu-id="3230b-122">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="3230b-123">Poiché è possibile che i numeri di telefono per questi account sono stati gestiti in Microsoft 365 anziché in locale, eseguire il comando seguente in Skype for Business PowerShell online:</span><span class="sxs-lookup"><span data-stu-id="3230b-123">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="3230b-124">Assegnare numeri di telefono ai nuovi account delle risorse creati nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="3230b-124">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="3230b-125">Per ulteriori informazioni su come assegnare un numero di telefono a un account della risorsa, vedere l'articolo seguente: [Assegnare un numero di servizio](/microsoftteams/manage-resource-accounts#assign-a-service-number).</span><span class="sxs-lookup"><span data-stu-id="3230b-125">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="3230b-126">Eliminare gli endpoint locali eseguendo il comando di PowerShell Skype for Business Server locale seguente:</span><span class="sxs-lookup"><span data-stu-id="3230b-126">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="3230b-127">A questo punto è possibile rimuovere la distribuzione locale [Skype for Business distribuzione](decommission-remove-on-prem.md).</span><span class="sxs-lookup"><span data-stu-id="3230b-127">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3230b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3230b-128">See also</span></span>

- [<span data-ttu-id="3230b-129">Rimuovi le autorizzazioni dell'ambiente locale Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3230b-129">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="3230b-130">Spostare tutti gli utenti necessari da locale a online</span><span class="sxs-lookup"><span data-stu-id="3230b-130">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="3230b-131">Disabilitare la configurazione ibrida</span><span class="sxs-lookup"><span data-stu-id="3230b-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="3230b-132">Rimuovere la distribuzione locale di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3230b-132">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




