---
title: Provisioning della topologia per l'esecuzione del caricamento in scenari di stress e prestazioni
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: La topologia di Skype for Business Server 2015 cambia o provisioning per consentire agli utenti di eseguire correttamente lo strumento stress e prestazioni.
ms.openlocfilehash: e58bfce5e618c6e62f272c0acb0b415cbb471d40
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992493"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="4f0ee-103">Provisioning della topologia per l'esecuzione del caricamento in scenari di stress e prestazioni</span><span class="sxs-lookup"><span data-stu-id="4f0ee-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="4f0ee-104">La topologia di Skype for Business Server 2015 cambia o provisioning per consentire agli utenti di eseguire correttamente lo strumento stress e prestazioni.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="4f0ee-105">A seconda delle impostazioni e della configurazione esistenti per la distribuzione di Skype for Business Server 2015, potrebbe essere necessario apportare alcune modifiche all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="4f0ee-106">Di seguito è riportato un elenco di queste modifiche:</span><span class="sxs-lookup"><span data-stu-id="4f0ee-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="4f0ee-107">Impostare i criteri di esecuzione di Windows PowerShell su senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="4f0ee-108">Se non si è sicuri di cosa sia impostato al momento, è possibile aprire Skype for Business Server Management Shell ed eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="4f0ee-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="4f0ee-109">Se il valore Unrestricted non viene restituito, sarà necessario eseguire il successivo:</span><span class="sxs-lookup"><span data-stu-id="4f0ee-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="4f0ee-110">Per configurare efficacemente Skype for Business Server, è necessario:</span><span class="sxs-lookup"><span data-stu-id="4f0ee-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="4f0ee-111">Acquisire familiarità con la topologia di Skype for Business Server 2015, ad esempio nomi di computer, istanze del servizio, nomi dei siti e criteri.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="4f0ee-112">Assegna alcuni degli utenti creati ai gruppi, ad esempio i gruppi di risposta alla ricerca di Response Group, come gli URI SIP.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="4f0ee-113">Per eseguire uno script da riga di comando, è possibile usare:</span><span class="sxs-lookup"><span data-stu-id="4f0ee-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="4f0ee-114">In genere, dopo aver eseguito uno script da questo pacchetto, le tracce risultanti verranno archiviate in un file nello stesso percorso da cui è stato eseguito lo script.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="4f0ee-115">Esiste anche un formato di denominazione, \<scriptname\>$h $ m $ s. txt.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="4f0ee-116">Quindi, se è stato eseguito il ArchivingPolicy. ps1 alle 12:15 PM, viene visualizzato un file di log denominato ArchivingPolicy121500. txt.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="4f0ee-117">Anche se sono stati forniti questi esempi per la configurazione del server, è necessario modificare la configurazione e ripristinare o eseguire il rollback dopo aver completato l'esecuzione del test di carico.</span><span class="sxs-lookup"><span data-stu-id="4f0ee-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

