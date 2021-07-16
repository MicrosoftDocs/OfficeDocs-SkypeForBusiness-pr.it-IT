---
title: Disabilitare la distribuzione ibrida per completare la migrazione Teams solo
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: Questo articolo include la procedura dettagliata per disabilitare l'ambiente ibrido come parte del consolidamento del cloud per Teams e Skype for Business.
ms.openlocfilehash: 87bd1f6e0dcabed067174972dd0f0fc51149beb0
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453645"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a><span data-ttu-id="ae95d-103">Disabilitare la configurazione ibrida per completare la migrazione a Teams solo</span><span class="sxs-lookup"><span data-stu-id="ae95d-103">Disable your hybrid configuration to complete migration to Teams Only</span></span> 

<span data-ttu-id="ae95d-104">In questo articolo viene descritto come disabilitare la configurazione ibrida prima di rimuovere le autorizzazioni dell'ambiente Skype for Business locale.</span><span class="sxs-lookup"><span data-stu-id="ae95d-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="ae95d-105">Questo è il passaggio 2 della procedura seguente per rimuovere le autorizzazioni dell'ambiente locale:</span><span class="sxs-lookup"><span data-stu-id="ae95d-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="ae95d-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="ae95d-106">Step 1.</span></span> <span data-ttu-id="ae95d-107">[Spostare tutti gli utenti necessari da locale a online.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="ae95d-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="ae95d-108">**Passaggio 2. Disabilitare la configurazione ibrida.**</span><span class="sxs-lookup"><span data-stu-id="ae95d-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="ae95d-109">(Questo articolo)</span><span class="sxs-lookup"><span data-stu-id="ae95d-109">(This article)</span></span>

- <span data-ttu-id="ae95d-110">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="ae95d-110">Step 3.</span></span> <span data-ttu-id="ae95d-111">[Eseguire la migrazione degli endpoint dell'applicazione ibrida da locale a online.](decommission-move-on-prem-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="ae95d-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="ae95d-112">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="ae95d-112">Step 4.</span></span> <span data-ttu-id="ae95d-113">[Rimuovere la distribuzione locale Skype for Business .](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="ae95d-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ae95d-114">I passaggi 2 e 3 devono essere evasi nella stessa finestra di manutenzione perché gli endpoint delle applicazioni ibride esistenti non saranno individuabili tra i passaggi 2 e il completamento del passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="ae95d-114">Steps 2 and 3 should be done in the same maintenance window because any existing hybrid application endpoints will not be discoverable between steps 2 and completion of step 3.</span></span>


## <a name="summary"></a><span data-ttu-id="ae95d-115">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="ae95d-115">Summary</span></span>

<span data-ttu-id="ae95d-116">Dopo aver aggiornato tutti gli utenti da Skype for Business locale a Teams Solo in Microsoft 365, è possibile rimuovere le autorizzazioni per la distribuzione Skype for Business locale.</span><span class="sxs-lookup"><span data-stu-id="ae95d-116">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span>

<span data-ttu-id="ae95d-117">Prima di rimuovere le autorizzazioni per la distribuzione di Skype for Business locale e rimuovere qualsiasi hardware, è necessario separare logicamente la distribuzione locale da Microsoft 365 disabilitando la distribuzione ibrida.</span><span class="sxs-lookup"><span data-stu-id="ae95d-117">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="ae95d-118">La disabilitazione ibrida prevede i quattro passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae95d-118">Disabling hybrid consists of the following four steps:</span></span>

1. <span data-ttu-id="ae95d-119">[Aggiornare i record DNS in modo che puntino Microsoft 365](#update-dns-to-point-to-microsoft-365).</span><span class="sxs-lookup"><span data-stu-id="ae95d-119">[Update DNS records to point to Microsoft 365](#update-dns-to-point-to-microsoft-365).</span></span>

2. <span data-ttu-id="ae95d-120">[Modificare la modalità di coesistenza per l'organizzazione Teams solo](#change-the-coexistence-mode-for-your-organization-to-teams-only).</span><span class="sxs-lookup"><span data-stu-id="ae95d-120">[Change the coexistence mode for your organization to Teams Only](#change-the-coexistence-mode-for-your-organization-to-teams-only).</span></span>

3. <span data-ttu-id="ae95d-121">[Disabilitare lo spazio degli indirizzi SIP condiviso (noto anche come "dominio diviso") nell'Microsoft 365 organizzazione](#disable-shared-sip-address-space-in-microsoft-365-organization).</span><span class="sxs-lookup"><span data-stu-id="ae95d-121">[Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization](#disable-shared-sip-address-space-in-microsoft-365-organization).</span></span>

4. [<span data-ttu-id="ae95d-122">Disabilitare la comunicazione tra locale e Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae95d-122">Disable communication between on-premises and Microsoft 365</span></span>](#disable-communication-between-on-premises-and-microsoft-365)

<span data-ttu-id="ae95d-123">Questi passaggi separano logicamente la distribuzione locale di Skype for Business Server da Microsoft 365 e assicurati che l'organizzazione sia completamente Teams solo.</span><span class="sxs-lookup"><span data-stu-id="ae95d-123">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and ensure your organization is fully Teams Only.</span></span> <span data-ttu-id="ae95d-124">Dopo aver completato questi passaggi, è possibile rimuovere le autorizzazioni della distribuzione di Skype for Business locale utilizzando uno dei due metodi a cui si fa riferimento in Decidere come gestire gli attributi dopo la rimozione delle [autorizzazioni.](cloud-consolidation-managing-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="ae95d-124">After you've completed these steps, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

> [!Important] 
> <span data-ttu-id="ae95d-125">Al termine di questa separazione logica, gli attributi msRTCSIP da Active Directory locale hanno ancora valori e continueranno a essere sincronizzati tramite Azure AD Connessione in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ae95d-125">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="ae95d-126">La modalità di rimozione delle autorizzazioni per l'ambiente locale dipende dal fatto che si intenda o meno lasciare tali attributi sul posto o prima di cancellarli da Active Directory locale.</span><span class="sxs-lookup"><span data-stu-id="ae95d-126">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="ae95d-127">Tenere presente che la cancellazione degli attributi msRTCSIP locali dopo la migrazione dall'ambiente locale potrebbe comportare la perdita del servizio per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ae95d-127">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="ae95d-128">I dettagli e i compromessi dei due approcci di rimozione delle autorizzazioni sono descritti in Decidere come gestire gli attributi [dopo la rimozione.](cloud-consolidation-managing-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="ae95d-128">Details and tradeoffs of the two decommissioning approaches are described in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

## <a name="update-dns-to-point-to-microsoft-365"></a><span data-ttu-id="ae95d-129">Aggiornare DNS in modo che punti a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae95d-129">Update DNS to point to Microsoft 365</span></span>

<span data-ttu-id="ae95d-130">Il DNS esterno dell'organizzazione per l'organizzazione locale deve essere aggiornato in modo che i record di Skype for Business puntino a Microsoft 365 anziché alla distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="ae95d-130">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> 

<span data-ttu-id="ae95d-131">Inoltre, i record CNAME per meet o dialin (se presente) possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="ae95d-131">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="ae95d-132">Infine, tutti i record DNS Skype for Business nella rete interna devono essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="ae95d-132">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

<span data-ttu-id="ae95d-133">Per informazioni dettagliate sull'aggiornamento dei record DNS, vedere [Update DNS entries to enable your organization to be all Teams Only](decommission-manage-dns-entries.md).</span><span class="sxs-lookup"><span data-stu-id="ae95d-133">For details about updating DNS records, see [Update DNS entries to enable your organization to be all Teams Only](decommission-manage-dns-entries.md).</span></span>

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a><span data-ttu-id="ae95d-134">Modificare la modalità di coesistenza per l'organizzazione Teams solo</span><span class="sxs-lookup"><span data-stu-id="ae95d-134">Change the coexistence mode for your organization to Teams Only</span></span>

<span data-ttu-id="ae95d-135">Questo passaggio garantisce che qualsiasi nuovo utente dell'organizzazione sia sempre creato come Teams solo utente.</span><span class="sxs-lookup"><span data-stu-id="ae95d-135">This step ensures that any new user in your organization is always created as a Teams Only user.</span></span> 

<span data-ttu-id="ae95d-136">Se si tenta di modificare la modalità tenant in Teams Solo verrà verificata automaticamente l'esistenza di eventuali record DNS locali che potrebbero essere stati persi nel passaggio 1 e identificheranno tali record nell'output.</span><span class="sxs-lookup"><span data-stu-id="ae95d-136">Attempting to change the tenant mode to Teams Only will automatically check for existence of any on-premises DNS records that may have been missed in step 1 and identify these records in the output.</span></span> <span data-ttu-id="ae95d-137">La modifica della modalità tenant in Teams avrà esito positivo solo dopo l'aggiornamento di tutti i record DNS per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae95d-137">Changing the tenant mode to Teams Only will not succeed until all DNS records for your organization are updated.</span></span> 

<span data-ttu-id="ae95d-138">Per modificare la modalità tenant in Teams eseguire solo il comando seguente da una Teams di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae95d-138">To change the tenant mode to Teams Only run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

<span data-ttu-id="ae95d-139">In alternativa, è possibile utilizzare l'interfaccia di amministrazione di Teams per modificare la modalità di coesistenza del tenant in TeamsOnly, in "Impostazioni a livello di organizzazione" -> "Teams aggiornamento".</span><span class="sxs-lookup"><span data-stu-id="ae95d-139">Alternatively, you can use the Teams Admin Center to change the tenant coexistence mode to TeamsOnly, under "Org-wide settings" -> "Teams Upgrade."</span></span>    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a><span data-ttu-id="ae95d-140">Disabilitare lo spazio di indirizzi SIP condiviso nell Microsoft 365 interno</span><span class="sxs-lookup"><span data-stu-id="ae95d-140">Disable shared sip address space in Microsoft 365 organization</span></span>
    
<span data-ttu-id="ae95d-141">Per disabilitare lo spazio di indirizzi SIP condiviso, eseguire il comando seguente da una finestra Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae95d-141">To disable shared sip address space, run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a><span data-ttu-id="ae95d-142">Disabilitare la comunicazione tra locale e Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae95d-142">Disable communication between on-premises and Microsoft 365</span></span>

<span data-ttu-id="ae95d-143">Per disabilitare la comunicazione tra l'ambiente locale e Microsoft 365, eseguire il comando seguente da una finestra di PowerShell locale:</span><span class="sxs-lookup"><span data-stu-id="ae95d-143">To disable communication between the on-premises environment and Microsoft 365, run the following command from an on-premises PowerShell window:</span></span>

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a><span data-ttu-id="ae95d-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae95d-144">See also</span></span>

- [<span data-ttu-id="ae95d-145">Consolidamento cloud per Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ae95d-145">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="ae95d-146">Rimuovi le autorizzazioni dell'ambiente locale Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ae95d-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

