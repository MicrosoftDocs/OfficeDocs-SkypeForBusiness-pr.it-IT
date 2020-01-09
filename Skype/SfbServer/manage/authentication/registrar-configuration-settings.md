---
title: Gestire le impostazioni di configurazione del registrar in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Riepilogo: gestire le impostazioni di configurazione del registrar per Skype for Business Server.'
ms.openlocfilehash: 8aac78f782b7a9db23d3bb124943c55cdbd8565a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992303"
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="be97b-103">Gestire le impostazioni di configurazione del registrar in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="be97b-103">Manage Registrar configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="be97b-104">**Riepilogo:** Gestire le impostazioni di configurazione del registrar per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="be97b-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server.</span></span>
  
<span data-ttu-id="be97b-105">È possibile usare il registrar per configurare i metodi di autenticazione del server proxy.</span><span class="sxs-lookup"><span data-stu-id="be97b-105">You can use the Registrar to configure proxy server authentication methods.</span></span> <span data-ttu-id="be97b-106">Il protocollo di autenticazione specificato determina il tipo di problemi che i server del pool rilasciano ai client.</span><span class="sxs-lookup"><span data-stu-id="be97b-106">The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients.</span></span> <span data-ttu-id="be97b-107">I protocolli disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="be97b-107">The available protocols are:</span></span>
  
