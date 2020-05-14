---
title: Configurare l'integrazione del connettore Cloud con l'organizzazione Microsoft 365 o Office 365
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
description: Informazioni su come configurare l'integrazione dei connettori cloud con l'organizzazione Microsoft 365 o Office 365.
ms.openlocfilehash: 2c65551ce75efce61f82d47ac2b9c16db555ab42
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221246"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a><span data-ttu-id="58cb0-103">Configurare l'integrazione del connettore Cloud con l'organizzazione Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="58cb0-103">Configure Cloud Connector integration with your Microsoft 365 or Office 365 organization</span></span>
 
<span data-ttu-id="58cb0-104">Informazioni su come configurare l'integrazione dei connettori cloud con l'organizzazione Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="58cb0-104">Learn how to configure Cloud Connector integration with your Microsoft 365 or Office 365 organization.</span></span>
  
<span data-ttu-id="58cb0-105">Dopo aver completato l'installazione di Skype for Business Cloud Connector Edition, eseguire la procedura descritta in questa sezione per configurare la distribuzione e connetterla all'organizzazione Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="58cb0-105">Once the Skype for Business Cloud Connector Edition installation is complete, perform the steps in this section to configure your deployment and connect it to your Microsoft 365 or Office 365 organization.</span></span>
  
## <a name="configure-firewall-settings"></a><span data-ttu-id="58cb0-106">Configurare le impostazioni del firewall</span><span class="sxs-lookup"><span data-stu-id="58cb0-106">Configure firewall settings</span></span>

