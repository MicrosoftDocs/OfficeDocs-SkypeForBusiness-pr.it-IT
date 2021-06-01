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
description: "Informazioni su come configurare le Skype for Business per consentire agli utenti di parlare con utenti di un'altra organizzazione o per consentire ai contatti esterni di parlare con loro. "
ms.openlocfilehash: 3b4aeb2b40cf34579d3d584a50664550cd34038c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240004"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="1eb9b-103">Permettere agli utenti di contattare utenti Skype for Business esterni</span><span class="sxs-lookup"><span data-stu-id="1eb9b-103">Allow users to contact external Skype for Business users</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
  
<span data-ttu-id="1eb9b-104">Seguire la procedura descritta in questo articolo quando:</span><span class="sxs-lookup"><span data-stu-id="1eb9b-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="1eb9b-105">Si hanno utenti di domini diversi nell'azienda.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-105">You have users on different domains in your business.</span></span> <span data-ttu-id="1eb9b-106">Ad esempio, Rob@ContosoEast.com e Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>

- <span data-ttu-id="1eb9b-107">Si vuole che le persone dell'organizzazione usino le Skype for Business per contattare persone di aziende specifiche esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-107">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="1eb9b-108">Si vuole che chiunque altro al mondo che usa Skype for Business possa trovare e contattare l'utente usando il proprio indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-108">You want anyone else in the world who uses Skype for Business to be able to find and contact you using your email address.</span></span> <span data-ttu-id="1eb9b-109">Se l'utente e l'utente usano le impostazioni Skype for Business predefinite, questa funzionerà automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-109">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="1eb9b-110">In caso contrario, è necessario assicurarsi che la configurazione non blocchi il dominio.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>

## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="1eb9b-111">Abilitare le comunicazioni business-to-business per gli utenti</span><span class="sxs-lookup"><span data-stu-id="1eb9b-111">Enable business-to-business communications for your users</span></span>

<span data-ttu-id="1eb9b-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="1eb9b-112"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="1eb9b-113">Per eseguire [questa](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) comunicazione, è Microsoft 365 o Office 365 autorizzazioni di amministratore in entrambe le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this communication.</span></span>

