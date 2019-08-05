---
title: Aggiornare le statistiche di gestione per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Riepilogo: leggere questo argomento per informazioni su come aggiornare Statistics Manager per Skype for Business Server.'
ms.openlocfilehash: 70826776e9dfacdef75c7084a9aba6f4eede940a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195086"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="84ba9-103">Aggiornare le statistiche di gestione per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="84ba9-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="84ba9-104">**Riepilogo:** Leggere questo argomento per informazioni su come aggiornare Statistics Manager per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="84ba9-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="84ba9-105">Questo argomento descrive come aggiornare un'installazione esistente di Statistics Manager per Skype for Business Server, un potente strumento che consente di visualizzare in tempo reale i dati relativi alla salute e alle prestazioni di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="84ba9-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="84ba9-106">È possibile eseguire il polling dei dati sulle prestazioni in centinaia di server ogni pochi secondi e visualizzare i risultati immediatamente nel sito Web di gestione statistiche.</span><span class="sxs-lookup"><span data-stu-id="84ba9-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="84ba9-107">Per altre informazioni su Gestione statistiche e sulle nuove funzionalità della versione 2,0, vedere [pianificare la gestione delle statistiche per Skype for Business Server](plan.md) e [distribuire Gestione statistiche per Skype for Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="84ba9-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="84ba9-108">Esistono due metodi per l'aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="84ba9-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="84ba9-109">**Aggiornamento automatico.**</span><span class="sxs-lookup"><span data-stu-id="84ba9-109">**Automated upgrade.**</span></span> <span data-ttu-id="84ba9-110">Questo metodo usa uno script automatizzato.</span><span class="sxs-lookup"><span data-stu-id="84ba9-110">This method uses an automated script.</span></span> <span data-ttu-id="84ba9-111">È il metodo più semplice e dovrebbe essere applicabile a tutti gli scenari di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="84ba9-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="84ba9-112">**Aggiornamento manuale.**</span><span class="sxs-lookup"><span data-stu-id="84ba9-112">**Manual upgrade.**</span></span> <span data-ttu-id="84ba9-113">Questo metodo viene fornito come piano di backup nel caso insolito in cui l'aggiornamento automatico non riesce.</span><span class="sxs-lookup"><span data-stu-id="84ba9-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="84ba9-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="84ba9-114">Prerequisites</span></span>

<span data-ttu-id="84ba9-115">Prima di eseguire l'aggiornamento, assicurarsi di avere le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="84ba9-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="84ba9-116">Identificazione personale del certificato del listener attivo</span><span class="sxs-lookup"><span data-stu-id="84ba9-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="84ba9-117">Password del servizio listener (immessa durante l'installazione del listener e di ogni agente)</span><span class="sxs-lookup"><span data-stu-id="84ba9-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="84ba9-118">Configurazione del certificato SSL per il sito Web</span><span class="sxs-lookup"><span data-stu-id="84ba9-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="84ba9-119">Aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="84ba9-119">Automated upgrade</span></span>

