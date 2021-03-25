---
title: Gestire le impostazioni di configurazione della funzione di registrazione in Skype for Business Server
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
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Riepilogo: gestire le impostazioni di configurazione della funzione di registrazione per Skype for Business Server.'
ms.openlocfilehash: a1cd1048ea37a249126ec892560312a482459d44
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119575"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="2f953-103">Gestire le impostazioni di configurazione della funzione di registrazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2f953-103">Manage Registrar configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="2f953-104">**Riepilogo:** Gestire le impostazioni di configurazione della funzione di registrazione per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2f953-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server.</span></span>
  
<span data-ttu-id="2f953-p101">È possibile utilizzare la funzione di registrazione per configurare metodi di autenticazione di server proxy. Il protocollo di autenticazione specificato determina il tipo di richieste dei server del pool per i client. I protocolli disponibili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f953-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>
  
- <span data-ttu-id="2f953-108">**Kerberos** Si tratta dello schema di autenticazione basato su password più forte disponibile per i client, ma in genere è disponibile solo per i client aziendali perché richiede la connessione client a un Centro distribuzione chiavi (controller di dominio Kerberos).</span><span class="sxs-lookup"><span data-stu-id="2f953-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="2f953-109">Questa impostazione è appropriata se il server deve eseguire solo l'autenticazione dei client aziendali.</span><span class="sxs-lookup"><span data-stu-id="2f953-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="2f953-110">**NTLM** Si tratta dell'autenticazione basata su password disponibile per i client che utilizzano uno schema di hashing challenge-response sulla password.</span><span class="sxs-lookup"><span data-stu-id="2f953-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="2f953-111">È l'unica forma di autenticazione disponibile per i client senza connettività a un Centro distribuzione chiavi (controller di dominio Kerberos), ad esempio gli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="2f953-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="2f953-112">Se un server autentica solo utenti remoti, è consigliabile scegliere NTLM.</span><span class="sxs-lookup"><span data-stu-id="2f953-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="2f953-113">**Autenticazione certificato** Questo è il nuovo metodo di autenticazione quando il server deve ottenere certificati dai client Lync Phone Edition, dai telefoni delle aree comuni, da Skype for Business e dall'app Lync Windows Store.</span><span class="sxs-lookup"><span data-stu-id="2f953-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="2f953-114">Nei client Lync Phone Edition, dopo che un utente esegue l'accesso e viene autenticato correttamente fornendo un PIN ( Personal Identification Number), Skype for Business Server effettua quindi il provisioning dell'URI SIP al telefono ed effettua il provisioning di un certificato firmato skype for Business Server o di un certificato utente che identifica Joe (Ex: SN=joe@contoso.com ) al telefono.</span><span class="sxs-lookup"><span data-stu-id="2f953-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="2f953-115">Questo certificato viene utilizzato per l'autenticazione con la funzione di Registrazione avanzata e i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="2f953-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2f953-p105">È consigliabile abilitare sia Kerberos sia NTLM quando un server supporta l'autenticazione per client remoti e aziendali. Il server perimetrale e i server interni comunicano per assicurare che ai client remoti venga offerta solo l'autenticazione NTLM. I server in cui è abilitata solo l'autenticazione Kerberos non sono in grado di autenticare gli utenti remoti. Se il server autentica anche gli utenti aziendali, viene utilizzato Kerberos.</span><span class="sxs-lookup"><span data-stu-id="2f953-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="2f953-120">Se si utilizzeranno client di app lync di Windows Store, è necessario abilitare l'autenticazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="2f953-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="2f953-121">Per creare nuove impostazioni di configurazione della funzione di registrazione</span><span class="sxs-lookup"><span data-stu-id="2f953-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="2f953-122">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2f953-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="2f953-123">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2f953-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="2f953-124">Sulla barra di spostamento sinistra fare clic su **Sicurezza**, quindi su **Funzione di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="2f953-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="2f953-125">Nella pagina **Funzione di registrazione** fare clic su **Nuovo**</span><span class="sxs-lookup"><span data-stu-id="2f953-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="2f953-126">In **Seleziona un servizio** fare clic sul servizio a cui applicare la funzione di registrazione e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f953-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="2f953-127">In **Impostazione funzione di registrazione** selezionare una o più opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="2f953-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="2f953-128">**Abilita autenticazione Kerberos** per fare in modo che tutti i server del pool emettano richieste utilizzando l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="2f953-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="2f953-129">**Abilita autenticazione NTLM** per fare in modo che tutti i server del pool emettano richieste utilizzando l'autenticazione NTLM.</span><span class="sxs-lookup"><span data-stu-id="2f953-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="2f953-130">**Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.</span><span class="sxs-lookup"><span data-stu-id="2f953-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="2f953-131">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="2f953-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="2f953-132">Modificare le impostazioni di configurazione esistenti della funzione di registrazione</span><span class="sxs-lookup"><span data-stu-id="2f953-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="2f953-133">È possibile utilizzare la funzione di registrazione per configurare i protocolli di autenticazione dei server proxy.</span><span class="sxs-lookup"><span data-stu-id="2f953-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2f953-p106">Se un server supporta l'autenticazione sia per client remoti che per client aziendali, è consigliabile abilitare sia Kerberos che NTLM. Il server perimetrale e i server interni sono in comunicazione per garantire che ai client remoti sia fornita solo l'autenticazione NTLM. Se in questi server è abilitato solo Kerberos, non sono in grado di autenticare gli utenti remoti. Se attraverso questi server avviene anche l'autenticazione degli utenti aziendali, viene utilizzato Kerberos.</span><span class="sxs-lookup"><span data-stu-id="2f953-p106">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="2f953-138">Per modificare una funzione di registrazione esistente, seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="2f953-138">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="2f953-139">Per modificare le impostazioni di configurazione della funzione di registrazione esistente</span><span class="sxs-lookup"><span data-stu-id="2f953-139">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="2f953-140">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2f953-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="2f953-141">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2f953-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="2f953-142">Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Funzione di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="2f953-142">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="2f953-143">Nella pagina **Funzione di registrazione** fare clic su un servizio, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="2f953-143">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2f953-144">In **Modifica impostazione funzione di registrazione** selezionare una o più delle opzioni seguenti in base alle capacità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="2f953-144">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="2f953-145">**Abilita autenticazione Kerberos** perché i server del pool emettano richieste utilizzando l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="2f953-145">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="2f953-146">**Abilita autenticazione NTLM** per fare in modo che tutti i server del pool emettano richieste utilizzando l'autenticazione NTLM.</span><span class="sxs-lookup"><span data-stu-id="2f953-146">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="2f953-147">**Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.</span><span class="sxs-lookup"><span data-stu-id="2f953-147">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="2f953-148">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="2f953-148">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="2f953-149">Per eliminare le impostazioni di configurazione della funzione di registrazione</span><span class="sxs-lookup"><span data-stu-id="2f953-149">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="2f953-150">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2f953-150">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="2f953-151">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2f953-151">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2f953-152">Sulla barra di spostamento sinistra fare clic su **Sicurezza**, quindi su **Funzione di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="2f953-152">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="2f953-153">Nella pagina **Funzione di registrazione** digitare il nome della funzione di registrazione che si desidera eliminare nel campo di ricerca, per intero o in parte.</span><span class="sxs-lookup"><span data-stu-id="2f953-153">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="2f953-154">Nell'elenco fare clic sulla funzione di registrazione desiderata, fare clic su **Modifica**, quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="2f953-154">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="2f953-155">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f953-155">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2f953-156">Rimozione delle impostazioni di configurazione della funzione di registrazione tramite Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="2f953-156">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2f953-157">È possibile eliminare le impostazioni di configurazione della funzione di registrazione utilizzando Windows PowerShell e il cmdlet **Remove-CsProxyConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="2f953-157">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="2f953-158">È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f953-158">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2f953-159">Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo di blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="2f953-159">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="2f953-160">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2f953-160">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="2f953-161">Per rimuovere un set specifico di impostazioni di sicurezza della funzione di registrazione</span><span class="sxs-lookup"><span data-stu-id="2f953-161">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="2f953-162">Il comando seguente rimuove le impostazioni di sicurezza della funzione di registrazione applicate al server perimetrale atl-edge-011.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="2f953-162">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="2f953-163">Per rimuovere tutte le impostazioni di sicurezza della funzione di registrazione applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="2f953-163">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="2f953-164">Il comando seguente rimuove tutte le impostazioni di sicurezza della funzione di registrazione applicate al servizio di registrazione:</span><span class="sxs-lookup"><span data-stu-id="2f953-164">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="2f953-165">Per rimuovere tutte le impostazioni di sicurezza della funzione di registrazione che consentono l'autenticazione NTLM</span><span class="sxs-lookup"><span data-stu-id="2f953-165">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="2f953-166">Il comando seguente elimina tutte le impostazioni di sicurezza della funzione di registrazione che consentono l'utilizzo di NTLM per l'autenticazione client:</span><span class="sxs-lookup"><span data-stu-id="2f953-166">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="2f953-167">Per informazioni dettagliate, [vedere Remove-CsProxyConfiguration.](/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="2f953-167">For details, see [Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