<span data-ttu-id="1eb9b-114">![Icona che mostra il logo Microsoft Teams ](../images/teams-logo-30x30.png) **con l'interfaccia Teams di amministrazione**</span><span class="sxs-lookup"><span data-stu-id="1eb9b-114">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="1eb9b-115">Accedere con l'account Microsoft 365 o Office 365 amministratore.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-115">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="1eb9b-116">Nell'interfaccia di amministrazione passare a **Interfaccia di amministrazione**  >  **Teams**.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-116">In the admin center, go to **Admin Centers** > **Teams**.</span></span>

    ![Scegliere l'Teams amministratore.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="1eb9b-118">Nel centro **Teams scegliere** **Skype** > **portale legacy** 
  ![ Scegliere il portale legacy SfB.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="1eb9b-118">In the **Teams center**, choose **Skype** > **Legacy Portal**
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>

4. <span data-ttu-id="1eb9b-119">Nell'**interfaccia di amministrazione di Skype for Business** scegliere **Organizzazione** > **Comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="1eb9b-120">Per configurare la comunicazione con una specifica azienda o con utenti in un altro dominio, nella casella di riepilogo a discesa scegliere **Attiva solo per i domini consentiti**.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="1eb9b-121">Oppure, se si vuole abilitare la comunicazione con tutti gli altri utenti del mondo che hanno criteri di Skype for Business, scegliere Attivato ad eccezione **dei domini bloccati.**</span><span class="sxs-lookup"><span data-stu-id="1eb9b-121">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="1eb9b-122">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-122">This is the default setting.</span></span>

6. <span data-ttu-id="1eb9b-123">In **Domini bloccati o consentiti** scegliere e aggiungere il nome del dominio da **+** consentire.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>

7. <span data-ttu-id="1eb9b-124">Assicurarsi che l'amministratore dell'altra organizzazione eseerciti gli stessi passaggi **nell'interfaccia Skype for Business di amministrazione.**</span><span class="sxs-lookup"><span data-stu-id="1eb9b-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="1eb9b-125">Ad esempio, **nell'elenco dei domini consentiti,** l'amministratore deve immettere il dominio per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

8. <span data-ttu-id="1eb9b-126">Se si usa firewall Windows, Skype for Business automaticamente le porte necessarie.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>

    <span data-ttu-id="1eb9b-127">Se l'organizzazione usa una soluzione firewall diversa per limitare la connessione a Internet dei computer della rete, verificare che i computer client siano in grado di accedere agli URL e agli intervalli di indirizzi [IP](/microsoftteams/office-365-urls-ip-address-ranges)Office 365 seguenti.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="1eb9b-128">Potrebbe essere necessario aggiungere gli FQDN all'elenco di indirizzi consentiti in uscita nella configurazione del firewall o dell'infrastruttura proxy: **\* .api.skype.com,** \* *_.users.storage.live.com_* e **graph.skype.com**.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \**_.users.storage.live.com_*, and **graph.skype.com**.</span></span> <span data-ttu-id="1eb9b-129">Per istruzioni su come aprire queste porte nel firewall, consultare la documentazione fornita con essa.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>

    <span data-ttu-id="1eb9b-130">Per un elenco di tutte le porte da aprire, vedere Office 365 [URL e intervalli di](/microsoftteams/office-365-urls-ip-address-ranges)indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="1eb9b-131">Assicurarsi che anche l'amministratore dell'organizzazione abbia seguito questa procedura.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-131">Make sure that the administrator in the organization has also followed these steps.</span></span>

10. <span data-ttu-id="1eb9b-132">**ATTENDERE FINO A 24 ORE PER TESTARE**.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-132">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="1eb9b-133">Quando si modificano le impostazioni delle comunicazioni esterne, possono essere necessarie fino a 24 ore prima che le modifiche possano essere popolate in tutti i data center.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-133">When you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

<span data-ttu-id="1eb9b-134">![](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png)Skype È possibile consentire agli utenti di cercare e messaggistica istantanea con tutti gli utenti che Skype, l'app gratuita consumer.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="1eb9b-135">Per altre informazioni, vedere [Consentire agli Skype for Business di aggiungere Skype contatti.](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="1eb9b-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="1eb9b-136">Testare e risolvere i problemi</span><span class="sxs-lookup"><span data-stu-id="1eb9b-136">Test and troubleshoot</span></span>

<span data-ttu-id="1eb9b-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="1eb9b-137"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="1eb9b-138">**Il problema più comune che le persone riscontrano quando si configurano le comunicazioni business-to-business è ottenere gli URL Office 365 e gli intervalli di indirizzi [IP.](/microsoftteams/office-365-urls-ip-address-ranges)**</span><span class="sxs-lookup"><span data-stu-id="1eb9b-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="1eb9b-139">Per testare la configurazione, è necessario un contatto Skype for Business che non sia dietro il firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="1eb9b-140">Dopo aver modificato le impostazioni delle comunicazioni esterne, **ATTENDERE FINO A 24 ORE PER VERIFICARE**.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>

2. <span data-ttu-id="1eb9b-141">In Skype for Business, cercare il contatto in Skype for Business e inviare una richiesta di chat.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>

    <span data-ttu-id="1eb9b-142">Se viene visualizzato un messaggio che indica che non è stato possibile inviare il messaggio a causa dei criteri aziendali, è necessario verificare gli URL e gli intervalli di indirizzi IP Office 365 indirizzi [IP.](/microsoftteams/office-365-urls-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="1eb9b-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

3. <span data-ttu-id="1eb9b-143">Chiedi al tuo Skype for Business contatto di inviarti una richiesta di chat.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-143">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="1eb9b-144">Se non si riceve la richiesta, il problema sono le impostazioni del firewall, supponendo di aver già verificato che le impostazioni firewall dell'altra organizzazione siano corrette.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-144">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="1eb9b-145">Un altro modo per verificare se il problema è il firewall è passare a una posizione WiFi non dietro il firewall, ad esempio una caffetteria.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall, such as a coffee shop.</span></span> <span data-ttu-id="1eb9b-146">Usare Skype for Business per inviare una richiesta al contatto per chattare.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-146">Use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="1eb9b-147">Se il messaggio viene inviato, ma non al lavoro, il problema è il firewall.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="1eb9b-148">Come trovare altri utenti ed essere trovati quando ci si connette con un'altra azienda</span><span class="sxs-lookup"><span data-stu-id="1eb9b-148">How to find others, and be found, when connecting with another business</span></span>

<span data-ttu-id="1eb9b-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="1eb9b-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="1eb9b-150">Dopo aver abilitato la comunicazione esterna con altri Skype for Business utenti, gli utenti possono trovare utenti Skype for Business federati cercando i nomi di accesso.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in names.</span></span> <span data-ttu-id="1eb9b-151">Un esempio è Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-151">An example is Rob@contoso.com.</span></span> <span data-ttu-id="1eb9b-152">Dovrà quindi aggiungere la persona all'elenco dei contatti.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-152">Then they will need to add the person to their list of contacts.</span></span>
  
![Per trovare un utente in un'azienda federata, è necessario cercarne l'indirizzo di posta elettronica ,in genere anche il nome di accesso.](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="1eb9b-154">Suggerimenti sulla configurazione delle comunicazioni con le aziende federate</span><span class="sxs-lookup"><span data-stu-id="1eb9b-154">Tips on setting up communications with federated businesses</span></span>

<span data-ttu-id="1eb9b-155"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="1eb9b-155"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="1eb9b-156">Per configurare la federazione tra Skype for Business 2015 e Skype for Business Online, vedere questo articolo: Configurare la federazione [con Skype for Business Online.](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="1eb9b-156">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>

- <span data-ttu-id="1eb9b-157">Per configurare la federazione tra Lync e Skype for Business Online, vedere questo articolo: Configurazione del supporto della federazione [per un cliente di Lync Online.](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)</span><span class="sxs-lookup"><span data-stu-id="1eb9b-157">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer).</span></span>

- <span data-ttu-id="1eb9b-158">Quando due utenti di Skype for Business in Microsoft 365 o Office 365 comunicano tra loro in domini separati, possono usare solo le funzionalità di Skype for Business ,ad esempio le conversazioni video o la condivisione desktop, attivate in entrambe le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-158">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>

- <span data-ttu-id="1eb9b-159">Se un utente Skype for Business dell'organizzazione viene abilitato a un blocco In-Place o per controversia legale, tutte le conversazioni istantanee tra tale utente e altri utenti di Skype for Business o Skype verranno salvate **in** Elementi ripristinabili nella propria cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-159">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="1eb9b-160">Queste conversazioni non vengono salvate nella cartella **Cronologia** conversazioni della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-160">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>

## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="1eb9b-161">Disattivare le comunicazioni esterne per utenti specifici</span><span class="sxs-lookup"><span data-stu-id="1eb9b-161">Turn off external communication for specific individuals</span></span>

<span data-ttu-id="1eb9b-162"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="1eb9b-162"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="1eb9b-163">Dopo aver abilitato la comunicazione esterna per l'intera azienda, è possibile disattivarla solo per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-163">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="1eb9b-164">Accedere con l'account Microsoft 365 o Office 365 amministratore.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-164">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="1eb9b-165">Nell'interfaccia di amministrazione passare a **Utenti**  >  **utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-165">In the admin center, go to **Users** > **Active users**.</span></span>

3. <span data-ttu-id="1eb9b-166">Nell'elenco degli utenti scegliere l'utente e quindi, in Altre Impostazioni **,** fare clic su Modifica Skype for Business **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-166">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>

    ![Scegliere Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="1eb9b-168">**Nell'Skype for Business di amministrazione scegliere** Comunicazioni **esterne.**</span><span class="sxs-lookup"><span data-stu-id="1eb9b-168">In the **Skype for Business admin center**, choose **External communications**.</span></span>

    <span data-ttu-id="1eb9b-169">Nella pagina **Opzioni** verranno selezionate tutte le opzioni.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-169">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="1eb9b-170">Deselezionare le comunicazioni da disabilitare.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-170">Clear the communications you want to disable.</span></span> <span data-ttu-id="1eb9b-171">L'immagine seguente mostra che Jakob sarà in grado di comunicare con persone di altre aziende attendibili, ma non con altri Skype utenti.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-171">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>

    ![Scegliere Contatti esterni](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="1eb9b-173">Scegliere **Save**.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-173">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="1eb9b-174">Potrebbe essere necessario attendere fino a 24 ore per l'applicazione delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="1eb9b-174">You may have to wait for up to 24 hours for your changes to take effect.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="1eb9b-175">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1eb9b-175">Related topics</span></span>

<span data-ttu-id="1eb9b-176"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="1eb9b-176"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="1eb9b-177">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="1eb9b-177">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="1eb9b-178">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="1eb9b-178">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
