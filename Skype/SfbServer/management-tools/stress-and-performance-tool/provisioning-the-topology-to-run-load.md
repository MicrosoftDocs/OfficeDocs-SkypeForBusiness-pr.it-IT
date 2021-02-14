---
title: Provisioning della topologia per l'esecuzione del carico in scenari di stress e prestazioni
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Modifiche o provisioning della topologia di Skype for Business Server 2015 per consentire agli utenti di eseguire correttamente lo strumento Stress and Performance.
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814936"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="519ae-103">Provisioning della topologia per l'esecuzione del carico in scenari di stress e prestazioni</span><span class="sxs-lookup"><span data-stu-id="519ae-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="519ae-104">Modifiche o provisioning della topologia di Skype for Business Server 2015 per consentire agli utenti di eseguire correttamente lo strumento Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="519ae-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="519ae-105">A seconda delle impostazioni e della configurazione esistenti per la distribuzione di Skype for Business Server 2015, potrebbe essere necessario apportare alcune modifiche all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="519ae-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="519ae-106">Di seguito è riportato un elenco di tali modifiche:</span><span class="sxs-lookup"><span data-stu-id="519ae-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="519ae-107">Impostare il Windows PowerShell di esecuzione su Senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="519ae-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="519ae-108">Se non si è sicuri di cosa è attualmente impostato, è possibile aprire Skype for Business Server Management Shell ed eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="519ae-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="519ae-109">Se non viene restituito il valore Unrestricted, sarà necessario eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="519ae-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="519ae-110">Per configurare in modo efficace Skype for Business Server, è necessario:</span><span class="sxs-lookup"><span data-stu-id="519ae-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="519ae-111">Acquisire familiarità con la topologia di Skype for Business Server 2015 (ad esempio nomi computer, istanze del servizio, nomi di sito e criteri).</span><span class="sxs-lookup"><span data-stu-id="519ae-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="519ae-112">Assegnare alcuni degli utenti creati ai gruppi, ad esempio i gruppi di risposta di Response Group ,ad esempio gli URI SIP.</span><span class="sxs-lookup"><span data-stu-id="519ae-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="519ae-113">Per eseguire uno script dalla riga di comando, è possibile utilizzare:</span><span class="sxs-lookup"><span data-stu-id="519ae-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="519ae-114">In genere, dopo aver eseguito uno script da questo pacchetto, le tracce risultanti verranno archiviate in un file nello stesso percorso da cui è stato eseguito lo script.</span><span class="sxs-lookup"><span data-stu-id="519ae-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="519ae-115">Esiste anche un formato di denominazione, \<scriptname\> $h$m$s.txt.</span><span class="sxs-lookup"><span data-stu-id="519ae-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="519ae-116">Pertanto, se il ArchivingPolicy.ps1 è stato eseguito alle 12:15, si otterrà un file di registro denominato ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="519ae-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="519ae-117">Anche se questi esempi sono stati forniti per la configurazione del server, è necessario modificare la configurazione e ripristinarla o ripristinarla dopo aver completato l'esecuzione del test di carico.</span><span class="sxs-lookup"><span data-stu-id="519ae-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

