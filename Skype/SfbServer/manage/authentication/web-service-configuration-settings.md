---
title: Gestire le impostazioni di configurazione dei servizi Web in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Riepilogo: gestire le impostazioni di configurazione dei servizi Web in Skype for Business Server.'
ms.openlocfilehash: 2ab23e499cff7678ddb50c57cdc6f396a3c4203c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818678"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="975d4-103">Gestire le impostazioni di configurazione dei servizi Web in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="975d4-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="975d4-104">**Riepilogo:** Gestire le impostazioni di configurazione dei servizi Web in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="975d4-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="975d4-105">È possibile usare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati a Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="975d4-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="975d4-106">Seguire questa procedura per creare un nuovo criterio di servizio Web.</span><span class="sxs-lookup"><span data-stu-id="975d4-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="975d4-107">Per creare nuove impostazioni di configurazione del servizio Web</span><span class="sxs-lookup"><span data-stu-id="975d4-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="975d4-108">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="975d4-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="975d4-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="975d4-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="975d4-110">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="975d4-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="975d4-111">Nella pagina **servizio Web** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="975d4-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="975d4-112">Per configurare il servizio Web per un sito, fare clic su **configurazione sito**.</span><span class="sxs-lookup"><span data-stu-id="975d4-112">To configure the Web Service for a site, click **Site configuration**.</span></span> <span data-ttu-id="975d4-113">In **Seleziona un sito**fare clic sul sito a cui verranno applicati i criteri di servizio Web e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="975d4-113">In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="975d4-114">Per configurare il servizio Web per un pool, fare clic su **Configurazione pool**.</span><span class="sxs-lookup"><span data-stu-id="975d4-114">To configure the Web Service for a pool, click **Pool configuration**.</span></span> <span data-ttu-id="975d4-115">In **Seleziona un servizio**fare clic sul servizio a cui verranno applicati i criteri di servizio Web e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="975d4-115">In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="975d4-116">Nell' **impostazione di un nuovo servizio Web**, nell' **autenticazione integrata di Windows**, selezionare **negozia**, **autenticazione di Windows integrata**o **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="975d4-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="975d4-117">Selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="975d4-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="975d4-118">**Abilitare l'autenticazione PIN** per consentire ai client di essere autenticati usando i numeri di pin.</span><span class="sxs-lookup"><span data-stu-id="975d4-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="975d4-119">**Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.</span><span class="sxs-lookup"><span data-stu-id="975d4-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="975d4-120">**Abilitare il download della catena di certificati per consentire** ai server presentati con un certificato di autenticazione di scaricare la catena di certificati per tale certificato.</span><span class="sxs-lookup"><span data-stu-id="975d4-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="975d4-121">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="975d4-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="975d4-122">Modificare le impostazioni di configurazione del servizio Web esistente</span><span class="sxs-lookup"><span data-stu-id="975d4-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="975d4-123">È possibile usare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati a Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="975d4-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="975d4-124">Seguire questa procedura per modificare un criterio di servizio Web esistente.</span><span class="sxs-lookup"><span data-stu-id="975d4-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="975d4-125">Per modificare le impostazioni di configurazione del servizio Web esistente</span><span class="sxs-lookup"><span data-stu-id="975d4-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="975d4-126">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="975d4-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="975d4-127">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="975d4-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="975d4-128">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="975d4-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="975d4-129">Nella pagina **servizio Web** fare clic su una configurazione, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="975d4-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="975d4-130">In **Modifica impostazione servizio Web**, in **autenticazione di Windows integrata**, selezionare **negozia**, **autenticazione di Windows integrata**o **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="975d4-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="975d4-131">Selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="975d4-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="975d4-132">**Abilitare l'autenticazione PIN** per consentire ai client di essere autenticati usando i numeri di pin.</span><span class="sxs-lookup"><span data-stu-id="975d4-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="975d4-133">**Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.</span><span class="sxs-lookup"><span data-stu-id="975d4-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="975d4-134">**Abilitare il download della catena di certificati per consentire** ai server presentati con un certificato di autenticazione di scaricare la catena di certificati per tale certificato.</span><span class="sxs-lookup"><span data-stu-id="975d4-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="975d4-135">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="975d4-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="975d4-136">Eliminare le impostazioni di configurazione del servizio Web esistenti</span><span class="sxs-lookup"><span data-stu-id="975d4-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="975d4-137">Seguire questa procedura per eliminare le impostazioni di configurazione del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="975d4-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="975d4-138">Per eliminare le impostazioni di configurazione del servizio Web</span><span class="sxs-lookup"><span data-stu-id="975d4-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="975d4-139">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="975d4-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="975d4-140">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="975d4-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="975d4-141">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="975d4-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="975d4-142">Nella pagina **servizio Web** e nel campo di ricerca digitare tutto o parte del nome del criterio che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="975d4-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="975d4-143">Nell'elenco dei criteri fare clic sui criteri desiderati, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="975d4-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="975d4-144">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="975d4-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="975d4-145">Eliminazione delle impostazioni di configurazione del servizio Web tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="975d4-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="975d4-146">Per eliminare le impostazioni di configurazione del servizio Web, è possibile usare Windows PowerShell e il cmdlet **Remove-CsWebServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="975d4-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="975d4-147">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="975d4-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="975d4-148">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="975d4-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="975d4-149">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="975d4-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="975d4-150">Per eliminare una raccolta specifica di impostazioni di configurazione del servizio Web</span><span class="sxs-lookup"><span data-stu-id="975d4-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="975d4-151">Il comando seguente rimuove le impostazioni di sicurezza del servizio Web applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="975d4-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="975d4-152">Per eliminare tutte le impostazioni di configurazione del servizio Web applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="975d4-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="975d4-153">Il comando seguente rimuove tutte le impostazioni di sicurezza del servizio Web applicate all'ambito del servizio:</span><span class="sxs-lookup"><span data-stu-id="975d4-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="975d4-154">Per eliminare tutte le impostazioni di configurazione del servizio Web che consentono l'autenticazione dei certificati</span><span class="sxs-lookup"><span data-stu-id="975d4-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="975d4-155">Il comando seguente rimuove tutte le impostazioni di sicurezza del servizio Web che consentono l'uso dell'autenticazione dei certificati:</span><span class="sxs-lookup"><span data-stu-id="975d4-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="975d4-156">Per informazioni dettagliate, vedere [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="975d4-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  

