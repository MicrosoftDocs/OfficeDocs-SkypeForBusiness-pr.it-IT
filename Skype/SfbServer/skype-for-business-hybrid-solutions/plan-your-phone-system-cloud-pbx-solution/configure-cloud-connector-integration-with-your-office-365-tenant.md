---
title: Configurare l'integrazione del connettore cloud con l'organizzazione di Microsoft 365 o Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Informazioni su come configurare l'integrazione del connettore cloud con l'organizzazione di Microsoft 365 o Office 365.
ms.openlocfilehash: bf5d8c4fb9684a205670701428fa8db30835a871
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359072"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="d9fca-103">Configurare l'integrazione del connettore cloud con l'organizzazione di Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="d9fca-103">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>

> [!Important] 
> <span data-ttu-id="d9fca-104">Cloud Connector Edition andrà in ritiro il 31 luglio 2021 insieme a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="d9fca-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="d9fca-105">Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Instradamento diretto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="d9fca-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="d9fca-106">Informazioni su come configurare l'integrazione del connettore cloud con l'organizzazione di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="d9fca-106">Learn how to configure Cloud Connector integration with your Microsoft 365 or Office 365 organization.</span></span>
  
<span data-ttu-id="d9fca-107">Al termine dell'installazione di Skype for Business Cloud Connector Edition, eseguire i passaggi descritti in questa sezione per configurare la distribuzione e connetterla all'organizzazione di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="d9fca-107">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Microsoft 365 or Office 365 organization.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="d9fca-108">Configurare le impostazioni del firewall</span><span class="sxs-lookup"><span data-stu-id="d9fca-108">Configure firewall settings</span></span>

