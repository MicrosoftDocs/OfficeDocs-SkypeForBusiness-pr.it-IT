---
title: Convert-CcIsoToVhdx
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Il cmdlet Convert-CcIsoToVhdx crea un file di disco rigido virtuale di base (VHDX) usando un file ISO di Windows Server 2012 R2 fornito dal cliente. Il file VHDX verrà usato durante la distribuzione di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 780002c54a77746c51f418cae077ffcc9b1fb608
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001346"
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="a6022-104">Convert-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="a6022-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="a6022-105">Il cmdlet Convert-CcIsoToVhdx crea un file di disco rigido virtuale di base (VHDX) usando un file ISO di Windows Server 2012 R2 fornito dal cliente.</span><span class="sxs-lookup"><span data-stu-id="a6022-105">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file.</span></span> <span data-ttu-id="a6022-106">Il file VHDX verrà usato durante la distribuzione di Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="a6022-106">The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="a6022-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="a6022-107">Parameters</span></span>

|<span data-ttu-id="a6022-108">**Parametro**</span><span class="sxs-lookup"><span data-stu-id="a6022-108">**Parameter**</span></span>|<span data-ttu-id="a6022-109">**Richiesto**</span><span class="sxs-lookup"><span data-stu-id="a6022-109">**Required**</span></span>|<span data-ttu-id="a6022-110">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a6022-110">**Type**</span></span>|<span data-ttu-id="a6022-111">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a6022-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a6022-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="a6022-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="a6022-113">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="a6022-113">Required</span></span> <br/> |<span data-ttu-id="a6022-114">System.String</span><span class="sxs-lookup"><span data-stu-id="a6022-114">System.String</span></span>  <br/> | <span data-ttu-id="a6022-115">Percorso del file ISO di Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="a6022-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="a6022-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="a6022-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="a6022-117">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="a6022-117">Optional</span></span>  <br/> |<span data-ttu-id="a6022-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a6022-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="a6022-119">Se il processo di conversione non riesce durante Windows Update, è possibile provare a configurare una rete/proxy e aggiornare le finestre manualmente.</span><span class="sxs-lookup"><span data-stu-id="a6022-119">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually.</span></span> <span data-ttu-id="a6022-120">Dopo aver completato il lavoro manuale, puoi eseguire questo cmdlet con il parametro-GeneralizeOnly e completare i processi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="a6022-120">After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="a6022-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="a6022-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="a6022-122">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="a6022-122">Optional</span></span>  <br/> |<span data-ttu-id="a6022-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a6022-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="a6022-124">Per aggiornare Windows, potrebbe essere necessario qualche configurazione manuale della rete/proxy sulla VM di base.</span><span class="sxs-lookup"><span data-stu-id="a6022-124">To update Windows, some manual network/proxy configuration on the base VM might be necessary.</span></span> <span data-ttu-id="a6022-125">Il processo di conversione verrà sospeso prima di Windows Update se questo parametro è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a6022-125">The conversion process will pause before Windows update if this parameter is provided.</span></span> <span data-ttu-id="a6022-126">Dopo aver completato la configurazione manuale, è possibile riprendere il processo.</span><span class="sxs-lookup"><span data-stu-id="a6022-126">After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="a6022-127">Esempi</span><span class="sxs-lookup"><span data-stu-id="a6022-127">Examples</span></span>
<span data-ttu-id="a6022-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a6022-128"></span></span>

### <a name="example-1"></a><span data-ttu-id="a6022-129">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="a6022-129">Example 1</span></span>

<span data-ttu-id="a6022-130">L'esempio seguente prepara il file VHDX di base usando un file ISO di Windows Server 2012 R2 che si trova in "C:\ Windows_Server_2012_R2-EN-US-x64. ISO":</span><span class="sxs-lookup"><span data-stu-id="a6022-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="a6022-131">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="a6022-131">Example 2</span></span>

<span data-ttu-id="a6022-132">Se il cmdlet Convert-CcIsoToVhdx non riesce durante Windows Update, è probabilmente a causa di una configurazione di rete/proxy non corretta.</span><span class="sxs-lookup"><span data-stu-id="a6022-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="a6022-133">È possibile seguire le istruzioni nel messaggio di errore e accedere alla macchina virtuale di base per correggere il problema e aggiornare le finestre manualmente.</span><span class="sxs-lookup"><span data-stu-id="a6022-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="a6022-134">Dopo aver completato il lavoro manuale, eseguire di nuovo il cmdlet con il parametro-GeneralizeOnly per completare i processi rimanenti:</span><span class="sxs-lookup"><span data-stu-id="a6022-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="a6022-135">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="a6022-135">Example 3</span></span>

<span data-ttu-id="a6022-136">Se è necessaria la configurazione manuale per aggiornare Windows, è possibile usare il parametro-PauseBeforeUpdate.</span><span class="sxs-lookup"><span data-stu-id="a6022-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="a6022-137">Con questo parametro, il connettore Cloud verrà sospeso prima del processo di Windows Update.</span><span class="sxs-lookup"><span data-stu-id="a6022-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="a6022-138">È quindi possibile completare la configurazione manuale e riprendere il processo di conversione nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="a6022-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="a6022-139">Descrizione dettagliata</span><span class="sxs-lookup"><span data-stu-id="a6022-139">Detailed Description</span></span>
<span data-ttu-id="a6022-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a6022-140"></span></span>

<span data-ttu-id="a6022-141">Il cmdlet Convert-CcIsoToVhdx crea prima una VM di base, installa alcuni componenti di base da cui dipende il Cloud Connector e quindi installa gli aggiornamenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="a6022-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="a6022-142">Infine, generalizza la macchina virtuale (Sysprep) per ottenere un file di VHDX di base che verrà usato dalle macchine virtuali di un appliance di connessione cloud.</span><span class="sxs-lookup"><span data-stu-id="a6022-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="a6022-143">Tipi di input</span><span class="sxs-lookup"><span data-stu-id="a6022-143">Input Types</span></span>
<span data-ttu-id="a6022-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a6022-144"></span></span>

<span data-ttu-id="a6022-145">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a6022-145">None.</span></span> <span data-ttu-id="a6022-146">Il cmdlet Convert-CcIsoToVhdx non accetta l'input da pipeline.</span><span class="sxs-lookup"><span data-stu-id="a6022-146">The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="a6022-147">Tipi restituiti</span><span class="sxs-lookup"><span data-stu-id="a6022-147">Return Types</span></span>
<span data-ttu-id="a6022-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a6022-148"></span></span>

<span data-ttu-id="a6022-149">Nessuno</span><span class="sxs-lookup"><span data-stu-id="a6022-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a6022-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6022-150">See also</span></span>
<span data-ttu-id="a6022-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a6022-151"></span></span>

<span data-ttu-id="a6022-152">Nessuno</span><span class="sxs-lookup"><span data-stu-id="a6022-152">None</span></span>
  

