---
title: Modificare un criterio di archiviazione esistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Riepilogo: informazioni su come modificare i criteri di archiviazione degli utenti per Skype for Business Server.'
ms.openlocfilehash: 47c9d5938c22b93db48c96265831cbf24ecc24d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817706"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="c2766-103">Modificare un criterio di archiviazione esistente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c2766-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="c2766-104">**Riepilogo:** Informazioni su come modificare i criteri di archiviazione degli utenti per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c2766-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="c2766-105">Quando si distribuisce per la prima volta Skype for Business Server, si impostano i criteri di archiviazione iniziali che determinano la modalità di implementazione dell'archiviazione per gli utenti nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c2766-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="c2766-106">In questo argomento viene descritto come gestire e modificare i criteri.</span><span class="sxs-lookup"><span data-stu-id="c2766-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="c2766-107">Modificare i criteri di archiviazione utilizzando il Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="c2766-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="c2766-108">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="c2766-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="c2766-109">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c2766-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c2766-110">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="c2766-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="c2766-111">Nell'elenco dei criteri eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2766-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="c2766-112">Per modificare i criteri per l'intera distribuzione, fare clic su **Globale** nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="c2766-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="c2766-113">Per modificare i criteri per un singolo sito, fare clic sul nome del sito nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="c2766-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="c2766-114">Per modificare i criteri per un singolo utente o gruppo di utenti, fare clic sul nome dell'utente o del gruppo di utenti nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="c2766-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c2766-115">Nella pagina **Modifica Criteri di archiviazione** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2766-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="c2766-116">Per abilitare o disabilitare l'archiviazione interna per i criteri, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.</span><span class="sxs-lookup"><span data-stu-id="c2766-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="c2766-117">Per abilitare o disabilitare l'archiviazione esterna per i criteri, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="c2766-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="c2766-118">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="c2766-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c2766-119">Le impostazioni dei criteri utente sono valide solo per gli utenti e i gruppi di utenti specifici a cui vengono applicati i criteri.</span><span class="sxs-lookup"><span data-stu-id="c2766-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="c2766-120">Per informazioni dettagliate, vedere [Applicare un criterio di archiviazione agli utenti in Skype for Business Server.](apply-a-policy-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="c2766-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="c2766-121">Modificare i criteri di archiviazione utilizzando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c2766-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="c2766-122">È inoltre possibile modificare i criteri di archiviazione utilizzando Windows PowerShell **cmdlet Set-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="c2766-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="c2766-123">Abilitare i criteri di archiviazione</span><span class="sxs-lookup"><span data-stu-id="c2766-123">Enable archiving policies</span></span>

<span data-ttu-id="c2766-124">Per abilitare l'archiviazione delle sessioni di comunicazione interne, impostare il valore del parametro ArchiveInternal su True ($True):</span><span class="sxs-lookup"><span data-stu-id="c2766-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="c2766-125">Per abilitare l'archiviazione delle sessioni di comunicazione esterne, impostare il valore del parametro ArchiveExternal su True ($True):</span><span class="sxs-lookup"><span data-stu-id="c2766-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="c2766-126">Per abilitare l'archiviazione delle sessioni di comunicazione sia interne che esterne, impostare il valore dei parametri ArchiveInternal e ArchiveExternal su True:</span><span class="sxs-lookup"><span data-stu-id="c2766-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="c2766-127">Disabilitare i criteri di archiviazione</span><span class="sxs-lookup"><span data-stu-id="c2766-127">Disable archiving policies</span></span>

<span data-ttu-id="c2766-128">Per disabilitare completamente l'archiviazione, impostare il valore dei parametri ArchiveInternal e ArchiveExternal su False ($False):</span><span class="sxs-lookup"><span data-stu-id="c2766-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
