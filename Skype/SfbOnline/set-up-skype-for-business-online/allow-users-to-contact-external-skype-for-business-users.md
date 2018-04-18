---
title: Consentire agli utenti di contatti esterni Skype per gli utenti aziendali
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: "Informazioni su come configurare Skype for Business consentire agli utenti di comunicare agli utenti di un'altra organizzazione o consentire a tali contatti esterni. "
ms.openlocfilehash: 533bf45ff1abd0a1127ff54c91ab4c424c7d2df8
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="01e9b-103">Consentire agli utenti di contatti esterni Skype per gli utenti aziendali</span><span class="sxs-lookup"><span data-stu-id="01e9b-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="01e9b-104">Skype per la federazione Business non è disponibile per Office 365 gestito dal 21Vianet e organizzazioni Germania di Office 365.</span><span class="sxs-lookup"><span data-stu-id="01e9b-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="01e9b-105">Utilizzare la procedura descritta in questo articolo, se:</span><span class="sxs-lookup"><span data-stu-id="01e9b-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="01e9b-106">In un'azienda sono presenti utenti in domini diversi.</span><span class="sxs-lookup"><span data-stu-id="01e9b-106">You have users on different domains in your business.</span></span> <span data-ttu-id="01e9b-107">Ad esempio Rob@ContosoEast.com e Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="01e9b-107">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="01e9b-108">Le persone che si desidera all'interno dell'organizzazione di utilizzare Skype for Business per i contatti nelle aziende specifiche esterni all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="01e9b-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
<span data-ttu-id="01e9b-109">-Si desidera avevano in tutto il mondo che utilizza Skype per le aziende siano in grado di trovare e contattare un utente, utilizzando l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="01e9b-109">-You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="01e9b-110">Se si e è possibile utilizzare il valore predefinito Skype per le impostazioni di Business, questo funzionerà automaticamente.</span><span class="sxs-lookup"><span data-stu-id="01e9b-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="01e9b-111">In caso contrario, è necessario assicurarsi che la relativa configurazione non viene bloccata del dominio.</span><span class="sxs-lookup"><span data-stu-id="01e9b-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="01e9b-112">Abilitare le comunicazioni aziendali to business per gli utenti</span><span class="sxs-lookup"><span data-stu-id="01e9b-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="01e9b-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="01e9b-113"></span></span>

<span data-ttu-id="01e9b-114">Per verificare il funzionamento, guardare questo video:</span><span class="sxs-lookup"><span data-stu-id="01e9b-114">To see how this works, watch this video:</span></span>
***
> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=492278f0-6912-47ba-a1d1-00040061cf44&AutoPlayVideo=false]
***

