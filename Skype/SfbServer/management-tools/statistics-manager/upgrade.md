---
title: Aggiornare il gestore delle statistiche per Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: "Riepilogo: leggere questo argomento per informazioni sull'aggiornamento di Statistics Manager per Skype for Business Server."
ms.openlocfilehash: 6f2f0b885faad7bd650b3ff90650b64af98e9eee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821766"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="31e05-103">Aggiornare il gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="31e05-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="31e05-104">**Riepilogo:** Leggere questo argomento per informazioni sull'aggiornamento di Statistics Manager per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="31e05-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="31e05-105">In questo argomento viene descritto come aggiornare un'installazione esistente di Statistics Manager per Skype for Business Server, uno strumento potente che consente di visualizzare i dati sulle prestazioni e sull'integrità di Skype for Business Server in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="31e05-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="31e05-106">È possibile eseguire il polling dei dati sulle prestazioni in centinaia di server ogni pochi secondi e visualizzare immediatamente i risultati nel sito Web di Gestione statistiche.</span><span class="sxs-lookup"><span data-stu-id="31e05-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="31e05-107">Per ulteriori informazioni su Gestione statistiche e sulle nuove funzionalità della versione 2.0, vedere [Plan for Statistics Manager for Skype for Business Server](plan.md) e Deploy Statistics Manager for Skype for Business [Server.](deploy.md)</span><span class="sxs-lookup"><span data-stu-id="31e05-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="31e05-108">Esistono due metodi per l'aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="31e05-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="31e05-109">**Aggiornamento automatico.**</span><span class="sxs-lookup"><span data-stu-id="31e05-109">**Automated upgrade.**</span></span> <span data-ttu-id="31e05-110">Questo metodo usa uno script automatico.</span><span class="sxs-lookup"><span data-stu-id="31e05-110">This method uses an automated script.</span></span> <span data-ttu-id="31e05-111">È il metodo più semplice e deve essere applicabile a tutti gli scenari di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="31e05-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="31e05-112">**Aggiornamento manuale.**</span><span class="sxs-lookup"><span data-stu-id="31e05-112">**Manual upgrade.**</span></span> <span data-ttu-id="31e05-113">Questo metodo viene fornito come piano di backup nel caso in cui l'aggiornamento automatico non riesca.</span><span class="sxs-lookup"><span data-stu-id="31e05-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="31e05-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="31e05-114">Prerequisites</span></span>

<span data-ttu-id="31e05-115">Prima di eseguire l'aggiornamento, assicurarsi di disporre delle informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="31e05-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="31e05-116">Identificazione personale certificato listener attivo</span><span class="sxs-lookup"><span data-stu-id="31e05-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="31e05-117">Password del servizio listener (immessa durante l'installazione del listener e di ogni agente)</span><span class="sxs-lookup"><span data-stu-id="31e05-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="31e05-118">Configurazione del certificato SSL per il sito Web</span><span class="sxs-lookup"><span data-stu-id="31e05-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="31e05-119">Aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="31e05-119">Automated upgrade</span></span>