<span data-ttu-id="d9fca-109">Configurare le impostazioni del firewall per le impostazioni del firewall interno ed esterno per la rete perimetrale per aprire le porte necessarie, come descritto [in](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) Porte e protocolli in Plan for Skype for Business Cloud [Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="d9fca-109">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="d9fca-110">Configurare i gateway PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="d9fca-110">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="d9fca-111">Configurare i trunk in ogni gateway PSTN in modo che puntino al Mediation Server per tutte le appliance.</span><span class="sxs-lookup"><span data-stu-id="d9fca-111">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="d9fca-112">Poiché l'FQDN del pool è lo stesso per tutti i server del pool, ogni trunk deve puntare a un FQDN o a un indirizzo IP di Mediation Server anziché all'FQDN del pool Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d9fca-112">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="d9fca-113">I trunk devono essere impostati con la stessa priorità.</span><span class="sxs-lookup"><span data-stu-id="d9fca-113">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="d9fca-114">Se si utilizza TLS tra Mediation Server e gateway, sarà necessario configurare i gateway e i Mediation Server per supportare MTLS nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d9fca-114">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="d9fca-115">Esportare la CA radice dal computer Di Active Directory di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d9fca-115">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="d9fca-116">Seguire le istruzioni del fornitore del gateway PSTN per l'importazione della CA radice.</span><span class="sxs-lookup"><span data-stu-id="d9fca-116">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="d9fca-117">Importare il certificato della CA radice per il certificato rilasciato al gateway nei Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d9fca-117">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="d9fca-118">Se è necessario ottenere un certificato SSL per il gateway, è possibile eseguire questa operazione utilizzando il servizio Autorità di certificazione in esecuzione nel computer Cloud Connector Active Directory nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d9fca-118">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="d9fca-119">Modificare il modello di server Web esistente per consentire agli utenti autenticati di registrarsi oppure creare un nuovo modello di server Web per configurare altre proprietà e consentire agli utenti autenticati di eseguire la registrazione.</span><span class="sxs-lookup"><span data-stu-id="d9fca-119">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="d9fca-120">Per istruzioni dettagliate, vedere [Modelli di certificato.](https://technet.microsoft.com/library/cc730705.aspx)</span><span class="sxs-lookup"><span data-stu-id="d9fca-120">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="d9fca-121">Richiedere un certificato utilizzando lo snap-in Certificati selezionando il modello server Web abilitato.</span><span class="sxs-lookup"><span data-stu-id="d9fca-121">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="d9fca-122">Assicurarsi di aggiungere nome comune in Oggetto e nome DNS in Nome alternativo con FQDN del gateway e verificare che nella chiave privata che rende esportabile la chiave privata sia selezionata in Opzioni chiave.</span><span class="sxs-lookup"><span data-stu-id="d9fca-122">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="d9fca-123">Esportare il certificato SSL con chiave privata e seguire le istruzioni del fornitore del gateway PSTN per l'importazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="d9fca-123">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="d9fca-124">Aggiornare il dominio per il tenant</span><span class="sxs-lookup"><span data-stu-id="d9fca-124">Update the domain for your tenant</span></span>

<span data-ttu-id="d9fca-125">Assicurarsi di aver completato i passaggi per aggiornare il dominio in Microsoft 365 o Office 365 e avere la possibilità di aggiungere record DNS.</span><span class="sxs-lookup"><span data-stu-id="d9fca-125">Make sure that you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="d9fca-126">Per ulteriori informazioni su come configurare il dominio in Microsoft 365 o Office 365, vedere Aggiungere un dominio [a Microsoft 365 o Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="d9fca-126">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-for-your-edge"></a><span data-ttu-id="d9fca-127">Aggiungere record DNS per il server perimetrale</span><span class="sxs-lookup"><span data-stu-id="d9fca-127">Add DNS records for your Edge</span></span>

<span data-ttu-id="d9fca-128">Aggiungere i record DNS seguenti all'organizzazione di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="d9fca-128">Add the following DNS records to your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="d9fca-129">Per informazioni su come aggiungere record DNS, vedere Aggiungere o modificare record [DNS personalizzati in Microsoft 365 o Office 365.](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)</span><span class="sxs-lookup"><span data-stu-id="d9fca-129">For information about how to add DNS records, see [Add or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="d9fca-130">Aggiungere un record A DNS per Access Edge.</span><span class="sxs-lookup"><span data-stu-id="d9fca-130">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="d9fca-131">I record SRV verranno creati automaticamente da Microsoft 365 o Office 365 e dagli script di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d9fca-131">SRV records will automatically be created by Microsoft 365 or Office 365 and the deployment scripts.</span></span> <span data-ttu-id="d9fca-132">Verificare che sia possibile cercare i due servizi SIP seguenti nel server perimetrale: \_ sip e \_ sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="d9fca-132">Confirm that you can look up the following two SIP services on the Edge: \_sip and \_sipfederationtls.</span></span>
    
     ![Conferma record SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a><span data-ttu-id="d9fca-134">Configurare la connettività ibrida tra Cloud Connector Edition e Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="d9fca-134">Set up hybrid connectivity between Cloud Connector Edition and Microsoft 365 or Office 365</span></span>

<span data-ttu-id="d9fca-135">Per configurare la connettività ibrida tra la distribuzione di Skype for Business Cloud Connector Edition e l'organizzazione di Microsoft 365 o Office 365, eseguire il cmdlet seguente in una sessione remota di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9fca-135">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="d9fca-136">Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [Configurare il computer per Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="d9fca-136">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="d9fca-137">Il cmdlet imposta l'FQDN esterno di Access Edge.</span><span class="sxs-lookup"><span data-stu-id="d9fca-137">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="d9fca-138">Nel primo dei comandi, deve essere quello per il \<External Access Edge FQDN\> ruolo Access Edge SIP.</span><span class="sxs-lookup"><span data-stu-id="d9fca-138">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="d9fca-139">Per impostazione predefinita, deve essere \<Domain Name\> ap.</span><span class="sxs-lookup"><span data-stu-id="d9fca-139">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="d9fca-140">L'FQDN access edge esterno utilizzato per la destinazione peer deve essere impostato su un sito PSTN che verrà utilizzato solo come fallback nel caso in cui un utente non sia assegnato a un sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="d9fca-140">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="d9fca-141">Per ulteriori informazioni, vedere [Distribuire un singolo sito in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e Distribuire più siti in Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="d9fca-141">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="d9fca-142">Configurare i gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="d9fca-142">Set up PSTN gateways</span></span>

<span data-ttu-id="d9fca-143">Configurare i trunk in ogni gateway PSTN in modo che puntino al Mediation Server per tutte le appliance.</span><span class="sxs-lookup"><span data-stu-id="d9fca-143">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="d9fca-144">Ogni trunk deve puntare a un FQDN o a un indirizzo IP di Mediation Server anziché all'FQDN del pool Mediation Server perché l'FQDN del pool è lo stesso per tutti i server del pool.</span><span class="sxs-lookup"><span data-stu-id="d9fca-144">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="d9fca-145">I trunk devono essere impostati con la stessa priorità.</span><span class="sxs-lookup"><span data-stu-id="d9fca-145">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="d9fca-146">Se si utilizza TLS tra Mediation Server e gateway, sarà necessario configurare i gateway e i Mediation Server per supportare MTLS nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d9fca-146">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="d9fca-147">Esportare la CA radice dal computer Di Active Directory di Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d9fca-147">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="d9fca-148">Seguire le istruzioni del fornitore del gateway PSTN per l'importazione della CA radice.</span><span class="sxs-lookup"><span data-stu-id="d9fca-148">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="d9fca-149">Importare il certificato della CA radice per il certificato rilasciato al gateway nei Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d9fca-149">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="d9fca-150">Se è necessario ottenere un certificato SSL per il gateway, è possibile eseguire questa operazione utilizzando il servizio Autorità di certificazione in esecuzione nel computer Cloud Connector Active Directory nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="d9fca-150">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="d9fca-151">Modificare il modello di server Web esistente per consentire agli utenti autenticati di eseguire la registrazione oppure creare un nuovo modello di server Web per configurare altre proprietà e consentire agli utenti autenticati di registrarsi.</span><span class="sxs-lookup"><span data-stu-id="d9fca-151">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="d9fca-152">Per istruzioni dettagliate, vedere [Modelli di certificato.](https://technet.microsoft.com/library/cc730705.aspx)</span><span class="sxs-lookup"><span data-stu-id="d9fca-152">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="d9fca-153">Richiedere un certificato utilizzando lo snap-in Certificati selezionando il modello server Web abilitato.</span><span class="sxs-lookup"><span data-stu-id="d9fca-153">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="d9fca-154">Assicurarsi di aggiungere nome comune in Oggetto e nome DNS in Nome alternativo con FQDN del gateway e verificare che nella chiave privata che rende esportabile la chiave privata sia selezionata in Opzioni chiave.</span><span class="sxs-lookup"><span data-stu-id="d9fca-154">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="d9fca-155">Esportare il certificato SSL con chiave privata e seguire le istruzioni del fornitore del gateway PSTN per l'importazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="d9fca-155">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="d9fca-156">I gateway PSTN in un sito PSTN devono connettersi solo ai Mediation Server nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="d9fca-156">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users"></a><span data-ttu-id="d9fca-157">Configurare gli utenti</span><span class="sxs-lookup"><span data-stu-id="d9fca-157">Set up your users</span></span>

<span data-ttu-id="d9fca-158">Accedere all'interfaccia di amministrazione di Microsoft 365, aggiungere gli utenti che saranno abilitati per i servizi vocali online e assegnare una licenza E5 o un componente aggiuntivo Sistema telefonico alla licenza E3 a questi utenti.</span><span class="sxs-lookup"><span data-stu-id="d9fca-158">Log in to the Microsoft 365 admin center, add the users that will be enabled for online voice services, and assign an E5 license or Phone System add-on to the E3 license to these users.</span></span> <span data-ttu-id="d9fca-159">Per informazioni sull'aggiunta di utenti, vedere [Aggiungere utenti a Microsoft 365 per le aziende.](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)</span><span class="sxs-lookup"><span data-stu-id="d9fca-159">For information about adding users, see [Add users to Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a><span data-ttu-id="d9fca-160">Abilitare gli utenti per i servizi vocali e vocali di Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="d9fca-160">Enable users for Phone System voice and voicemail services</span></span>
 
<span data-ttu-id="d9fca-161">Dopo aver aggiunto gli utenti a Microsoft 365 o Office 365, abilitare i propri account per i servizi vocali di Sistema telefonico, inclusa la segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="d9fca-161">After adding your users to Microsoft 365 or Office 365, enable their accounts for Phone System voice services, including voicemail.</span></span> <span data-ttu-id="d9fca-162">Per abilitare queste funzionalità, è necessario accedere all'organizzazione di Microsoft 365 o Office 365 con un account che è un ruolo di amministratore globale ed essere in grado di eseguire Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9fca-162">To enable these capabilities, you must log in to your Microsoft 365 or Office 365 organization with an account that is a Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="d9fca-163">Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [Configurare il computer per Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d9fca-163">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="d9fca-164">Assegnare il criterio all'utente e configurare il numero di telefono della voce aziendale dell'utente, specificato con il valore del parametro **Identity:**</span><span class="sxs-lookup"><span data-stu-id="d9fca-164">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="d9fca-165">È possibile specificare un'identità utente utilizzando l'indirizzo SIP dell'utente, il nome dell'entità utente (UPN) o il nome visualizzato di Active Directory dell'utente (ad esempio, "Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="d9fca-165">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="d9fca-166">Il carattere asterisco ( ) può essere utilizzato anche \* con il nome visualizzato come identità utente.</span><span class="sxs-lookup"><span data-stu-id="d9fca-166">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="d9fca-167">Ad esempio, l'identità " Smith" restituisce tutti gli utenti il cui nome visualizzato termina con il valore \* stringa "Smith".</span><span class="sxs-lookup"><span data-stu-id="d9fca-167">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="d9fca-168">È quindi possibile verificare che gli utenti siano stati aggiunti e abilitati utilizzando lo script seguente:</span><span class="sxs-lookup"><span data-stu-id="d9fca-168">You can then verify that the users were added and enabled using the following script:</span></span>
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="d9fca-169">Dovrai decidere se gli utenti devono essere in grado di effettuare chiamate internazionali.</span><span class="sxs-lookup"><span data-stu-id="d9fca-169">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="d9fca-170">Per impostazione predefinita, le chiamate internazionali sono abilitate.</span><span class="sxs-lookup"><span data-stu-id="d9fca-170">By default, international calling is enabled.</span></span> <span data-ttu-id="d9fca-171">È possibile disabilitare o abilitare gli utenti per la composizione internazionale utilizzando l'interfaccia di amministrazione online di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d9fca-171">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="d9fca-172">Per disabilitare le chiamate internazionali per utente, eseguire il cmdlet seguente in PowerShell di Skype for Business online:</span><span class="sxs-lookup"><span data-stu-id="d9fca-172">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="d9fca-173">Per abilitare nuovamente le chiamate internazionali per ogni utente dopo che è stata disabilitata, eseguire lo stesso cmdlet, ma modificare il valore di **PolicyName** in *InternationalCallsAllowed.*</span><span class="sxs-lookup"><span data-stu-id="d9fca-173">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="d9fca-174">Assegnare utenti a siti PSTN</span><span class="sxs-lookup"><span data-stu-id="d9fca-174">Assign users to PSTN sites</span></span>

<span data-ttu-id="d9fca-175">Usare PowerShell remoto del tenant per assegnare un sito agli utenti anche se è stato distribuito un solo sito.</span><span class="sxs-lookup"><span data-stu-id="d9fca-175">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="d9fca-176">Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [Configurare il computer per Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="d9fca-176">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="d9fca-177">Se a un utente non è assegnato alcun sito PSTN, la connettività ibrida tra la distribuzione di Skype for Business Cloud Connector Edition e l'organizzazione di Microsoft 365 o Office 365 verrà tornerà a usare il livello di tenant predefinito 1 (Destinazione peer) in modo che le chiamate possano essere completate.</span><span class="sxs-lookup"><span data-stu-id="d9fca-177">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="d9fca-178">Configurare le impostazioni di Mediation Server ibrido online</span><span class="sxs-lookup"><span data-stu-id="d9fca-178">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="d9fca-179"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="d9fca-179"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="d9fca-180">Quando una chiamata P2P viene inoltrata a una conferenza PSTN, il server per conferenze di Skype for Business online invierà un invito al Mediation Server del connettore cloud.</span><span class="sxs-lookup"><span data-stu-id="d9fca-180">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="d9fca-181">Per assicurarsi che Microsoft 365 o Office 365 possa instradare correttamente questo invito, è necessario configurare un'impostazione nel tenant online per ogni Mediation Server cloud Connector come segue:</span><span class="sxs-lookup"><span data-stu-id="d9fca-181">To ensure that Microsoft 365 or Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="d9fca-182">Creare un utente nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9fca-182">Create a user in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d9fca-183">Utilizzare il nome utente desiderato, ad esempio "MediationServer1".</span><span class="sxs-lookup"><span data-stu-id="d9fca-183">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="d9fca-184">Utilizzare il dominio SIP predefinito di Cloud Connector (il primo dominio SIP nel file ini) come dominio utente.</span><span class="sxs-lookup"><span data-stu-id="d9fca-184">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="d9fca-185">Tieni presente che l'assegnazione della licenza è necessaria solo per la propagazione dell'utente nella directory di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="d9fca-185">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="d9fca-186">Assegnare una licenza di Microsoft 365 o Office 365 (ad esempio E5) all'account creato, consentire fino a un'ora per la propagazione delle modifiche, verificare che il provisioning degli account utente sia stato eseguito correttamente nella directory di Skype for Business online eseguendo il cmdlet seguente, quindi rimuovere la licenza da questo account.</span><span class="sxs-lookup"><span data-stu-id="d9fca-186">Assign a Microsoft 365 or Office 365 license (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="d9fca-187">Avviare una sessione remota di PowerShell di Azure AD tenant utilizzando le credenziali di amministratore globale o utente, quindi eseguire il cmdlet seguente per impostare il reparto per l'account utente di Azure AD configurato nel passaggio 1 su "HybridMediationServer":</span><span class="sxs-lookup"><span data-stu-id="d9fca-187">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="d9fca-188">Avviare una sessione remota di PowerShell di Skype for Business tenant utilizzando le credenziali di amministratore tenant di Skype for Business, quindi eseguire il cmdlet seguente per impostare l'FQDN di Mediation Server ed Edge Server su tale account utente, sostituendo con il nome visualizzato dell'utente per l'account creato nel passaggio \<DisplayName\> 1:</span><span class="sxs-lookup"><span data-stu-id="d9fca-188">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="d9fca-189">Per l'identità, utilizzare il nome visualizzato dell'account utente creato per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d9fca-189">For Identity, use the Display Name of the user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="d9fca-190">Per  *MediationServerFQDN,*  utilizzare il nome di dominio completo interno definito per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d9fca-190">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="d9fca-191">Per  *EdgeServerExternalFQDN,*  utilizzare il nome di dominio completo esterno definito per il proxy di accesso del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d9fca-191">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="d9fca-192">Se sono presenti più siti PSTN del connettore cloud, scegliere l'FQDN del proxy di accesso al server perimetrale assegnato al sito in cui si trova il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="d9fca-192">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="d9fca-193">Se sono presenti più Mediation Server cloud Connector (più siti, ha), ripetere i passaggi precedenti per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="d9fca-193">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    
