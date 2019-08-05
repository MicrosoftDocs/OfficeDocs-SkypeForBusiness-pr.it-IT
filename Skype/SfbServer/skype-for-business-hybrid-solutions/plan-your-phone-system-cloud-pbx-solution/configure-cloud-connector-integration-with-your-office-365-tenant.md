---
title: Configurare l'integrazione del connettore Cloud con il tenant di Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Informazioni su come configurare l'integrazione con il Cloud Connector con il tenant di Office 365.
ms.openlocfilehash: 1742fbadec95eb72e46fb6cc46f006e1baeaf8f1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190874"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a><span data-ttu-id="a102b-103">Configurare l'integrazione del connettore Cloud con il tenant di Office 365</span><span class="sxs-lookup"><span data-stu-id="a102b-103">Configure Cloud Connector integration with your Office 365 tenant</span></span>
 
<span data-ttu-id="a102b-104">Informazioni su come configurare l'integrazione con il Cloud Connector con il tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="a102b-104">Learn how to configure Cloud Connector integration with your Office 365 tenant.</span></span>
  
<span data-ttu-id="a102b-105">Una volta completata l'installazione di Skype for Business Cloud Connector Edition, eseguire i passaggi descritti in questa sezione per configurare la distribuzione e connetterla al tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="a102b-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Office 365 tenant.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="a102b-106">Configurare le impostazioni del firewall</span><span class="sxs-lookup"><span data-stu-id="a102b-106">Configure firewall settings</span></span>