<span data-ttu-id="31e05-120">Lo script raccoglierà le informazioni sul certificato corrente e la password del listener, disinstalla la versione precedente del prodotto e quindi installerà la nuova versione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="31e05-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="31e05-121">L'istanza di Redis installata nel server non verrà toccata, quindi tutti i dati archiviati nella cache verranno conservati tramite il processo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="31e05-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="31e05-122">Inserire i file MSI per la nuova versione dell'agente, del listener e del sito Web insieme allo script Update-StatsMan.ps1 in una singola cartella nel computer listener.</span><span class="sxs-lookup"><span data-stu-id="31e05-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="31e05-123">Aprire una finestra di PowerShell amministrativa.</span><span class="sxs-lookup"><span data-stu-id="31e05-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="31e05-124">Aggiornare il componente listener:</span><span class="sxs-lookup"><span data-stu-id="31e05-124">Upgrade the Listener component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="31e05-125">La password del servizio Gestione statistiche verrà visualizzata come testo non crittografato nella riga di comando quando viene passata al programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="31e05-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="31e05-126">Assicurati di proteggere il monitor in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="31e05-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="31e05-127">Quando si esegue lo script, dovrebbe essere richiesto di disinstallare la versione precedente del prodotto.</span><span class="sxs-lookup"><span data-stu-id="31e05-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="31e05-128">Risposta Sì.</span><span class="sxs-lookup"><span data-stu-id="31e05-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="31e05-129">Se il servizio listener è in esecuzione, verrà richiesto di chiudere l'applicazione prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="31e05-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="31e05-130">Consentire la chiusura dell'applicazione (il servizio listener di Gestione statistiche verrà arrestato).</span><span class="sxs-lookup"><span data-stu-id="31e05-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="31e05-131">Continuare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="31e05-131">Continue the install process.</span></span> <span data-ttu-id="31e05-132">Si noti che la password del servizio e l'identificazione personale del certificato sono precompilato.</span><span class="sxs-lookup"><span data-stu-id="31e05-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="31e05-133">In caso contrario, aggiungere i valori salvati prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="31e05-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="31e05-134">Aprire una finestra di PowerShell amministrativa.</span><span class="sxs-lookup"><span data-stu-id="31e05-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="31e05-135">Aggiornare il componente Sito Web:</span><span class="sxs-lookup"><span data-stu-id="31e05-135">Upgrade the Website component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="31e05-136">Quando si esegue lo script, dovrebbe essere richiesto di disinstallare la versione precedente del prodotto.</span><span class="sxs-lookup"><span data-stu-id="31e05-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="31e05-137">Risposta Sì.</span><span class="sxs-lookup"><span data-stu-id="31e05-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="31e05-138">Se il servizio agente è in esecuzione, verrà richiesto di chiudere l'applicazione prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="31e05-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="31e05-139">Consentire la chiusura dell'applicazione (il servizio Agente StatsMan verrà arrestato).</span><span class="sxs-lookup"><span data-stu-id="31e05-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="31e05-140">Continuare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="31e05-140">Continue the install process.</span></span> <span data-ttu-id="31e05-141">Si noti che la password del servizio e l'identificazione personale del certificato sono precompilato.</span><span class="sxs-lookup"><span data-stu-id="31e05-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="31e05-142">In caso contrario, aggiungere i valori salvati prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="31e05-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="31e05-143">Aprire una finestra di PowerShell amministrativa.</span><span class="sxs-lookup"><span data-stu-id="31e05-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="31e05-144">Aggiornare il componente Agente:</span><span class="sxs-lookup"><span data-stu-id="31e05-144">Upgrade the Agent component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="31e05-145">Quando si esegue lo script, dovrebbe essere richiesto di disinstallare la versione precedente del prodotto.</span><span class="sxs-lookup"><span data-stu-id="31e05-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="31e05-146">Risposta Sì.</span><span class="sxs-lookup"><span data-stu-id="31e05-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="31e05-147">Continuare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="31e05-147">Continue the install process.</span></span> <span data-ttu-id="31e05-148">Si noti che la porta del sito Web è precompilato.</span><span class="sxs-lookup"><span data-stu-id="31e05-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="31e05-149">In caso contrario, aggiungere il valore salvato prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="31e05-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="31e05-150">Verificare che il sito Web funzioni come previsto utilizzando il browser.</span><span class="sxs-lookup"><span data-stu-id="31e05-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="31e05-151">L'aggiornamento dell'agente può essere utilizzato con l'opzione -NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="31e05-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="31e05-152">In questo modo il processo di disinstallazione/installazione verrà eseguito in modo invisibile all'utente, consentendo a strumenti come PSExec di eseguire l'aggiornamento in remoto su un numero elevato di server.</span><span class="sxs-lookup"><span data-stu-id="31e05-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="31e05-153">Aggiornamento manuale</span><span class="sxs-lookup"><span data-stu-id="31e05-153">Manual upgrade</span></span>

<span data-ttu-id="31e05-154">Se per qualche motivo l'aggiornamento automatico non riesce, è sempre possibile eseguire un aggiornamento manuale nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="31e05-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="31e05-155">Nel computer listener disinstallare listener, sito Web e agente (se installato nel server) tramite il Pannello di controllo Programmi e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="31e05-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="31e05-156">Mantenere Installato Redis in modo che i dati nella cache siano mantenuti tramite il processo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="31e05-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="31e05-157">Installare le nuove versioni dei componenti, inclusi i valori salvati in precedenza quando vengono richiesti.</span><span class="sxs-lookup"><span data-stu-id="31e05-157">Install the new versions of the components, including the values you saved above when prompted for them.</span></span> <span data-ttu-id="31e05-158">Per ulteriori informazioni sull'installazione dei componenti, vedere [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="31e05-158">For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="31e05-159">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="31e05-159">For more information</span></span>
<span data-ttu-id="31e05-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="31e05-160"><a name="BKMK_Fixed"> </a></span></span>

<span data-ttu-id="31e05-161">Per ulteriori informazioni, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="31e05-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="31e05-162">Pianificare il gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="31e05-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="31e05-163">Distribuire il gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="31e05-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="31e05-164">Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="31e05-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