<span data-ttu-id="84ba9-120">Lo script raccoglierà le informazioni sul certificato corrente e la password del listener, disinstallerà la versione precedente del prodotto e quindi installerà la nuova versione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="84ba9-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="84ba9-121">L'istanza Redis installata nel server non verrà toccata, quindi tutti i dati archiviati nella cache verranno mantenuti tramite il processo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="84ba9-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="84ba9-122">Posizionare i file MSI per la nuova versione dell'agente, del listener e del sito Web insieme allo script Update-StatsMan. ps1 in una singola cartella nel computer del listener.</span><span class="sxs-lookup"><span data-stu-id="84ba9-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="84ba9-123">Aprire una finestra di PowerShell amministrativa.</span><span class="sxs-lookup"><span data-stu-id="84ba9-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="84ba9-124">Aggiornare il componente listener:</span><span class="sxs-lookup"><span data-stu-id="84ba9-124">Upgrade the Listener component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="84ba9-125">La password del servizio di gestione statistiche verrà visualizzata in testo non crittografato nella riga di comando mentre viene passata al programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="84ba9-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="84ba9-126">Assicurarsi di proteggere il monitor in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="84ba9-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="84ba9-127">Per eseguire lo script, è necessario che venga richiesto di disinstallare la versione precedente del prodotto.</span><span class="sxs-lookup"><span data-stu-id="84ba9-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="84ba9-128">Rispondere Sì.</span><span class="sxs-lookup"><span data-stu-id="84ba9-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="84ba9-129">Se il servizio listener è in funzione, verrà richiesto di chiudere l'applicazione prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="84ba9-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="84ba9-130">Consentire all'applicazione di chiudere (il servizio listener di gestione statistiche verrà interrotto).</span><span class="sxs-lookup"><span data-stu-id="84ba9-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="84ba9-131">Continuare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="84ba9-131">Continue the install process.</span></span> <span data-ttu-id="84ba9-132">Si noti che la password del servizio e l'identificazione personale del certificato vengono precompilate.</span><span class="sxs-lookup"><span data-stu-id="84ba9-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="84ba9-133">In caso contrario, aggiungere i valori salvati prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="84ba9-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="84ba9-134">Aprire una finestra di PowerShell amministrativa.</span><span class="sxs-lookup"><span data-stu-id="84ba9-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="84ba9-135">Aggiornare il componente sito Web:</span><span class="sxs-lookup"><span data-stu-id="84ba9-135">Upgrade the Website component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="84ba9-136">Per eseguire lo script, è necessario che venga richiesto di disinstallare la versione precedente del prodotto.</span><span class="sxs-lookup"><span data-stu-id="84ba9-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="84ba9-137">Rispondere Sì.</span><span class="sxs-lookup"><span data-stu-id="84ba9-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="84ba9-138">Se il servizio agente è in funzione, verrà richiesto di chiudere l'applicazione prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="84ba9-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="84ba9-139">Consenti chiusura dell'applicazione (il servizio agente di statistiche verrà interrotto).</span><span class="sxs-lookup"><span data-stu-id="84ba9-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="84ba9-140">Continuare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="84ba9-140">Continue the install process.</span></span> <span data-ttu-id="84ba9-141">Si noti che la password del servizio e l'identificazione personale del certificato vengono precompilate.</span><span class="sxs-lookup"><span data-stu-id="84ba9-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="84ba9-142">In caso contrario, aggiungere i valori salvati prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="84ba9-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="84ba9-143">Aprire una finestra di PowerShell amministrativa.</span><span class="sxs-lookup"><span data-stu-id="84ba9-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="84ba9-144">Aggiornare il componente Agent:</span><span class="sxs-lookup"><span data-stu-id="84ba9-144">Upgrade the Agent component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="84ba9-145">Per eseguire lo script, è necessario che venga richiesto di disinstallare la versione precedente del prodotto.</span><span class="sxs-lookup"><span data-stu-id="84ba9-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="84ba9-146">Rispondere Sì.</span><span class="sxs-lookup"><span data-stu-id="84ba9-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="84ba9-147">Continuare il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="84ba9-147">Continue the install process.</span></span> <span data-ttu-id="84ba9-148">Si noti che la porta del sito Web viene prepopolata.</span><span class="sxs-lookup"><span data-stu-id="84ba9-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="84ba9-149">In caso contrario, Aggiungi il valore salvato prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="84ba9-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="84ba9-150">Verificare che il sito Web funzioni come previsto tramite il browser.</span><span class="sxs-lookup"><span data-stu-id="84ba9-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="84ba9-151">L'aggiornamento dell'agente può essere usato con l'opzione-noprompt.</span><span class="sxs-lookup"><span data-stu-id="84ba9-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="84ba9-152">Ciò consentirà l'esecuzione del processo di disinstallazione/installazione in modo invisibile all'utente, consentendo agli strumenti come PSExec di eseguire l'aggiornamento in remoto su un numero elevato di server.</span><span class="sxs-lookup"><span data-stu-id="84ba9-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="84ba9-153">Aggiornamento manuale</span><span class="sxs-lookup"><span data-stu-id="84ba9-153">Manual upgrade</span></span>

<span data-ttu-id="84ba9-154">Se per qualche motivo l'aggiornamento automatico non riesce, è sempre possibile eseguire un aggiornamento manuale nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="84ba9-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="84ba9-155">Nel computer listener disinstallare il listener, il sito Web e l'agente (se è stato installato nel server) tramite il pannello di controllo programmi e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="84ba9-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="84ba9-156">Mantenere Redis installato in modo che i dati nella cache vengano mantenuti tramite il processo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="84ba9-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="84ba9-157">Installare le nuove versioni dei componenti, inclusi i valori salvati sopra quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="84ba9-157">Install the new versions of the components, including the values you saved above when prompted for them.</span></span> <span data-ttu-id="84ba9-158">Per altre informazioni sull'installazione di componenti, vedere [distribuire Gestione statistiche](deploy.md#BKMK_Deploy)</span><span class="sxs-lookup"><span data-stu-id="84ba9-158">For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="84ba9-159">Per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="84ba9-159">For more information</span></span>
<span data-ttu-id="84ba9-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="84ba9-160"></span></span>

<span data-ttu-id="84ba9-161">Per altre informazioni, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="84ba9-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="84ba9-162">Pianificare la gestione delle statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="84ba9-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="84ba9-163">Distribuire Gestione statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="84ba9-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="84ba9-164">Risolvere i problemi di gestione statistiche per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="84ba9-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
