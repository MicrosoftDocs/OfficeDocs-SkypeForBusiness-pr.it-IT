---
title: Permettere agli utenti di contattare utenti Skype for Business esterni
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: "Scopri come configurare Skype for business per consentire agli utenti di parlare con gli utenti di un'altra organizzazione o di consentire loro di accedere ai contatti esterni. "
ms.openlocfilehash: 394613e3137c65e814cc08dd898ec797d560d1c6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010939"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="4241b-103">Permettere agli utenti di contattare utenti Skype for Business esterni</span><span class="sxs-lookup"><span data-stu-id="4241b-103">Allow users to contact external Skype for Business users</span></span>

> [!NOTE]
> <span data-ttu-id="4241b-104">La Federazione di Skype for business non è disponibile per Office 365 gestito da 21Vianet e dalle organizzazioni di Office 365 Germany.</span><span class="sxs-lookup"><span data-stu-id="4241b-104">Skype for Business federation isn't available to Office 365 operated by 21Vianet and Office 365 Germany organizations.</span></span> 
  
<span data-ttu-id="4241b-105">Seguire i passaggi di questo articolo quando:</span><span class="sxs-lookup"><span data-stu-id="4241b-105">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="4241b-106">Si hanno utenti su domini diversi nell'azienda.</span><span class="sxs-lookup"><span data-stu-id="4241b-106">You have users on different domains in your business.</span></span> <span data-ttu-id="4241b-107">Ad esempio, Rob@ContosoEast.com e Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="4241b-107">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>
    
- <span data-ttu-id="4241b-108">Si vuole che gli utenti dell'organizzazione usino Skype for business per contattare persone di aziende specifiche all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4241b-108">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>
    
- <span data-ttu-id="4241b-109">Si vuole che chiunque altro al mondo usi Skype for business sia in grado di trovare e contattare l'utente, usando l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4241b-109">You want anyone else in the world who uses Skype for Business to be able to find and contact you, using your email address.</span></span> <span data-ttu-id="4241b-110">Se si usano le impostazioni predefinite di Skype for business, questo funzionerà automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4241b-110">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="4241b-111">In caso contrario, è necessario assicurarsi che la configurazione non blocchi il dominio.</span><span class="sxs-lookup"><span data-stu-id="4241b-111">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>
    
## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="4241b-112">Abilitare le comunicazioni business-to-business per gli utenti</span><span class="sxs-lookup"><span data-stu-id="4241b-112">Enable business-to-business communications for your users</span></span>
<span data-ttu-id="4241b-113"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="4241b-113"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="4241b-114">Per eseguire questa operazione, è necessario disporre [delle autorizzazioni di amministratore](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in entrambe le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4241b-114">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Office 365 in both organizations to do this.</span></span>

<span data-ttu-id="4241b-115">![Icona che mostra il logo](../images/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di teams**</span><span class="sxs-lookup"><span data-stu-id="4241b-115">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="4241b-116">Accedere con l'account di amministratore di Office 365.</span><span class="sxs-lookup"><span data-stu-id="4241b-116">Sign in with your Office 365 admin account.</span></span> 
    
2. <span data-ttu-id="4241b-117">Nell'interfaccia di amministrazione accedere a**Teams**di interfaccia di **Amministrazione** > .</span><span class="sxs-lookup"><span data-stu-id="4241b-117">In the admin center, go to **Admin Centers** > **Teams**.</span></span>
    
    ![Scegliere l'amministratore di teams.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="4241b-119">Nel **centro teams**scegliere **Skype** > **legacy Portal** 
 ![scegliere il portale legacy di SFB.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="4241b-119">In the **Teams center**, choose **Skype** > **Legacy Portal** 
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>
 
4. <span data-ttu-id="4241b-120">Nell'interfaccia di **amministrazione di Skype for business** scegli \*\*\*\* > **comunicazioni esterne**dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4241b-120">In the **Skype for Business admin center** , choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="4241b-121">Per configurare la comunicazione con un'azienda specifica o con utenti di un altro dominio, nella casella a discesa scegliere **solo per i domini consentiti**.</span><span class="sxs-lookup"><span data-stu-id="4241b-121">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>
    
    <span data-ttu-id="4241b-122">In alternativa, se vuoi abilitare la comunicazione con tutti gli altri utenti del mondo che hanno aperto i criteri di Skype for business, scegli attivato **eccetto i domini bloccati**.</span><span class="sxs-lookup"><span data-stu-id="4241b-122">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="4241b-123">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4241b-123">This is the default setting.</span></span>
    
6. <span data-ttu-id="4241b-124">In **domini bloccati o consentiti**scegliere **+** e aggiungere il nome del dominio che si vuole consentire.</span><span class="sxs-lookup"><span data-stu-id="4241b-124">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>
    
7. <span data-ttu-id="4241b-125">Verificare che l'amministratore dell'altra organizzazione effettui gli stessi passaggi nell'interfaccia di **amministrazione di Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="4241b-125">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="4241b-126">Nell'elenco dei **domini consentiti** , ad esempio, l'amministratore deve immettere il dominio per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="4241b-126">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>
    
8. <span data-ttu-id="4241b-127">Se si usa Windows Firewall, Skype for Business apre automaticamente le porte necessarie.</span><span class="sxs-lookup"><span data-stu-id="4241b-127">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="4241b-128">Se l'organizzazione usa una soluzione firewall diversa per limitare la connessione a Internet da parte dei computer della rete, assicurarsi che i computer client siano in grado di accedere agli [URL e agli intervalli di indirizzi IP di Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)seguenti.</span><span class="sxs-lookup"><span data-stu-id="4241b-128">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="4241b-129">Potrebbe essere necessario aggiungere i nomi di dominio completi all'elenco Consenti in uscita nella configurazione del firewall o dell'infrastruttura proxy: \*\* \*. API.Skype.com\*\*, \* **. Users.storage.Live.com**e **Graph.Skype.com**.</span><span class="sxs-lookup"><span data-stu-id="4241b-129">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="4241b-130">Per istruzioni su come aprire queste porte nel firewall, controllare la documentazione fornita con esso.</span><span class="sxs-lookup"><span data-stu-id="4241b-130">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>
    
    <span data-ttu-id="4241b-131">Per un elenco di tutte le porte che è necessario aprire, vedere [URL e intervalli di indirizzi IP di Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="4241b-131">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="4241b-132">Verificare che anche l'amministratore dell'organizzazione abbia seguito questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="4241b-132">Make sure that the administrator in the organization has also followed these steps.</span></span>
    
10. <span data-ttu-id="4241b-133">**Attendere fino a 24 ore per eseguire il test**.</span><span class="sxs-lookup"><span data-stu-id="4241b-133">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="4241b-134">Ogni volta che si modificano le impostazioni di comunicazione esterna, è possibile che le modifiche vengano inserite in tutti i centri dati fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="4241b-134">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
<span data-ttu-id="4241b-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) è possibile consentire agli utenti di cercare e inviare messaggi istantanei con tutti coloro che usano Skype, l'app consumer gratuita.</span><span class="sxs-lookup"><span data-stu-id="4241b-135">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="4241b-136">Per altre informazioni, vedere [consentire agli utenti di Skype for business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="4241b-136">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="4241b-137">Test e risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="4241b-137">Test and troubleshoot</span></span>
<span data-ttu-id="4241b-138"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="4241b-138"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="4241b-139">**Il problema più comune che si verifica quando si configura la comunicazione business-to-business è ottenere gli [URL di Office 365 e gli intervalli di indirizzi IP](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) giusti.**</span><span class="sxs-lookup"><span data-stu-id="4241b-139">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="4241b-140">Per testare la configurazione, è necessario un contatto in Skype for business che non si trova dietro il firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="4241b-140">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="4241b-141">Dopo aver modificato le impostazioni di comunicazione esterna, **attendere fino a 24 ore per**eseguire il test.</span><span class="sxs-lookup"><span data-stu-id="4241b-141">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="4241b-142">In Skype for business cerca il tuo contatto in Skype for business e invia una richiesta di chat.</span><span class="sxs-lookup"><span data-stu-id="4241b-142">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>
    
    <span data-ttu-id="4241b-143">Se viene visualizzato un messaggio che non può essere inviato a causa di criteri aziendali, è necessario effettuare un doppio controllo sugli [URL e gli intervalli di indirizzi IP di Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="4241b-143">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>
    
3. <span data-ttu-id="4241b-144">Chiedere al contatto Skype for business di inviare una richiesta di chat.</span><span class="sxs-lookup"><span data-stu-id="4241b-144">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="4241b-145">Se non si riceve la richiesta, il problema è che le impostazioni del firewall (presumendo che abbiano già confermato le impostazioni del firewall siano corrette).</span><span class="sxs-lookup"><span data-stu-id="4241b-145">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>
    
4. <span data-ttu-id="4241b-146">Un altro modo per verificare se il problema è il firewall consiste nell'accedere a una posizione WiFi non dietro il firewall, ad esempio un coffee shop, e usare Skype for business per inviare una richiesta al contatto per la chat.</span><span class="sxs-lookup"><span data-stu-id="4241b-146">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="4241b-147">Se il messaggio passa da lì, ma non quando si è al lavoro, si sa che il problema è il firewall.</span><span class="sxs-lookup"><span data-stu-id="4241b-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="4241b-148">Come trovare altre persone e trovarle durante la connessione con un'altra azienda</span><span class="sxs-lookup"><span data-stu-id="4241b-148">How to find others, and be found, when connecting with another business</span></span>
<span data-ttu-id="4241b-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="4241b-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="4241b-150">Dopo aver abilitato le comunicazioni esterne con altri utenti di Skype for business, gli utenti possono trovare gli utenti di Skype for business federati per cercare il nome di accesso: ad esempio, Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4241b-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in name: for example, Rob@contoso.com.</span></span> <span data-ttu-id="4241b-151">Sarà quindi necessario aggiungere la persona al proprio elenco di contatti.</span><span class="sxs-lookup"><span data-stu-id="4241b-151">Then they will need to add the person to their list of contacts.</span></span>
  
![Per trovare un utente in un'azienda federata, è necessario cercare l'indirizzo di posta elettronica (in genere è anche il nome di accesso).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="4241b-153">Suggerimenti per la configurazione delle comunicazioni con le aziende federate</span><span class="sxs-lookup"><span data-stu-id="4241b-153">Tips on setting up communications with federated businesses</span></span>
<span data-ttu-id="4241b-154"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="4241b-154"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="4241b-155">Per configurare la Federazione tra Skype for business 2015 e Skype for business online, vedere questo articolo: [configurare la Federazione con Skype for business online](https://technet.microsoft.com/library/jj205126.aspx).</span><span class="sxs-lookup"><span data-stu-id="4241b-155">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/library/jj205126.aspx).</span></span>
    
- <span data-ttu-id="4241b-156">Per configurare la Federazione tra Lync e Skype for business online, vedere questo articolo: [configurazione del supporto federativo per un cliente di Lync Online](https://technet.microsoft.com/library/hh202193.aspx).</span><span class="sxs-lookup"><span data-stu-id="4241b-156">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/library/hh202193.aspx).</span></span>
    
- <span data-ttu-id="4241b-157">Quando due utenti di Skype for business in Office 365 comunicano tra loro su domini separati, possono usare solo le caratteristiche di Skype for business (ad esempio, conversazioni video o condivisione desktop) attivate in entrambe le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4241b-157">When two Skype for Business users in Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>
    
- <span data-ttu-id="4241b-158">Se un utente di Skype for business nell'organizzazione viene inserito in un blocco sul posto o in una controversia legale, le conversazioni ISTANTANEe tra l'utente e gli altri utenti di Skype for business o Skype verranno salvate in **elementi ripristinabili** nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="4241b-158">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="4241b-159">Le conversazioni non vengono salvate nella cartella **Cronologia conversazioni** nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="4241b-159">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>
    
## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="4241b-160">Disattivare le comunicazioni esterne per individui specifici</span><span class="sxs-lookup"><span data-stu-id="4241b-160">Turn off external communication for specific individuals</span></span>
<span data-ttu-id="4241b-161"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="4241b-161"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="4241b-162">Dopo aver abilitato le comunicazioni esterne per l'intera azienda, è possibile disattivarle solo per singoli utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="4241b-162">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="4241b-163">Accedere con l'account di amministratore di Office 365.</span><span class="sxs-lookup"><span data-stu-id="4241b-163">Sign in with your Office 365 admin account.</span></span>
    
2. <span data-ttu-id="4241b-164">Nell'interfaccia di amministrazione, passa a utenti**attivi**degli **utenti** > .</span><span class="sxs-lookup"><span data-stu-id="4241b-164">In the admin center, go to **Users** > **Active users**.</span></span>
    
3. <span data-ttu-id="4241b-165">Nell'elenco degli utenti scegliere l'utente e quindi, in **altre impostazioni**, fare clic su **modifica proprietà Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="4241b-165">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>
    
    ![Scegliere Skype for business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="4241b-167">Nell'interfaccia di **amministrazione di Skype for business**scegli **comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="4241b-167">In the **Skype for Business admin center**, choose **External communications**.</span></span>
    
    <span data-ttu-id="4241b-168">Nella pagina **Opzioni** verranno selezionate tutte le scelte.</span><span class="sxs-lookup"><span data-stu-id="4241b-168">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="4241b-169">Deselezionare le comunicazioni che si desidera disabilitare.</span><span class="sxs-lookup"><span data-stu-id="4241b-169">Clear the communications you want to disable.</span></span> <span data-ttu-id="4241b-170">L'immagine seguente mostra che Jakob sarà in grado di comunicare con persone di altre aziende attendibili, ma non con altri utenti Skype.</span><span class="sxs-lookup"><span data-stu-id="4241b-170">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>
    
    ![Scegliere contatti esterni](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="4241b-172">Scegliere **Save**.</span><span class="sxs-lookup"><span data-stu-id="4241b-172">Choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4241b-173">Potrebbe essere necessario attendere fino a 24 ore affinché le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="4241b-173">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a><span data-ttu-id="4241b-174">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4241b-174">Related topics</span></span>
<span data-ttu-id="4241b-175"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="4241b-175"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="4241b-176">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="4241b-176">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="4241b-177">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="4241b-177">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