<span data-ttu-id="a102b-107">Configurare le impostazioni del firewall per le impostazioni del firewall interno ed esterno per la rete perimetrale per aprire le porte necessarie come descritto in [porte e protocolli](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [piano per Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="a102b-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="a102b-108">Configurare i gateway PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="a102b-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="a102b-109">Configurare Trunks in ogni gateway PSTN per puntare di nuovo a Mediation Server per tutti gli elettrodomestici.</span><span class="sxs-lookup"><span data-stu-id="a102b-109">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="a102b-110">Poiché il nome di dominio completo del pool è lo stesso per tutti i server del pool, ogni trunk deve puntare a un nome di dominio completo di Mediation Server o indirizzo IP anziché il nome di dominio completo del pool di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="a102b-110">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="a102b-111">I trunk devono essere impostati nella stessa priorità.</span><span class="sxs-lookup"><span data-stu-id="a102b-111">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="a102b-112">Se si usa TLS tra i server di mediazione e i gateway, sarà necessario configurare i gateway e i server di mediazione per supportare MTLS nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="a102b-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="a102b-113">Esportare la CA radice dal computer Active Directory Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a102b-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="a102b-114">Seguire le istruzioni del fornitore del gateway PSTN per l'importazione della CA radice.</span><span class="sxs-lookup"><span data-stu-id="a102b-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="a102b-115">Importare il certificato della CA radice per il certificato emesso nel gateway in Mediation Servers.</span><span class="sxs-lookup"><span data-stu-id="a102b-115">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="a102b-116">Se è necessario ottenere un certificato SSL per il gateway, è possibile eseguire questa operazione usando il servizio autorità di certificazione in uso nel computer Active Directory Cloud Connector, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a102b-116">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="a102b-117">Modificare il modello di server Web esistente per consentire agli utenti autenticati di eseguire la registrazione oppure creare un nuovo modello di server Web per configurare altre proprietà e consentire agli utenti autenticati di eseguire la registrazione.</span><span class="sxs-lookup"><span data-stu-id="a102b-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="a102b-118">Per istruzioni dettagliate, vedere [modelli di certificato](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="a102b-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/en-us/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="a102b-119">Richiedere un certificato usando lo snap-in certificato selezionando il modello di server Web abilitato.</span><span class="sxs-lookup"><span data-stu-id="a102b-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="a102b-120">Assicurarsi di aggiungere il nome comune in nome oggetto e DNS in nome alternativo con FQDN del gateway e verificare che nella chiave privata sia selezionata l'opzione Imposta chiave privata esportabile in opzioni chiave.</span><span class="sxs-lookup"><span data-stu-id="a102b-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="a102b-121">Esportare il certificato SSL con la chiave privata e seguire le istruzioni del fornitore del gateway PSTN per l'importazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="a102b-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="a102b-122">Aggiornare il dominio per il tenant</span><span class="sxs-lookup"><span data-stu-id="a102b-122">Update the domain for your tenant</span></span>

<span data-ttu-id="a102b-123">Verificare di aver completato i passaggi per aggiornare il dominio in Office 365 e avere la possibilità di aggiungere record DNS.</span><span class="sxs-lookup"><span data-stu-id="a102b-123">Make sure that you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="a102b-124">Per altre informazioni su come configurare il dominio in Office 365, vedere [aggiungere un dominio a office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="a102b-124">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a><span data-ttu-id="a102b-125">Aggiungere record DNS in Office 365 per il proprio Edge</span><span class="sxs-lookup"><span data-stu-id="a102b-125">Add DNS records in Office 365 for your Edge</span></span>

<span data-ttu-id="a102b-126">Aggiungere i record DNS seguenti al tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="a102b-126">Add the following DNS records to your Office 365 tenant.</span></span> <span data-ttu-id="a102b-127">Per informazioni su come aggiungere record DNS al tenant di Office 365, vedere [aggiungere o modificare record DNS personalizzati in office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="a102b-127">For information about how to add DNS records to your Office 365 tenant, see [Add or edit custom DNS records in Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="a102b-128">Aggiungere un record DNS per Edge Access.</span><span class="sxs-lookup"><span data-stu-id="a102b-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="a102b-129">I record SRV verranno creati automaticamente da Office 365 e dagli script di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a102b-129">SRV records will automatically be created by Office 365 and the deployment scripts.</span></span> <span data-ttu-id="a102b-130">Verificare che sia possibile cercare i due servizi SIP seguenti in Edge: _sip e _sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="a102b-130">Confirm that you can look up the following two SIP services on the Edge: _sip and _sipfederationtls.</span></span>
    
     ![Conferma di record SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a><span data-ttu-id="a102b-132">Configurare la connettività ibrida tra Cloud Connector Edition e Office 365</span><span class="sxs-lookup"><span data-stu-id="a102b-132">Set up hybrid connectivity between Cloud Connector Edition and Office 365</span></span>

<span data-ttu-id="a102b-133">Per configurare la connettività ibrida tra la distribuzione di Skype for Business Cloud Connector Edition e il tenant di Office 365, eseguire il cmdlet seguente in una sessione remota di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a102b-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="a102b-134">Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [configurare il computer per Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a102b-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="a102b-135">Il cmdlet imposta il nome di dominio completo esterno di Access Edge.</span><span class="sxs-lookup"><span data-stu-id="a102b-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="a102b-136">Nel primo dei comandi l' \<FQDN\> del bordo di accesso esterno deve essere quello per il ruolo di Access Edge SIP.</span><span class="sxs-lookup"><span data-stu-id="a102b-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="a102b-137">Per impostazione predefinita, questo deve essere il\<nome\>di AP. Domain.</span><span class="sxs-lookup"><span data-stu-id="a102b-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="a102b-138">L'FQDN del bordo di accesso esterno usato per la destinazione peer deve essere impostato su un sito PSTN che verrà usato solo come fallback, se un utente non viene assegnato a un sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="a102b-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="a102b-139">Per altre informazioni, vedere [distribuire un singolo sito nel Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e [distribuire più siti in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="a102b-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="a102b-140">Configurare gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="a102b-140">Set up PSTN gateways</span></span>

<span data-ttu-id="a102b-141">Configurare Trunks in ogni gateway PSTN per puntare di nuovo a Mediation Server per tutti gli elettrodomestici.</span><span class="sxs-lookup"><span data-stu-id="a102b-141">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="a102b-142">Ogni trunk deve puntare a un FQDN di Mediation Server o a un indirizzo IP anziché al nome di dominio completo del pool di Mediation Server, perché il nome di dominio completo del pool è uguale per tutti i server del pool.</span><span class="sxs-lookup"><span data-stu-id="a102b-142">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="a102b-143">I trunk devono essere impostati nella stessa priorità.</span><span class="sxs-lookup"><span data-stu-id="a102b-143">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="a102b-144">Se si usa TLS tra i server di mediazione e i gateway, sarà necessario configurare i gateway e i server di mediazione per supportare MTLS nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="a102b-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="a102b-145">Esportare la CA radice dal computer Active Directory Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a102b-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="a102b-146">Seguire le istruzioni del fornitore del gateway PSTN per l'importazione della CA radice.</span><span class="sxs-lookup"><span data-stu-id="a102b-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="a102b-147">Importare il certificato della CA radice per il certificato emesso nel gateway in Mediation Servers.</span><span class="sxs-lookup"><span data-stu-id="a102b-147">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="a102b-148">Se è necessario ottenere un certificato SSL per il gateway, è possibile eseguire questa operazione usando il servizio autorità di certificazione in uso nel computer Active Directory Cloud Connector, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a102b-148">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="a102b-149">Modificare il modello di server Web esistente per consentire agli utenti autenticati di eseguire la registrazione oppure creare un nuovo modello di server Web per configurare altre proprietà e consentire agli utenti autenticati di eseguire la registrazione.</span><span class="sxs-lookup"><span data-stu-id="a102b-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="a102b-150">Per istruzioni dettagliate, vedere [modelli di certificato](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="a102b-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="a102b-151">Richiedere un certificato usando lo snap-in certificato selezionando il modello di server Web abilitato.</span><span class="sxs-lookup"><span data-stu-id="a102b-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="a102b-152">Assicurarsi di aggiungere il nome comune in nome oggetto e DNS in nome alternativo con FQDN del gateway e verificare che nella chiave privata sia selezionata l'opzione Imposta chiave privata esportabile in opzioni chiave.</span><span class="sxs-lookup"><span data-stu-id="a102b-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="a102b-153">Esportare il certificato SSL con la chiave privata e seguire le istruzioni del fornitore del gateway PSTN per l'importazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="a102b-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="a102b-154">I gateway PSTN in un sito PSTN devono connettersi solo ai server di mediazione nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="a102b-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users-in-office-365"></a><span data-ttu-id="a102b-155">Configurare gli utenti in Office 365</span><span class="sxs-lookup"><span data-stu-id="a102b-155">Set up your users in Office 365</span></span>

<span data-ttu-id="a102b-156">Accedere al portale di amministrazione di Office 365, aggiungere gli utenti che verranno abilitati per i servizi vocali online e assegnare una licenza E5 o un sistema telefonico nel componente aggiuntivo di Office 365 alla licenza E3 per questi utenti.</span><span class="sxs-lookup"><span data-stu-id="a102b-156">Log in to the Office 365 admin portal, add the users that will be enabled for online voice services, and assign an E5 license or Phone System in Office 365 add-on to the E3 license to these users.</span></span> <span data-ttu-id="a102b-157">Per informazioni sull'aggiunta di utenti, vedere [aggiungere utenti a Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span><span class="sxs-lookup"><span data-stu-id="a102b-157">For information about adding users, see [Add users to Office 365 for business](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a><span data-ttu-id="a102b-158">Abilitare gli utenti per il sistema telefonico in Office 365 servizi vocali e della segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="a102b-158">Enable users for Phone System in Office 365 voice and voicemail services</span></span>

<span data-ttu-id="a102b-159">Dopo aver aggiunto gli utenti a Office 365, abilitare gli account per il sistema telefonico in Office 365 Voice Services, inclusa la segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="a102b-159">After adding your users to Office 365, enable their accounts for Phone System in Office 365 voice services, including voicemail.</span></span> <span data-ttu-id="a102b-160">Per abilitare queste funzionalità, è necessario accedere al tenant di Office 365 con un account che è un ruolo di amministratore globale di Office 365 ed essere in grado di eseguire una sessione remota di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a102b-160">To enable these capabilities, you must log in to your Office 365 tenant with an account that is an Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="a102b-161">Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [configurare il computer per Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a102b-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="a102b-162">Assegnare i criteri all'utente e configurare il numero di telefono vocale aziendale dell'utente, specificato con il valore del parametro **Identity** :</span><span class="sxs-lookup"><span data-stu-id="a102b-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="a102b-163">È anche possibile specificare l'identità di un utente per l'indirizzo SIP, il nome dell'entità utente (UPN), il nome di dominio e il nomeutente (dominio\nomeutente) e il nome visualizzato in Active Directory ("Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="a102b-163">You can also specify a user's Identity by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
<span data-ttu-id="a102b-164">Puoi quindi verificare che gli utenti siano stati aggiunti e abilitati usando lo script seguente:</span><span class="sxs-lookup"><span data-stu-id="a102b-164">You can then verify that the users were added and enabled using the following script:</span></span>
  
```
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

<span data-ttu-id="a102b-165">È necessario decidere se gli utenti devono essere in grado di effettuare chiamate internazionali.</span><span class="sxs-lookup"><span data-stu-id="a102b-165">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="a102b-166">Per impostazione predefinita, le chiamate internazionali sono abilitate.</span><span class="sxs-lookup"><span data-stu-id="a102b-166">By default, international calling is enabled.</span></span> <span data-ttu-id="a102b-167">Puoi disabilitare o abilitare gli utenti per la chiamata internazionale usando l'interfaccia di amministrazione di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="a102b-167">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="a102b-168">Per disabilitare le chiamate internazionali per ogni utente, eseguire il cmdlet seguente in Skype for Business Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a102b-168">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="a102b-169">Per riabilitare le chiamate internazionali per ogni utente dopo la disattivazione, eseguire lo stesso cmdlet, ma modificare il valore di PolicyName \*\*\*\* in *InternationalCallsAllowed* .</span><span class="sxs-lookup"><span data-stu-id="a102b-169">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="a102b-170">Assegnare utenti a siti PSTN</span><span class="sxs-lookup"><span data-stu-id="a102b-170">Assign users to PSTN sites</span></span>

<span data-ttu-id="a102b-171">Usare PowerShell remoto del tenant per assegnare un sito agli utenti anche se è stato distribuito solo un singolo sito.</span><span class="sxs-lookup"><span data-stu-id="a102b-171">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="a102b-172">Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [configurare il computer per Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a102b-172">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="a102b-173">Se non viene assegnato un sito PSTN a un utente, la connettività ibrida tra la distribuzione di Skype for Business Cloud Connector Edition e il tenant di Office 365 ritornerà a usare il livello di tenant predefinito (peer Destination) in modo che le chiamate possano essere completate.</span><span class="sxs-lookup"><span data-stu-id="a102b-173">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Office 365 tenant will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="a102b-174">Configurare le impostazioni del server di mediazione ibrida online</span><span class="sxs-lookup"><span data-stu-id="a102b-174">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="a102b-175"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="a102b-175"></span></span>

<span data-ttu-id="a102b-176">Quando una chiamata P2P viene escalated in una conferenza PSTN, Skype for business online Conferencing Server invierà un invito al Cloud Connector Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="a102b-176">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="a102b-177">Per assicurarsi che Office 365 possa instradare l'invito correttamente, è necessario configurare un'impostazione nel tenant online per ogni Mediation Server di Cloud Connector come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a102b-177">To ensure that Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="a102b-178">Creare un utente nel portale di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="a102b-178">Create a user in the Office 365 admin portal.</span></span> <span data-ttu-id="a102b-179">Usare il nome utente desiderato, ad esempio "MediationServer1".</span><span class="sxs-lookup"><span data-stu-id="a102b-179">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="a102b-180">Usa il dominio SIP predefinito di Cloud Connector (il primo dominio SIP nel file ini) come dominio utente.</span><span class="sxs-lookup"><span data-stu-id="a102b-180">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="a102b-181">Tieni presente che l'assegnazione delle licenze è necessaria solo per la propagazione degli utenti nella directory Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="a102b-181">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="a102b-182">Assegnare una licenza di Office 365 (ad esempio E5) all'account creato, consentire fino a un'ora per la propagazione delle modifiche, verificare che gli account utente siano stati provisionati correttamente nella directory di Skype for business online eseguendo il cmdlet seguente e quindi rimuovere il licenza da questo account.</span><span class="sxs-lookup"><span data-stu-id="a102b-182">Assign an Office 365 licenses (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```
   Gets-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="a102b-183">Avviare una sessione remota di PowerShell per tenant Azure AD utilizzando le credenziali di amministratore globale o utente e quindi eseguire il cmdlet seguente per impostare il reparto per l'account utente di Azure AD configurato nel passaggio 1 in "HybridMediationServer":</span><span class="sxs-lookup"><span data-stu-id="a102b-183">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="a102b-184">Avviare una sessione remota di PowerShell per Skype for business con le credenziali di amministratore del tenant di Skype for business e quindi eseguire il cmdlet seguente per impostare il nome di dominio completo di Mediation Server e \<Edge\> server su tale account utente, sostituendo DisplayName con il nome visualizzato dell'utente per l'account creato nel passaggio 1:</span><span class="sxs-lookup"><span data-stu-id="a102b-184">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="a102b-185">Per identità, usare il nome visualizzato dell'account utente di Office 365 creato per questo Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="a102b-185">For Identity, use the Display Name of the Office 365 user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="a102b-186">Per *MediationServerFQDN* , usa il nome di dominio completo interno definito per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="a102b-186">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="a102b-187">Per *EdgeServerExternalFQDN* , usa il nome FQDN esterno definito per il proxy di accesso a Edge Server.</span><span class="sxs-lookup"><span data-stu-id="a102b-187">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="a102b-188">Se sono presenti più siti PSTN per il connettore Cloud, scegliere il nome di dominio completo del proxy di Access Edge Server assegnato al sito in cui si trova il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="a102b-188">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="a102b-189">Se sono presenti più server di mediazione Cloud Connector (più siti, HA), ripetere i passaggi precedenti per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="a102b-189">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    