<span data-ttu-id="01e9b-115">In entrambe le organizzazioni a tale scopo, è necessario disporre [delle autorizzazioni di amministratore](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365.</span><span class="sxs-lookup"><span data-stu-id="01e9b-115">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>
  
1. <span data-ttu-id="01e9b-116">Accedere con l'account di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="01e9b-116">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="01e9b-117">In Interfaccia di amministrazione di Office 365, vai a **Interfacce di amministrazione** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="01e9b-117">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="01e9b-119">In **Interfaccia di amministrazione di Skype for Business**, scegli **Organizzazione** > **Comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="01e9b-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
    
4. <span data-ttu-id="01e9b-120">Per configurare la comunicazione con un aziendali specifici o agli utenti in un altro dominio, nella casella a discesa fare clic **su solo per domini consentiti**.</span><span class="sxs-lookup"><span data-stu-id="01e9b-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="01e9b-121">In alternativa, se si desidera consentire le comunicazioni con tutti gli altri partecipanti in tutto il mondo è Apri Skype per i criteri aziendali, scegliere **su ad eccezione dei domini bloccati**.</span><span class="sxs-lookup"><span data-stu-id="01e9b-121">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="01e9b-122">Questo è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="01e9b-122">This is the default setting.</span></span>
    
5. <span data-ttu-id="01e9b-123">In **domini consentiti o bloccati**, scegliere **+** e aggiungere il nome del dominio che si desidera consentire.</span><span class="sxs-lookup"><span data-stu-id="01e9b-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
6. <span data-ttu-id="01e9b-124">Verificare che l'amministratore all'interno dell'organizzazione è la stessa procedura loro **Skype per interfaccia di amministrazione di Business**.</span><span class="sxs-lookup"><span data-stu-id="01e9b-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="01e9b-125">Ad esempio, nel loro elenco **domini consentiti** proprio amministratore deve immettere il dominio per la propria azienda.</span><span class="sxs-lookup"><span data-stu-id="01e9b-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
7. <span data-ttu-id="01e9b-126">Se si utilizza Windows Firewall, Skype for Business apre automaticamente le porte necessarie.</span><span class="sxs-lookup"><span data-stu-id="01e9b-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="01e9b-127">Se l'organizzazione utilizza una soluzione di firewall diverso per limitare i computer della rete di connettersi a Internet, verificare che i computer client siano in grado di accedere ai seguenti [intervalli di indirizzi IP e gli URL di Office 365](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="01e9b-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="01e9b-128">Ciò potrebbe essere necessario aggiungere i nomi FQDN per l'uscita elenco Consenti di firewall o proxy di configurazione dell'infrastruttura: ** \*. api.skype.com**, \* **. users.storage.live.com**e **graph.skype.com**. Per istruzioni su come aprire le porte del firewall, consultare la documentazione fornita con esso.</span><span class="sxs-lookup"><span data-stu-id="01e9b-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**. For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="01e9b-129">Per un elenco di tutte le porte, è necessario aprire, vedere [Office 365 URL e intervalli di indirizzi IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="01e9b-129">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

8. <span data-ttu-id="01e9b-130">Verificare che l'amministratore dell'organizzazione ha inoltre seguita la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="01e9b-130">Make sure that the administrator in the organization has also followed these steps.</span></span>
    
9. <span data-ttu-id="01e9b-p106">**ATTENDI FINO A 24 ORE PRIMA DEL TEST**. Ogni volta che modifichi le impostazioni per le comunicazioni esterne, possono occorrere fino a 24 ore perché le modifiche vengano distribuite su tutti i data center.</span><span class="sxs-lookup"><span data-stu-id="01e9b-p106">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="01e9b-133">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) è possibile consentire agli utenti di cercare e messaggistica immediata con tutti gli utenti Skype, app consumer gratuita!</span><span class="sxs-lookup"><span data-stu-id="01e9b-133">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="01e9b-134">Per ulteriori informazioni, vedere [Skype consente agli utenti aziendali aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="01e9b-134">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="01e9b-135">Test e risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="01e9b-135">Test and troubleshoot</span></span>
<span data-ttu-id="01e9b-136"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="01e9b-136"></span></span>

 <span data-ttu-id="01e9b-137">**Il problema più comune persone verificano durante l'impostazione di comunicazione business to business otterrà le [Office 365 URL e intervalli di indirizzi IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) destro.**</span><span class="sxs-lookup"><span data-stu-id="01e9b-137">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="01e9b-138">Per testare l'installazione, è necessario un contatto in Skype per le aziende che non sono protetti dal firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="01e9b-138">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="01e9b-139">Dopo aver modificato le impostazioni di comunicazione esterna, **ASPETTA FINO A 24 ORE PER TESTARLE**.</span><span class="sxs-lookup"><span data-stu-id="01e9b-139">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="01e9b-140">In Skype per le aziende, cercare il contatto in Skype per le aziende e inviare una richiesta a chat.</span><span class="sxs-lookup"><span data-stu-id="01e9b-140">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="01e9b-141">Se viene visualizzato un messaggio in cui non è stato inviato a causa di politica aziendale, è necessario fare doppio clic di [Office 365 URL e intervalli di indirizzi IP](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="01e9b-141">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="01e9b-142">Chiedere la Skype per contatto commerciale per inviare una richiesta a chat.</span><span class="sxs-lookup"><span data-stu-id="01e9b-142">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="01e9b-143">Se non si ricevono le proprie richieste, il problema è le impostazioni del firewall (presupponendo che hai già confermato che le relative impostazioni di firewall siano corrette).</span><span class="sxs-lookup"><span data-stu-id="01e9b-143">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="01e9b-144">Per verificare se il problema è firewall, è passare a una posizione wifi non protetti dal firewall, ad esempio un Internet café e utilizzare Skype for Business per inviare una richiesta al contatto alla chat.</span><span class="sxs-lookup"><span data-stu-id="01e9b-144">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="01e9b-145">Se il messaggio viene inviato disponibili, ma non quando si è in ufficio, si conosce il problema è firewall.</span><span class="sxs-lookup"><span data-stu-id="01e9b-145">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="01e9b-146">Come individuare altri utenti e sono disponibili durante la connessione con un'altra business</span><span class="sxs-lookup"><span data-stu-id="01e9b-146">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="01e9b-147"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="01e9b-147"></span></span>

<span data-ttu-id="01e9b-148">Dopo aver abilitato le comunicazioni esterne con altri Skype per gli utenti aziendali, gli utenti possano trovare Skype federati per gli utenti aziendali di ricercare il nome di accesso: ad esempio Rob@contoso.com. È necessario quindi aggiungere la persona all'elenco dei contatti.</span><span class="sxs-lookup"><span data-stu-id="01e9b-148">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com. Then they will need to add the person to their list of contacts.</span></span>
  
![Per individuare un utente in un'azienda federata, è necessario cercare l'indirizzo di posta elettronica (si tratta in genere anche il nome di accesso).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="01e9b-150">Suggerimenti sull'impostazione delle comunicazioni con aziende federate</span><span class="sxs-lookup"><span data-stu-id="01e9b-150">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="01e9b-151"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="01e9b-151"></span></span>

- <span data-ttu-id="01e9b-152">Per configurare la federazione tra Skype per 2015 Business e Skype Business online, vedere questo articolo di TechNet: [configurazione della federazione con Skype Business online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span><span class="sxs-lookup"><span data-stu-id="01e9b-152">To configure federation between Skype for Business 2015 and Skype for Business Online, see this TechNet article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="01e9b-153">Per configurare la federazione tra Lync e Skype Business online, vedere questo articolo di TechNet: [Configurazione del supporto per la federazione per un cliente di Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span><span class="sxs-lookup"><span data-stu-id="01e9b-153">To configure federation between Lync and Skype for Business Online, see this TechNet article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/en-us/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="01e9b-154">Quando si comunica tra loro due Skype per gli utenti aziendali di Office 365 in domini separati, possono utilizzare solo Skype per le caratteristiche (ad esempio, le conversazioni video o condivisione del desktop) che vengono attivate in entrambe le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="01e9b-154">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="01e9b-155">Se un Skype per utenti Business all'interno dell'organizzazione è collocato in un In locale o conservazione per controversia legale, le conversazioni di messaggistica immediata tra l'utente e altre Skype per utenti Business o Skype verranno salvate nel **Degli elementi recuperabili** nella propria cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="01e9b-155">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="01e9b-156">Le conversazioni non vengono salvate nella cartella **Cronologia conversazioni** nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="01e9b-156">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="01e9b-157">Disattivare le comunicazioni esterne per specifici utenti</span><span class="sxs-lookup"><span data-stu-id="01e9b-157">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="01e9b-158"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="01e9b-158"></span></span>

<span data-ttu-id="01e9b-159">Dopo aver abilitato le comunicazioni esterne per un'intera azienda, è possibile disattivare lo per solo a utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="01e9b-159">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="01e9b-160">Accedere con l'account di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="01e9b-160">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="01e9b-161">Nell'interfaccia di amministrazione di Office 365 accedere agli **utenti** > **utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="01e9b-161">In the Office 365 admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="01e9b-162">Nell'elenco di utenti, scegliere l'utente e quindi, in **Altre impostazioni**, fare clic su **Modifica Skype per le proprietà di Business**.</span><span class="sxs-lookup"><span data-stu-id="01e9b-162">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Scegliere Skype per le aziende](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="01e9b-164">**Skype per interfaccia di amministrazione di Business**, scegliere **comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="01e9b-164">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="01e9b-165">Nella pagina **Opzioni di** tutte le scelte verrà selezionate.</span><span class="sxs-lookup"><span data-stu-id="01e9b-165">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="01e9b-166">Deselezionare le comunicazioni da disattivare.</span><span class="sxs-lookup"><span data-stu-id="01e9b-166">Clear the communications you want to disable.</span></span> <span data-ttu-id="01e9b-167">Nell'immagine seguente viene illustrato che Jakob saranno in grado di comunicare con utenti di altre aziende attendibili, ma non con altri utenti Skype.</span><span class="sxs-lookup"><span data-stu-id="01e9b-167">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Scegliere contatti esterni](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="01e9b-169">Scegliere **Save**.</span><span class="sxs-lookup"><span data-stu-id="01e9b-169">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="01e9b-170">Potrebbe essere necessario attendere fino a 24 ore rendere effettive le modifiche.</span><span class="sxs-lookup"><span data-stu-id="01e9b-170">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="01e9b-171">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="01e9b-171">Related topics</span></span>
<span data-ttu-id="01e9b-172"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="01e9b-172"></span></span>

[<span data-ttu-id="01e9b-173">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="01e9b-173">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="01e9b-174">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="01e9b-174">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
