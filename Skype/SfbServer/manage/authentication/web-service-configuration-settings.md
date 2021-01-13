---
title: Gestire le impostazioni di configurazione del servizio Web in Skype for Business Server
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
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Riepilogo: gestire le impostazioni di configurazione del servizio Web in Skype for Business Server.'
ms.openlocfilehash: 68abe01614902d5e6f4c58040b30b6afbd475df8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806496"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="d7eea-103">Gestire le impostazioni di configurazione del servizio Web in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d7eea-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="d7eea-104">**Riepilogo:** Gestire le impostazioni di configurazione del servizio Web in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d7eea-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="d7eea-105">È possibile utilizzare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d7eea-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="d7eea-106">Eseguire la procedura seguente per creare un nuovo criterio di servizio Web.</span><span class="sxs-lookup"><span data-stu-id="d7eea-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="d7eea-107">Per creare nuove impostazioni di configurazione del servizio Web</span><span class="sxs-lookup"><span data-stu-id="d7eea-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="d7eea-108">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d7eea-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="d7eea-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d7eea-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="d7eea-110">Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="d7eea-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="d7eea-111">Nella pagina **servizio Web** fare clic su **nuovo** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7eea-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="d7eea-112">Per configurare il servizio Web per un sito, fare clic su **configurazione sito**.</span><span class="sxs-lookup"><span data-stu-id="d7eea-112">To configure the Web Service for a site, click **Site configuration**.</span></span> <span data-ttu-id="d7eea-113">In **Seleziona un sito** fare clic sul sito a cui verranno applicati i criteri del servizio Web e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7eea-113">In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="d7eea-114">Per configurare il servizio Web per un pool, fare clic su **Configurazione pool**.</span><span class="sxs-lookup"><span data-stu-id="d7eea-114">To configure the Web Service for a pool, click **Pool configuration**.</span></span> <span data-ttu-id="d7eea-115">In **Seleziona un servizio** fare clic sul servizio a cui verranno applicati i criteri del servizio Web e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7eea-115">In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="d7eea-116">In **nuova impostazione del servizio Web**, in **autenticazione integrata di Windows**, selezionare **negozia**, **autenticazione integrata di Windows** o **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="d7eea-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="d7eea-117">Selezionare una o più delle opzioni seguenti in base alle capacità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="d7eea-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="d7eea-118">**Abilita autenticazione PIN** per consentire l'autenticazione dei client tramite numeri PIN.</span><span class="sxs-lookup"><span data-stu-id="d7eea-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="d7eea-119">**Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.</span><span class="sxs-lookup"><span data-stu-id="d7eea-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="d7eea-120">**Abilita download catena di certificati** per fare in modo che i server a cui viene presentato un certificato di autenticazione eseguano il download della catena di certificati per tale certificato.</span><span class="sxs-lookup"><span data-stu-id="d7eea-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="d7eea-121">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="d7eea-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="d7eea-122">Modificare le impostazioni di configurazione del servizio Web esistenti</span><span class="sxs-lookup"><span data-stu-id="d7eea-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="d7eea-123">È possibile utilizzare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d7eea-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="d7eea-124">Eseguire la procedura seguente per modificare i criteri per un servizio Web esistente.</span><span class="sxs-lookup"><span data-stu-id="d7eea-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="d7eea-125">Per modificare le impostazioni di configurazione del servizio Web esistenti</span><span class="sxs-lookup"><span data-stu-id="d7eea-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="d7eea-126">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d7eea-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="d7eea-127">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d7eea-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="d7eea-128">Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="d7eea-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="d7eea-129">Nella pagina **Servizio Web** fare clic su una configurazione, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="d7eea-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d7eea-130">In **Modifica impostazione servizio Web**, in **Autenticazione integrata di Windows**, selezionare **Negoziazione**, **Autenticazione integrata di Windows** o **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="d7eea-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="d7eea-131">Selezionare una o più delle opzioni seguenti in base alle capacità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="d7eea-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="d7eea-132">**Abilita autenticazione PIN** per consentire l'autenticazione dei client tramite numeri PIN.</span><span class="sxs-lookup"><span data-stu-id="d7eea-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="d7eea-133">**Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.</span><span class="sxs-lookup"><span data-stu-id="d7eea-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="d7eea-134">**Abilita download catena di certificati** per fare in modo che i server a cui viene presentato un certificato di autenticazione eseguano il download della catena di certificati per tale certificato.</span><span class="sxs-lookup"><span data-stu-id="d7eea-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="d7eea-135">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="d7eea-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="d7eea-136">Eliminare le impostazioni di configurazione del servizio Web esistenti</span><span class="sxs-lookup"><span data-stu-id="d7eea-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="d7eea-137">Eseguire la procedura seguente per eliminare le impostazioni di configurazione del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="d7eea-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="d7eea-138">Per eliminare le impostazioni di configurazione del servizio Web</span><span class="sxs-lookup"><span data-stu-id="d7eea-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="d7eea-139">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d7eea-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="d7eea-140">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d7eea-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="d7eea-141">Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="d7eea-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="d7eea-142">Nella pagina **Servizio Web** digitare il nome dei criteri che si desidera eliminare nel campo di ricerca, per intero o in parte.</span><span class="sxs-lookup"><span data-stu-id="d7eea-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="d7eea-143">Nell'elenco dei criteri fare clic sui criteri desiderati, fare clic su **Modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="d7eea-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="d7eea-144">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d7eea-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d7eea-145">Eliminazione delle impostazioni di configurazione del servizio Web tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7eea-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d7eea-146">È possibile eliminare le impostazioni di configurazione del servizio Web utilizzando Windows PowerShell e il cmdlet **Remove-CsWebServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d7eea-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="d7eea-147">È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7eea-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d7eea-148">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo del Blog ["Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="d7eea-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="d7eea-149">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d7eea-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="d7eea-150">Per eliminare una raccolta specifica di impostazioni di configurazione di servizi Web</span><span class="sxs-lookup"><span data-stu-id="d7eea-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="d7eea-151">Con il comando seguente vengono rimosse le impostazioni di sicurezza di servizi Web applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="d7eea-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="d7eea-152">Per eliminare tutte le impostazioni di configurazione del servizio Web applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="d7eea-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="d7eea-153">Con il comando seguente vengono rimosse tutte le impostazioni di sicurezza di servizi Web applicate nell'ambito del servizio:</span><span class="sxs-lookup"><span data-stu-id="d7eea-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="d7eea-154">Per eliminare tutte le impostazioni di configurazione del servizio Web che consentono l'autenticazione dei certificati</span><span class="sxs-lookup"><span data-stu-id="d7eea-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="d7eea-155">Con il comando seguente vengono rimosse tutte le impostazioni di sicurezza di servizi Web che consentono l'utilizzo dell'autenticazione basata sui certificati:</span><span class="sxs-lookup"><span data-stu-id="d7eea-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="d7eea-156">Per informazioni dettagliate, vedere [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d7eea-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  

