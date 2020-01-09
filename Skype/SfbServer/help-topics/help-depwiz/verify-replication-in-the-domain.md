---
title: Verifica della replica nel dominio
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 'Per verificare la replica della preparazione del dominio eseguita nel passaggio 1: preparare lo schema, è necessario eseguire un cmdlet da Skype for Business Server Management Shell Lync Server Management Shell. Per eseguire il cmdlet di Windows PowerShell, accedere a un computer che fa parte del dominio che si è preparato e come membro del gruppo Domain Admins. Effettuare le seguenti operazioni:'
ms.openlocfilehash: f20806a11850276032bae19b4311734669be5a53
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989051"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="4f11c-105">Verifica della replica nel dominio</span><span class="sxs-lookup"><span data-stu-id="4f11c-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="4f11c-106">Per verificare la replica della preparazione del dominio eseguita nel **passaggio 1: preparare lo schema**, è necessario eseguire un cmdlet da Skype for Business Server Management Shell Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4f11c-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="4f11c-107">Per eseguire il cmdlet di Windows PowerShell, accedere a un computer che fa parte del dominio che si è preparato e come membro del gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="4f11c-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="4f11c-108">Effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="4f11c-108">Do the following:</span></span>
  
1. <span data-ttu-id="4f11c-109">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4f11c-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4f11c-110">In Windows PowerShell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="4f11c-110">In Windows PowerShell, type the following:</span></span>
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="4f11c-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4f11c-111">For example:</span></span>
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="4f11c-112">Il parametro GlobalSettingsDomainController consente di indicare dove vengono archiviate le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="4f11c-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="4f11c-113">Se le impostazioni sono archiviate nel contenitore di sistema (tipico delle distribuzioni di aggiornamento che non hanno eseguito la migrazione dell'impostazione globale al contenitore di configurazione), si definisce un controller di dominio nella radice della foresta dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4f11c-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="4f11c-114">Se invece le impostazioni globali sono incluse nel contenitore Configuration, come avviene in genere con le distribuzioni nuove o di aggiornamento per cui è stata eseguita la migrazione delle impostazioni nel contenitore Configuration, definire un controller di dominio nella foresta.</span><span class="sxs-lookup"><span data-stu-id="4f11c-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="4f11c-115">Se non specifichi questo parametro, il cmdlet presuppone che le impostazioni siano archiviate nel contenitore di configurazione e faccia riferimento a qualsiasi controller di dominio in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4f11c-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="4f11c-116">Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="4f11c-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="4f11c-117">Questo cmdlet restituirà il valore **LC_DOMAIN_SETTINGS_STATE_READY** se la preparazione del dominio ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4f11c-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