<span data-ttu-id="58cb0-107">Configurare le impostazioni del firewall per le impostazioni del firewall interno ed esterno per la rete perimetrale per aprire le porte necessarie come descritto in [porte e protocolli](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span><span class="sxs-lookup"><span data-stu-id="58cb0-107">Configure the firewall settings for your internal and external firewall settings for you perimeter network to open the required ports as described in [Ports and protocols](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) in [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span>
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a><span data-ttu-id="58cb0-108">Configurare i gateway PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="58cb0-108">Set up Public Switched Telephone Network (PSTN) gateways</span></span>

<span data-ttu-id="58cb0-109">Configurare trunk su ogni gateway PSTN in modo che punti a Mediation Server per tutti gli elettrodomestici.</span><span class="sxs-lookup"><span data-stu-id="58cb0-109">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="58cb0-110">Poiché il nome FQDN del pool è lo stesso per tutti i server del pool, ciascun trunk deve puntare a un FQDN Mediation Server o a un indirizzo IP anziché all'FQDN del pool di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="58cb0-110">Because the pool FQDN is the same for all servers in the pool, each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN.</span></span> <span data-ttu-id="58cb0-111">I trunk devono essere impostati con la stessa priorità.</span><span class="sxs-lookup"><span data-stu-id="58cb0-111">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="58cb0-112">Se si utilizza TLS tra Mediation Server e gateway, sarà necessario configurare i gateway e Mediation Server per supportare MTLS, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="58cb0-112">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="58cb0-113">Esportare la CA radice dal computer di Active Directory del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="58cb0-113">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="58cb0-114">Seguire le istruzioni del fornitore del gateway PSTN per l'importazione della CA radice.</span><span class="sxs-lookup"><span data-stu-id="58cb0-114">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="58cb0-115">Importare il certificato della CA radice per il certificato emesso sul gateway nei Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="58cb0-115">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="58cb0-116">Se è necessario ottenere un certificato SSL per il gateway, è possibile eseguire questa operazione utilizzando il servizio autorità di certificazione in esecuzione nel computer del connettore Cloud Active Directory come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="58cb0-116">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="58cb0-117">Modificare il modello di server Web esistente per consentire agli utenti autenticati di registrare o creare un nuovo modello di server Web per configurare altre proprietà e consentire agli utenti autenticati di eseguire la registrazione.</span><span class="sxs-lookup"><span data-stu-id="58cb0-117">Modify the existing Web Server template to enable Authenticated users to enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="58cb0-118">Per istruzioni dettagliate, vedere [modelli di certificato](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="58cb0-118">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="58cb0-119">Richiedere un certificato mediante lo snap-in certificato selezionando il modello di server Web abilitato.</span><span class="sxs-lookup"><span data-stu-id="58cb0-119">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="58cb0-120">Assicurarsi di aggiungere il nome comune in Subject and DNS Name in nome alternativo con il nome di dominio completo del gateway e confermare che la chiave privata che rende esportabile la chiave privata sia selezionata in opzioni chiave.</span><span class="sxs-lookup"><span data-stu-id="58cb0-120">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="58cb0-121">Esportare il certificato SSL con la chiave privata e seguire le istruzioni del fornitore del gateway PSTN per l'importazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="58cb0-121">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
## <a name="update-the-domain-for-your-tenant"></a><span data-ttu-id="58cb0-122">Aggiornare il dominio per il tenant</span><span class="sxs-lookup"><span data-stu-id="58cb0-122">Update the domain for your tenant</span></span>

<span data-ttu-id="58cb0-123">Assicurarsi di aver completato la procedura per aggiornare il dominio in Microsoft 365 o Office 365 e avere la possibilità di aggiungere record DNS.</span><span class="sxs-lookup"><span data-stu-id="58cb0-123">Make sure that you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="58cb0-124">Per ulteriori informazioni su come configurare il dominio in Microsoft 365 o Office 365, vedere [aggiungere un dominio a microsoft 365 o office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span><span class="sxs-lookup"><span data-stu-id="58cb0-124">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
  
## <a name="add-dns-records-for-your-edge"></a><span data-ttu-id="58cb0-125">Aggiungere record DNS per il proprio server perimetrale</span><span class="sxs-lookup"><span data-stu-id="58cb0-125">Add DNS records for your Edge</span></span>

<span data-ttu-id="58cb0-126">Aggiungere i seguenti record DNS all'organizzazione Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="58cb0-126">Add the following DNS records to your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="58cb0-127">Per informazioni su come aggiungere record DNS, vedere [aggiungere o modificare record DNS personalizzati in Microsoft 365 o Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span><span class="sxs-lookup"><span data-stu-id="58cb0-127">For information about how to add DNS records, see [Add or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).</span></span>
  
1. <span data-ttu-id="58cb0-128">Aggiungere un record A DNS per Access Edge.</span><span class="sxs-lookup"><span data-stu-id="58cb0-128">Add a DNS A record for Access Edge.</span></span>
    
2. <span data-ttu-id="58cb0-129">I record SRV verranno creati automaticamente da Microsoft 365 o Office 365 e dagli script di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="58cb0-129">SRV records will automatically be created by Microsoft 365 or Office 365 and the deployment scripts.</span></span> <span data-ttu-id="58cb0-130">Verificare che sia possibile cercare i due servizi SIP seguenti nel server perimetrale: \_ SIP e \_ sipfederationtls.</span><span class="sxs-lookup"><span data-stu-id="58cb0-130">Confirm that you can look up the following two SIP services on the Edge: \_sip and \_sipfederationtls.</span></span>
    
     ![Conferma dei record SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a><span data-ttu-id="58cb0-132">Configurare la connettività ibrida tra Cloud Connector Edition e Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="58cb0-132">Set up hybrid connectivity between Cloud Connector Edition and Microsoft 365 or Office 365</span></span>

<span data-ttu-id="58cb0-133">Per configurare la connettività ibrida tra la distribuzione di Skype for Business Cloud Connector Edition e l'organizzazione Microsoft 365 o Office 365, eseguire il cmdlet seguente in una sessione di PowerShell remota.</span><span class="sxs-lookup"><span data-stu-id="58cb0-133">To configure hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization, run the following cmdlet in a remote PowerShell session.</span></span> <span data-ttu-id="58cb0-134">Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [configurare il computer per Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="58cb0-134">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
<span data-ttu-id="58cb0-135">Il cmdlet imposta il nome di dominio completo esterno di Access Edge.</span><span class="sxs-lookup"><span data-stu-id="58cb0-135">The cmdlet sets the Access Edge external FQDN.</span></span> <span data-ttu-id="58cb0-136">Nel primo dei comandi, l'FQDN del \< perimetro di accesso esterno \> deve essere quello per il ruolo Access Edge SIP.</span><span class="sxs-lookup"><span data-stu-id="58cb0-136">In the first of the commands, the \<External Access Edge FQDN\> should be the one for the SIP Access Edge role.</span></span> <span data-ttu-id="58cb0-137">Per impostazione predefinita, questo dovrebbe essere AP. \< Nome di dominio \> .</span><span class="sxs-lookup"><span data-stu-id="58cb0-137">By default, this should be ap.\<Domain Name\>.</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> <span data-ttu-id="58cb0-138">L'FQDN del perimetro di accesso esterno utilizzato per la destinazione peer deve essere impostato su un sito PSTN che verrà utilizzato solo come fallback nel caso in cui un utente non sia assegnato a un sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="58cb0-138">The External Access Edge FQDN used for Peer Destination should be set to a PSTN site that will only be used as a fallback in case a user isn't assigned to a PSTN site.</span></span> <span data-ttu-id="58cb0-139">Per ulteriori informazioni, vedere [deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e [deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="58cb0-139">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
## <a name="set-up-pstn-gateways"></a><span data-ttu-id="58cb0-140">Configurare i gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="58cb0-140">Set up PSTN gateways</span></span>

<span data-ttu-id="58cb0-141">Configurare trunk su ogni gateway PSTN in modo che punti a Mediation Server per tutti gli elettrodomestici.</span><span class="sxs-lookup"><span data-stu-id="58cb0-141">Set up trunks on each PSTN gateway to point back to Mediation Servers for all appliances.</span></span> <span data-ttu-id="58cb0-142">Ogni trunk deve puntare a un FQDN Mediation Server o a un indirizzo IP anziché all'FQDN del pool di Mediation Server, in quanto l'FQDN del pool è lo stesso per tutti i server del pool.</span><span class="sxs-lookup"><span data-stu-id="58cb0-142">Each trunk should point to one Mediation Server FQDN or IP address instead of the Mediation Server pool FQDN because the pool FQDN is the same for all servers in the pool.</span></span> <span data-ttu-id="58cb0-143">I trunk devono essere impostati con la stessa priorità.</span><span class="sxs-lookup"><span data-stu-id="58cb0-143">Trunks should be set in the same priority.</span></span>
  
<span data-ttu-id="58cb0-144">Se si utilizza TLS tra Mediation Server e gateway, sarà necessario configurare i gateway e Mediation Server per supportare MTLS, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="58cb0-144">If you are using TLS between Mediation Servers and gateways, you will need to configure the gateways and Mediation Servers to support MTLS as follows:</span></span>
  
1. <span data-ttu-id="58cb0-145">Esportare la CA radice dal computer di Active Directory del connettore Cloud.</span><span class="sxs-lookup"><span data-stu-id="58cb0-145">Export the Root CA from the Cloud Connector Active Directory computer.</span></span>
    
2. <span data-ttu-id="58cb0-146">Seguire le istruzioni del fornitore del gateway PSTN per l'importazione della CA radice.</span><span class="sxs-lookup"><span data-stu-id="58cb0-146">Follow the PSTN gateway vendor instructions for importing the Root CA.</span></span>
    
3. <span data-ttu-id="58cb0-147">Importare il certificato della CA radice per il certificato emesso sul gateway nei Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="58cb0-147">Import the Root CA certificate for the certificate issued to your gateway on the Mediation Servers.</span></span> <span data-ttu-id="58cb0-148">Se è necessario ottenere un certificato SSL per il gateway, è possibile eseguire questa operazione utilizzando il servizio autorità di certificazione in esecuzione nel computer del connettore Cloud Active Directory come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="58cb0-148">If you need to obtain an SSL certificate for the gateway, you may do this using the Certificate Authority service running on the Cloud Connector Active Directory computer as follows:</span></span>
    
   - <span data-ttu-id="58cb0-149">Modificare il modello di server Web esistente per consentire agli utenti autenticati di registrare o creare un nuovo modello di server Web per configurare altre proprietà e consentire agli utenti autenticati di eseguire la registrazione.</span><span class="sxs-lookup"><span data-stu-id="58cb0-149">Modify the existing Web Server template to enable Authenticated users to Enroll, or create a new Web Server template to configure other properties and enable Authenticated users to enroll.</span></span> <span data-ttu-id="58cb0-150">Per istruzioni dettagliate, vedere [modelli di certificato](https://technet.microsoft.com/library/cc730705.aspx).</span><span class="sxs-lookup"><span data-stu-id="58cb0-150">For detailed instructions, see [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).</span></span>
    
   - <span data-ttu-id="58cb0-151">Richiedere un certificato mediante lo snap-in certificato selezionando il modello di server Web abilitato.</span><span class="sxs-lookup"><span data-stu-id="58cb0-151">Request a certificate using Certificate snap-in selecting the Web Server template that you have enabled.</span></span> <span data-ttu-id="58cb0-152">Assicurarsi di aggiungere il nome comune in Subject and DNS Name in nome alternativo con il nome di dominio completo del gateway e confermare che la chiave privata che rende esportabile la chiave privata sia selezionata in opzioni chiave.</span><span class="sxs-lookup"><span data-stu-id="58cb0-152">Be sure to add Common name in Subject and DNS name in Alternative name with FQDN of the gateway, and confirm on the Private Key that Make private key exportable is selected under key options.</span></span> 
    
4. <span data-ttu-id="58cb0-153">Esportare il certificato SSL con la chiave privata e seguire le istruzioni del fornitore del gateway PSTN per l'importazione del certificato.</span><span class="sxs-lookup"><span data-stu-id="58cb0-153">Export the SSL certificate with Private key and follow the instructions from your PSTN gateway vendor for importing the certificate.</span></span>
    
5. <span data-ttu-id="58cb0-154">I gateway PSTN in un sito PSTN devono connettersi solo ai Mediation Server nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="58cb0-154">PSTN gateway(s) in one PSTN site should only connect to the Mediation Server(s) in the same site.</span></span>
    
## <a name="set-up-your-users"></a><span data-ttu-id="58cb0-155">Configurare gli utenti</span><span class="sxs-lookup"><span data-stu-id="58cb0-155">Set up your users</span></span>

<span data-ttu-id="58cb0-156">Accedere all'interfaccia di amministrazione di Microsoft 365, aggiungere gli utenti che verranno abilitati per i servizi vocali online e assegnare una licenza E5 o un componente aggiuntivo di sistema telefonico alla licenza E3 per questi utenti.</span><span class="sxs-lookup"><span data-stu-id="58cb0-156">Log in to the Microsoft 365 admin center, add the users that will be enabled for online voice services, and assign an E5 license or Phone System add-on to the E3 license to these users.</span></span> <span data-ttu-id="58cb0-157">Per informazioni sull'aggiunta di utenti, vedere [aggiungere utenti a Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span><span class="sxs-lookup"><span data-stu-id="58cb0-157">For information about adding users, see [Add users to Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).</span></span>
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a><span data-ttu-id="58cb0-158">Abilitare gli utenti per i servizi vocali e di segreteria telefonica del sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="58cb0-158">Enable users for Phone System voice and voicemail services</span></span>
 
<span data-ttu-id="58cb0-159">Dopo aver aggiunto gli utenti a Microsoft 365 o Office 365, abilitare gli account per i servizi vocali del sistema telefonico, inclusa la segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="58cb0-159">After adding your users to Microsoft 365 or Office 365, enable their accounts for Phone System voice services, including voicemail.</span></span> <span data-ttu-id="58cb0-160">Per abilitare queste funzionalità, è necessario accedere all'organizzazione Microsoft 365 o Office 365 con un account che sia un ruolo di amministratore globale ed essere in grado di eseguire Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="58cb0-160">To enable these capabilities, you must log in to your Microsoft 365 or Office 365 organization with an account that is a Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="58cb0-161">Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [configurare il computer per Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="58cb0-161">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)</span></span>
  
- <span data-ttu-id="58cb0-162">Assegnare il criterio all'utente e configurare il numero di telefono della segreteria telefonica dell'utente, specificato con il valore del parametro **Identity** :</span><span class="sxs-lookup"><span data-stu-id="58cb0-162">Assign the policy to your user and configure the user's business voice phone number, which you specify with the value of the **Identity** parameter:</span></span>
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > <span data-ttu-id="58cb0-163">È possibile specificare un'identità utente utilizzando l'indirizzo SIP dell'utente, il nome dell'entità utente (UPN) o il nome visualizzato di Active Directory dell'utente (ad esempio, "Bob Kelly").</span><span class="sxs-lookup"><span data-stu-id="58cb0-163">A user identity can be specified using the user's SIP address, user principal name (UPN), or the user's Active Directory display name (for example, "Bob Kelly").</span></span> <span data-ttu-id="58cb0-164">Il carattere asterisco ( \* ) può essere utilizzato anche con il nome visualizzato come identità dell'utente.</span><span class="sxs-lookup"><span data-stu-id="58cb0-164">The asterisk (\*) character can also be used with the Display Name as the user Identity.</span></span> <span data-ttu-id="58cb0-165">Ad esempio, il parametro Identity " \* Smith" restituisce tutti gli utenti che dispongono di un nome visualizzato che termina con il valore stringa "Smith".</span><span class="sxs-lookup"><span data-stu-id="58cb0-165">For example, the Identity "\*Smith" returns all the users who have a display name that ends with the string value "Smith".</span></span>
  
<span data-ttu-id="58cb0-166">È quindi possibile verificare che gli utenti siano stati aggiunti e abilitati utilizzando lo script seguente:</span><span class="sxs-lookup"><span data-stu-id="58cb0-166">You can then verify that the users were added and enabled using the following script:</span></span>
  
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

<span data-ttu-id="58cb0-167">È necessario decidere se gli utenti devono essere in grado di effettuare chiamate internazionali.</span><span class="sxs-lookup"><span data-stu-id="58cb0-167">You'll need to decide whether your users should be able to make international calls.</span></span> <span data-ttu-id="58cb0-168">Per impostazione predefinita, la chiamata internazionale è abilitata.</span><span class="sxs-lookup"><span data-stu-id="58cb0-168">By default, international calling is enabled.</span></span> <span data-ttu-id="58cb0-169">È possibile disabilitare o abilitare gli utenti per la composizione internazionale utilizzando l'interfaccia di amministrazione di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="58cb0-169">You can disable or enable users for international dialing using the online Skype for Business admin center.</span></span>
  
<span data-ttu-id="58cb0-170">Per disabilitare le chiamate internazionali per ogni utente, eseguire il seguente cmdlet in PowerShell per Skype for business online:</span><span class="sxs-lookup"><span data-stu-id="58cb0-170">To disable international calling on a per user basis, run the following cmdlet in Skype for Business Online PowerShell:</span></span>
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

<span data-ttu-id="58cb0-171">Per riabilitare la chiamata internazionale per ogni utente dopo che è stata disattivata, eseguire lo stesso cmdlet, ma cambiare il valore di **PolicyName** in *InternationalCallsAllowed* .</span><span class="sxs-lookup"><span data-stu-id="58cb0-171">To re-enable international calling on a per user basis after it has been disabled, run the same cmdlet, but change the value for **PolicyName** to *InternationalCallsAllowed*  .</span></span>
  
## <a name="assign-users-to-pstn-sites"></a><span data-ttu-id="58cb0-172">Assegnare gli utenti ai siti PSTN</span><span class="sxs-lookup"><span data-stu-id="58cb0-172">Assign users to PSTN sites</span></span>

<span data-ttu-id="58cb0-173">Utilizzare PowerShell remote tenant per assegnare un sito agli utenti anche se è stato distribuito un singolo sito.</span><span class="sxs-lookup"><span data-stu-id="58cb0-173">Use tenant remote PowerShell to assign a site to users even if you only deployed a single site.</span></span> <span data-ttu-id="58cb0-174">Per informazioni su come stabilire una sessione remota di PowerShell, vedere: [configurare il computer per Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="58cb0-174">To learn how to establish a remote PowerShell session, see: [Set up your computer for Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).</span></span>
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> <span data-ttu-id="58cb0-175">Se non è stato assegnato alcun sito PSTN a un utente, la connettività ibrida tra la distribuzione di Skype for Business Cloud Connector Edition e l'organizzazione di Microsoft 365 o Office 365 ritornerà per utilizzare il livello di tenant default One (peer Destination) in modo che le chiamate possano essere completate.</span><span class="sxs-lookup"><span data-stu-id="58cb0-175">If no PSTN site is assigned to a user, hybrid connectivity between your Skype for Business Cloud Connector Edition deployment and your Microsoft 365 or Office 365 organization will fall back to use the tenant level default one (Peer Destination) so that calls can be completed.</span></span> 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a><span data-ttu-id="58cb0-176">Configurare le impostazioni di Mediation server ibrido online</span><span class="sxs-lookup"><span data-stu-id="58cb0-176">Configure online hybrid Mediation Server Settings</span></span>
<span data-ttu-id="58cb0-177"><a name="BKMK_ConfigureMediationServer"> </a></span><span class="sxs-lookup"><span data-stu-id="58cb0-177"><a name="BKMK_ConfigureMediationServer"> </a></span></span>

<span data-ttu-id="58cb0-178">Quando una chiamata P2P viene inoltrata a una conferenza PSTN, Skype for business online Conferencing Server invierà un invito a Cloud Connector Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="58cb0-178">When a P2P call is escalated to a PSTN conference, the Skype for Business Online conferencing server will send an invite to the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="58cb0-179">Per garantire che Microsoft 365 o Office 365 sia in grado di instradare correttamente l'invito, è necessario configurare un'impostazione nel tenant online per ogni Mediation Server di Cloud Connector come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="58cb0-179">To ensure that Microsoft 365 or Office 365 can route this invite successfully, you need to configure a setting in your online tenant for each Cloud Connector Mediation Server as follows:</span></span> 
  
1. <span data-ttu-id="58cb0-180">Creare un utente nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="58cb0-180">Create a user in the Microsoft 365 admin center.</span></span> <span data-ttu-id="58cb0-181">Utilizzare qualsiasi nome utente desiderato, ad esempio "MediationServer1".</span><span class="sxs-lookup"><span data-stu-id="58cb0-181">Use any user name you want, such as "MediationServer1."</span></span>
    
    <span data-ttu-id="58cb0-182">Utilizzare il dominio SIP predefinito del connettore Cloud (il primo dominio SIP nel file. ini) come dominio utente.</span><span class="sxs-lookup"><span data-stu-id="58cb0-182">Use the default SIP domain of Cloud Connector (the first SIP domain in the .ini file) as the user domain.</span></span>
    
    <span data-ttu-id="58cb0-183">Tenere presente che l'assegnazione della licenza è necessaria solo per la propagazione degli utenti nella directory di Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="58cb0-183">Please note that license assignment is only required for the user propagation into the Skype for Business online directory.</span></span> <span data-ttu-id="58cb0-184">Assegnare una licenza di Microsoft 365 o Office 365 (ad esempio E5) all'account creato, consentire fino a un'ora per la propagazione delle modifiche, verificare che gli account utente siano stati correttamente provisionati nella directory di Skype for business online eseguendo il cmdlet seguente e quindi rimuovere la licenza da questo account.</span><span class="sxs-lookup"><span data-stu-id="58cb0-184">Assign a Microsoft 365 or Office 365 license (such as E5) to the account you create, allow up to one hour for the changes to propagate,verify the user accounts has been provisioned correctly to the Skype for Business online directory by running following cmdlet, then remove the license from this account.</span></span>
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. <span data-ttu-id="58cb0-185">Avviare una sessione Tenant Azure AD Remote PowerShell utilizzando le credenziali di amministratore globale o utente, quindi eseguire il seguente cmdlet per impostare il reparto per l'account utente di Azure AD configurato nel passaggio 1 su "HybridMediationServer":</span><span class="sxs-lookup"><span data-stu-id="58cb0-185">Start a tenant Azure AD remote PowerShell session using your global or user admin credentials, and then run the following cmdlet to set the department for the Azure AD user account configured in step 1 to "HybridMediationServer":</span></span>

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. <span data-ttu-id="58cb0-186">Avviare una sessione di PowerShell remota di Skype for business con le credenziali di amministratore del tenant di Skype for business, quindi eseguire il seguente cmdlet per impostare l'FQDN di Mediation Server e server perimetrale su tale account utente, sostituendo \< DisplayName \> con il nome visualizzato dell'utente per l'account creato nel passaggio 1:</span><span class="sxs-lookup"><span data-stu-id="58cb0-186">Start a tenant Skype for Business remote PowerShell session using your Skype for Business tenant admin credentials, and then run the following cmdlet to set the Mediation Server and Edge Server FQDN to that user account, replacing \<DisplayName\> with the Display Name of the user for the account you created in step 1:</span></span>
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    <span data-ttu-id="58cb0-187">Per Identity, utilizzare il nome visualizzato dell'account utente creato per questo Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="58cb0-187">For Identity, use the Display Name of the user account you created for this Mediation Server.</span></span>
    
    <span data-ttu-id="58cb0-188">Per *MediationServerFQDN* , utilizzare il nome di dominio completo interno definito per il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="58cb0-188">For  *MediationServerFQDN*  , use the internal FQDN defined for your Mediation Server.</span></span>
    
    <span data-ttu-id="58cb0-189">Per *EdgeServerExternalFQDN* , utilizzare il nome di dominio completo esterno definito per il proxy di accesso Edge Server.</span><span class="sxs-lookup"><span data-stu-id="58cb0-189">For  *EdgeServerExternalFQDN*  , use the external FQDN defined for Edge Server Access Proxy.</span></span> <span data-ttu-id="58cb0-190">Se sono presenti più siti PSTN del connettore Cloud, scegliere il nome di dominio completo del proxy di accesso server perimetrale assegnato al sito in cui si trova il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="58cb0-190">If there are multiple Cloud Connector PSTN sites, choose the Edge Server Access Proxy FQDN assigned to the site where the Mediation Server is located.</span></span>
    
4. <span data-ttu-id="58cb0-191">Se sono presenti più Mediation Server del connettore Cloud (più siti, HA), ripetere i passaggi precedenti per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="58cb0-191">If there are multiple Cloud Connector Mediation Servers (multiple-site, HA), please repeat the previous steps for each of them.</span></span>
    