- <span data-ttu-id="be97b-108">**Kerberos** Questo è lo schema di autenticazione basato su password più forte disponibile per i client, ma in genere è disponibile solo per i client aziendali, perché richiede la connessione del client a un centro distribuzione chiave (controller di dominio Kerberos).</span><span class="sxs-lookup"><span data-stu-id="be97b-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="be97b-109">Questa impostazione è appropriata se il server autentica solo i client aziendali.</span><span class="sxs-lookup"><span data-stu-id="be97b-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="be97b-110">**NTLM** Questa è l'autenticazione basata su password disponibile per i client che usano uno schema di hash per la risposta alla richiesta di verifica sulla password.</span><span class="sxs-lookup"><span data-stu-id="be97b-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="be97b-111">Questa è l'unica forma di autenticazione disponibile per i client senza connettività a un centro distribuzione chiave (controller di dominio Kerberos), ad esempio utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="be97b-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="be97b-112">Se un server esegue l'autenticazione solo per gli utenti remoti, è necessario scegliere NTLM.</span><span class="sxs-lookup"><span data-stu-id="be97b-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="be97b-113">**Autenticazione del certificato** Questo è il nuovo metodo di autenticazione quando il server deve ottenere i certificati da client Lync Phone Edition, telefoni area comune, Skype for business e l'app Lync di Windows Store.</span><span class="sxs-lookup"><span data-stu-id="be97b-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="be97b-114">Nei client di Lync Phone Edition, dopo che un utente ha effettuato l'accesso ed è stato autenticato fornendo un PIN (Personal Identification Number), Skype for Business Server applica quindi l'URI SIP al telefono e prevede un certificato firmato Skype for Business Server o un certificato utente che identifica Joe (es: SN=joe@contoso.com) al telefono.</span><span class="sxs-lookup"><span data-stu-id="be97b-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="be97b-115">Questo certificato viene usato per l'autenticazione con il registrar e i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="be97b-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="be97b-116">È consigliabile abilitare sia Kerberos che NTLM quando un server supporta l'autenticazione sia per i client remoti che per quelli aziendali.</span><span class="sxs-lookup"><span data-stu-id="be97b-116">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients.</span></span> <span data-ttu-id="be97b-117">Il server perimetrale e i server interni comunicano per garantire che solo l'autenticazione NTLM venga offerta ai client remoti.</span><span class="sxs-lookup"><span data-stu-id="be97b-117">The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients.</span></span> <span data-ttu-id="be97b-118">Se in questi server è abilitato solo Kerberos, non è possibile eseguire l'autenticazione degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="be97b-118">If only Kerberos is enabled on these servers, they cannot authenticate remote users.</span></span> <span data-ttu-id="be97b-119">Se gli utenti aziendali eseguono l'autenticazione anche sul server, viene usato Kerberos.</span><span class="sxs-lookup"><span data-stu-id="be97b-119">If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="be97b-120">Se si utilizzeranno i client delle app Lync di Windows Store, è necessario abilitare l'autenticazione dei certificati.</span><span class="sxs-lookup"><span data-stu-id="be97b-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="be97b-121">Per creare nuove impostazioni di configurazione del registrar</span><span class="sxs-lookup"><span data-stu-id="be97b-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="be97b-122">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="be97b-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="be97b-123">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="be97b-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="be97b-124">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **registrar**.</span><span class="sxs-lookup"><span data-stu-id="be97b-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="be97b-125">Nella pagina **registrar** fare clic su **nuovo**</span><span class="sxs-lookup"><span data-stu-id="be97b-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="be97b-126">In **Seleziona un servizio**fare clic sul servizio a cui deve essere applicato il registrar e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="be97b-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="be97b-127">In **nuova impostazione registrar**selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="be97b-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="be97b-128">**Abilitare l'autenticazione Kerberos per consentire** ai server del pool di emettere problemi con l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="be97b-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="be97b-129">**Abilitare l'autenticazione NTLM per consentire** ai server del pool di emettere problemi con NTLM.</span><span class="sxs-lookup"><span data-stu-id="be97b-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="be97b-130">**Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.</span><span class="sxs-lookup"><span data-stu-id="be97b-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="be97b-131">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="be97b-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="be97b-132">Modificare le impostazioni di configurazione del registrar esistenti</span><span class="sxs-lookup"><span data-stu-id="be97b-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="be97b-133">È possibile usare il registrar per configurare i protocolli di autenticazione del server proxy.</span><span class="sxs-lookup"><span data-stu-id="be97b-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="be97b-134">È consigliabile abilitare sia Kerberos che NTLM quando un server supporta l'autenticazione sia per i client remoti che per quelli aziendali.</span><span class="sxs-lookup"><span data-stu-id="be97b-134">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients.</span></span> <span data-ttu-id="be97b-135">Il server perimetrale e i server interni comunicano per garantire che solo l'autenticazione NTLM venga offerta ai client remoti.</span><span class="sxs-lookup"><span data-stu-id="be97b-135">The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients.</span></span> <span data-ttu-id="be97b-136">Se in questi server è abilitato solo Kerberos, non è possibile eseguire l'autenticazione degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="be97b-136">If only Kerberos is enabled on these servers, they cannot authenticate remote users.</span></span> <span data-ttu-id="be97b-137">Se gli utenti aziendali eseguono l'autenticazione anche sul server, viene usato Kerberos.</span><span class="sxs-lookup"><span data-stu-id="be97b-137">If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="be97b-138">Seguire questa procedura per modificare un registrar esistente.</span><span class="sxs-lookup"><span data-stu-id="be97b-138">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="be97b-139">Per modificare le impostazioni di configurazione del registrar esistenti</span><span class="sxs-lookup"><span data-stu-id="be97b-139">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="be97b-140">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="be97b-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="be97b-141">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="be97b-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="be97b-142">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **registrar**.</span><span class="sxs-lookup"><span data-stu-id="be97b-142">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="be97b-143">Nella pagina **registrar** fare clic su un servizio, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="be97b-143">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="be97b-144">In **modifica registrar**selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="be97b-144">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="be97b-145">**Abilitare l'autenticazione Kerberos per consentire** ai server del pool di emettere problemi con l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="be97b-145">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="be97b-146">**Abilitare l'autenticazione NTLM per consentire** ai server del pool di emettere problemi con NTLM.</span><span class="sxs-lookup"><span data-stu-id="be97b-146">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="be97b-147">**Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.</span><span class="sxs-lookup"><span data-stu-id="be97b-147">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="be97b-148">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="be97b-148">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="be97b-149">Per eliminare le impostazioni di configurazione del registrar</span><span class="sxs-lookup"><span data-stu-id="be97b-149">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="be97b-150">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .</span><span class="sxs-lookup"><span data-stu-id="be97b-150">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="be97b-151">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="be97b-151">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="be97b-152">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **registrar**.</span><span class="sxs-lookup"><span data-stu-id="be97b-152">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="be97b-153">Nella pagina **registrar** e nel campo di ricerca digitare tutto o parte del nome del registrar che si vuole eliminare.</span><span class="sxs-lookup"><span data-stu-id="be97b-153">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="be97b-154">Nell'elenco fare clic sul registrar desiderato, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="be97b-154">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="be97b-155">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="be97b-155">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="be97b-156">Rimozione delle impostazioni di configurazione del registrar tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be97b-156">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="be97b-157">Per eliminare le impostazioni di configurazione del registrar, è possibile usare Windows PowerShell e il cmdlet **Remove-CsProxyConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="be97b-157">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="be97b-158">Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="be97b-158">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="be97b-159">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="be97b-159">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="be97b-160">Il processo è lo stesso in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="be97b-160">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="be97b-161">Per rimuovere un set specifico di impostazioni di sicurezza del registrar</span><span class="sxs-lookup"><span data-stu-id="be97b-161">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="be97b-162">Il comando seguente rimuove le impostazioni di sicurezza del registrar applicate alla atl-edge-011.litwareinc.com di Edge Server:</span><span class="sxs-lookup"><span data-stu-id="be97b-162">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```PowerShell
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="be97b-163">Per rimuovere tutte le impostazioni di sicurezza del registrar applicate all'ambito del sito</span><span class="sxs-lookup"><span data-stu-id="be97b-163">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="be97b-164">Il comando seguente rimuove tutte le impostazioni di sicurezza del registrar applicate al servizio Registrar:</span><span class="sxs-lookup"><span data-stu-id="be97b-164">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="be97b-165">Per rimuovere tutte le impostazioni di sicurezza del registrar che consentono l'autenticazione NTLM</span><span class="sxs-lookup"><span data-stu-id="be97b-165">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="be97b-166">Il comando seguente elimina tutte le impostazioni di sicurezza del registrar che consentono l'uso di NTLM per l'autenticazione client:</span><span class="sxs-lookup"><span data-stu-id="be97b-166">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```PowerShell
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="be97b-167">Per informazioni dettagliate, vedere [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="be97b-167">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
  

