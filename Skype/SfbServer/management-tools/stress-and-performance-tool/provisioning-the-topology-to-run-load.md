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
ms.openlocfilehash: c7cdc10b3667ac99376904c81309df739e49844a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195079"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="58dc6-103">Provisioning della topologia per l'esecuzione del caricamento in scenari di stress e prestazioni</span><span class="sxs-lookup"><span data-stu-id="58dc6-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="58dc6-104">La topologia di Skype for Business Server 2015 cambia o provisioning per consentire agli utenti di eseguire correttamente lo strumento stress e prestazioni.</span><span class="sxs-lookup"><span data-stu-id="58dc6-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="58dc6-105">A seconda delle impostazioni e della configurazione esistenti per la distribuzione di Skype for Business Server 2015, potrebbe essere necessario apportare alcune modifiche all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="58dc6-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="58dc6-106">Di seguito è riportato un elenco di queste modifiche:</span><span class="sxs-lookup"><span data-stu-id="58dc6-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="58dc6-107">Impostare i criteri di esecuzione di Windows PowerShell su senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="58dc6-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="58dc6-108">Se non si è sicuri di cosa sia impostato al momento, è possibile aprire Skype for Business Server Management Shell ed eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="58dc6-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="58dc6-109">Se il valore Unrestricted non viene restituito, sarà necessario eseguire il successivo:</span><span class="sxs-lookup"><span data-stu-id="58dc6-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="58dc6-110">Per configurare efficacemente Skype for Business Server, è necessario:</span><span class="sxs-lookup"><span data-stu-id="58dc6-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="58dc6-111">Acquisire familiarità con la topologia di Skype for Business Server 2015, ad esempio nomi di computer, istanze del servizio, nomi dei siti e criteri.</span><span class="sxs-lookup"><span data-stu-id="58dc6-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="58dc6-112">Assegna alcuni degli utenti creati ai gruppi, ad esempio i gruppi di risposta alla ricerca di Response Group, come gli URI SIP.</span><span class="sxs-lookup"><span data-stu-id="58dc6-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="58dc6-113">Per eseguire uno script da riga di comando, è possibile usare:</span><span class="sxs-lookup"><span data-stu-id="58dc6-113">To run a script from command line, you can use:</span></span>
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="58dc6-114">In genere, dopo aver eseguito uno script da questo pacchetto, le tracce risultanti verranno archiviate in un file nello stesso percorso da cui è stato eseguito lo script.</span><span class="sxs-lookup"><span data-stu-id="58dc6-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="58dc6-115">Esiste anche un formato di denominazione, \<scriptname\>$h $ m $ s. txt.</span><span class="sxs-lookup"><span data-stu-id="58dc6-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="58dc6-116">Quindi, se è stato eseguito il ArchivingPolicy. ps1 alle 12:15 PM, viene visualizzato un file di log denominato ArchivingPolicy121500. txt.</span><span class="sxs-lookup"><span data-stu-id="58dc6-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="58dc6-117">Anche se sono stati forniti questi esempi per la configurazione del server, è necessario modificare la configurazione e ripristinare o eseguire il rollback dopo aver completato l'esecuzione del test di carico.</span><span class="sxs-lookup"><span data-stu-id="58dc6-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

