---
title: Spostare le directory conferenze
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Prima di rimuovere un pool, è necessario eseguire la procedura seguente per ogni directory conferenze nel pool legacy.
ms.openlocfilehash: 8a25b955ae769a712750ff08325b3fa29538be8a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752498"
---
# <a name="move-conference-directories"></a><span data-ttu-id="1b235-103">Spostare le directory conferenze</span><span class="sxs-lookup"><span data-stu-id="1b235-103">Move Conference Directories</span></span>

<span data-ttu-id="1b235-104">Prima di rimuovere il pool, è necessario eseguire la procedura seguente per ogni directory conferenze nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="1b235-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="1b235-105">Per spostare una directory conferenze in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="1b235-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="1b235-106">Aprire la shell di gestione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1b235-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="1b235-107">Per ottenere l'identità delle directory conferenze nell'organizzazione, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1b235-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="1b235-108">Il comando precedente restituisce tutte le directory conferenze nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1b235-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="1b235-109">Per questo motivo, è possibile che si desideri limitare i risultati al pool di cui è stata eseguita la rimozione.</span><span class="sxs-lookup"><span data-stu-id="1b235-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="1b235-110">Ad esempio, se si sta rimuovendo il pool con il nome di dominio completo (FQDN) pool01.contoso.net, utilizzare questo comando per limitare i dati restituiti alle directory conferenze del pool:</span><span class="sxs-lookup"><span data-stu-id="1b235-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="1b235-111">Questo comando restituisce solo le directory conferenze in cui la proprietà ServiceID contiene il nome di dominio completo pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="1b235-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="1b235-112">Per spostare le directory conferenze, eseguire il comando riportato di seguito per ogni directory conferenze nel pool:</span><span class="sxs-lookup"><span data-stu-id="1b235-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="1b235-113">Ad esempio, per spostare la directory conferenze 3, utilizzare questo comando, specificando un pool di Skype for Business Server 2019 come TargetPool:</span><span class="sxs-lookup"><span data-stu-id="1b235-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="1b235-114">Se si desidera spostare tutte le directory conferenze in un pool, utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="1b235-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="1b235-115">Scaricare la [disinstallazione di Microsoft legacy e rimuovere i ruoli del server](https://go.microsoft.com/fwlink/p/?linkId=246227) per istruzioni dettagliate sulla rimozione delle autorizzazioni dei pool legacy.</span><span class="sxs-lookup"><span data-stu-id="1b235-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="1b235-116">Quando si spostano le directory conferenze, è possibile che venga visualizzato l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="1b235-116">When moving conference directories, you might encounter the following error:</span></span>
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="1b235-117">Questo errore si verifica in genere quando Skype for Business Server Management Shell richiede un set aggiornato di autorizzazioni di Active Directory per completare un'attività.</span><span class="sxs-lookup"><span data-stu-id="1b235-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="1b235-118">Per risolvere il problema, chiudere l'istanza corrente di Management Shell, quindi aprire una nuova istanza di Shell ed eseguire di nuovo il comando per spostare la directory conferenze.</span><span class="sxs-lookup"><span data-stu-id="1b235-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

