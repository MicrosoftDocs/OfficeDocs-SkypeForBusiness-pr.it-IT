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
description: "Scopri come configurare Skype for Business in modo che gli utenti parlino con gli utenti di un'altra organizzazione o che i contatti esterni parlino con loro. "
ms.openlocfilehash: d9b3be381432fa95962df7a5a58ea9d81e223fc4
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625052"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a><span data-ttu-id="e3e30-103">Permettere agli utenti di contattare utenti Skype for Business esterni</span><span class="sxs-lookup"><span data-stu-id="e3e30-103">Allow users to contact external Skype for Business users</span></span>
  
<span data-ttu-id="e3e30-104">Seguire i passaggi descritti in questo articolo quando:</span><span class="sxs-lookup"><span data-stu-id="e3e30-104">Use the steps in this article when:</span></span>
  
- <span data-ttu-id="e3e30-105">Gli utenti dell'azienda hanno utenti con domini diversi.</span><span class="sxs-lookup"><span data-stu-id="e3e30-105">You have users on different domains in your business.</span></span> <span data-ttu-id="e3e30-106">Ad esempio, Rob@ContosoEast.com e Ann@ContosoWest.com.</span><span class="sxs-lookup"><span data-stu-id="e3e30-106">For example, Rob@ContosoEast.com and Ann@ContosoWest.com.</span></span>

- <span data-ttu-id="e3e30-107">Si desidera che le persone dell'organizzazione usino Skype for Business per contattare persone di aziende specifiche all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e3e30-107">You want the people in your organization to use Skype for Business to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="e3e30-108">Si desidera che chiunque altro nel mondo che usa Skype for Business possa trovarti e contattarti utilizzando il tuo indirizzo e-mail.</span><span class="sxs-lookup"><span data-stu-id="e3e30-108">You want anyone else in the world who uses Skype for Business to be able to find and contact you using your email address.</span></span> <span data-ttu-id="e3e30-109">Se tu e loro usate le impostazioni predefinite di Skype for Business, questa funzionerà automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e3e30-109">If you and they use the default Skype for Business settings, this will work automatically.</span></span> <span data-ttu-id="e3e30-110">In caso contrario, devono verificare che la loro configurazione non blocchi il dominio.</span><span class="sxs-lookup"><span data-stu-id="e3e30-110">If they don't, then they need to make sure their configuration isn't blocking your domain.</span></span>

## <a name="enable-business-to-business-communications-for-your-users"></a><span data-ttu-id="e3e30-111">Abilitare le comunicazioni business-to-business per gli utenti</span><span class="sxs-lookup"><span data-stu-id="e3e30-111">Enable business-to-business communications for your users</span></span>

<span data-ttu-id="e3e30-112"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="e3e30-112"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="e3e30-113">Per eseguire questa [comunicazione,](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) è necessario avere autorizzazioni di amministratore in Microsoft 365 o Office 365 in entrambe le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="e3e30-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) in Microsoft 365 or Office 365 in both organizations to do this communication.</span></span>

<span data-ttu-id="e3e30-114">![Icona che mostra il logo di Microsoft Teams ](../images/teams-logo-30x30.png) **tramite l'interfaccia di amministrazione di Teams**</span><span class="sxs-lookup"><span data-stu-id="e3e30-114">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Teams admin center**</span></span>
  
1. <span data-ttu-id="e3e30-115">Accedere con l'account di amministratore di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3e30-115">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="e3e30-116">Nell'interfaccia di amministrazione passare a **Team delle interfaccia di**  >  **amministrazione.**</span><span class="sxs-lookup"><span data-stu-id="e3e30-116">In the admin center, go to **Admin Centers** > **Teams**.</span></span>

    ![Scegliere l'amministratore di Teams.](../images/MS-Teams-Admin.png)
  
3. <span data-ttu-id="e3e30-118">Nel centro **Teams,** scegli **il portale legacy di** >  
  ![ Skype, scegli il portale legacy di SfB.](../images/SFBlegacy-size65.png)</span><span class="sxs-lookup"><span data-stu-id="e3e30-118">In the **Teams center**, choose **Skype** > **Legacy Portal**
![Choose the SfB Legacy Portal.](../images/SFBlegacy-size65.png)</span></span>

4. <span data-ttu-id="e3e30-119">Nell'**interfaccia di amministrazione di Skype for Business** scegliere **Organizzazione** > **Comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="e3e30-119">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span>
5. <span data-ttu-id="e3e30-120">Per configurare la comunicazione con una specifica azienda o con utenti in un altro dominio, nella casella di riepilogo a discesa scegliere **Attiva solo per i domini consentiti**.</span><span class="sxs-lookup"><span data-stu-id="e3e30-120">To set up communication with a specific business or with users in another domain, in the drop-down box, choose **On only for allowed domains**.</span></span>

    <span data-ttu-id="e3e30-121">OPPURE, se desideri consentire la comunicazione con chiunque altro nel mondo abbia politiche di Skype for Business, scegli Attivato ad eccezione **dei domini bloccati.**</span><span class="sxs-lookup"><span data-stu-id="e3e30-121">OR, if you want to enable communication with everyone else in the world who has open Skype for Business policies, choose **On except for blocked domains**.</span></span> <span data-ttu-id="e3e30-122">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e3e30-122">This is the default setting.</span></span>

6. <span data-ttu-id="e3e30-123">In **Domini bloccati o consentiti** scegliere e aggiungere il nome del dominio che si vuole **+** consentire.</span><span class="sxs-lookup"><span data-stu-id="e3e30-123">Under **Blocked or allowed domains**, choose **+** and add the name of the domain you want to allow.</span></span>

7. <span data-ttu-id="e3e30-124">Assicurati che l'amministratore dell'altra organizzazione eserciti questi stessi passaggi nell'interfaccia **di amministrazione di Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="e3e30-124">Make sure the admin in the other organization does these same steps in their **Skype for Business admin center**.</span></span> <span data-ttu-id="e3e30-125">Ad esempio, **nell'elenco dei domini consentiti,** l'amministratore deve immettere il dominio per l'azienda.</span><span class="sxs-lookup"><span data-stu-id="e3e30-125">For example, in their **allowed domains** list, their admin needs to enter the domain for your business.</span></span>

8. <span data-ttu-id="e3e30-126">Se si usa Windows Firewall, Skype for Business apre automaticamente le porte richieste.</span><span class="sxs-lookup"><span data-stu-id="e3e30-126">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>

    <span data-ttu-id="e3e30-127">Se l'organizzazione usa una soluzione firewall diversa per limitare la connessione a Internet dei computer della rete, verificare che i computer client siano in grado di accedere ai seguenti URL e intervalli di indirizzi IP per [Office 365.](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="e3e30-127">If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span> <span data-ttu-id="e3e30-128">A questo scopo può essere necessario aggiungere gli FQDN all'elenco degli elementi consentiti in uscita nella configurazione dell'infrastruttura del firewall o del proxy: con estensione **\* api.skype.com,** \* **users.storage.live.com** e **graph.skype.com.**</span><span class="sxs-lookup"><span data-stu-id="e3e30-128">This may require adding the FQDNs to the outbound allow list in your firewall or proxy infrastructure configuration: **\*.api.skype.com**, \***.users.storage.live.com**, and **graph.skype.com**.</span></span> <span data-ttu-id="e3e30-129">Per istruzioni su come aprire queste porte nel firewall, consultare la documentazione fornita con il firewall.</span><span class="sxs-lookup"><span data-stu-id="e3e30-129">For instructions on how to open these ports in your firewall, check the documentation that came with it.</span></span>

    <span data-ttu-id="e3e30-130">Per un elenco di tutte le porte che è necessario aprire, vedere URL e intervalli di indirizzi [IP per Office 365.](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="e3e30-130">For a list of all ports you need to open, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

9. <span data-ttu-id="e3e30-131">Assicurarsi che anche l'amministratore dell'organizzazione abbia seguito questa procedura.</span><span class="sxs-lookup"><span data-stu-id="e3e30-131">Make sure that the administrator in the organization has also followed these steps.</span></span>

10. <span data-ttu-id="e3e30-132">**ATTENDI FINO A 24 ORE PER IL TEST.**</span><span class="sxs-lookup"><span data-stu-id="e3e30-132">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="e3e30-133">Quando si modificano le impostazioni per le comunicazioni esterne, possono essere necessarie fino a 24 ore prima che le modifiche verranno popolate in tutti i data center.</span><span class="sxs-lookup"><span data-stu-id="e3e30-133">When you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>

<span data-ttu-id="e3e30-134">![Skype È possibile consentire agli utenti di cercare e usare la messaggistica istantanea con chiunque usi ](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Skype, l'app consumer gratuita.</span><span class="sxs-lookup"><span data-stu-id="e3e30-134">![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) You can allow your users to search for and IM with everyone who uses Skype, the free consumer app!</span></span> <span data-ttu-id="e3e30-135">Per ulteriori informazioni, consulta [Consentire agli utenti Skype for Business di aggiungere contatti Skype.](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="e3e30-135">To learn more, see [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span>
  
## <a name="test-and-troubleshoot"></a><span data-ttu-id="e3e30-136">Test e risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e3e30-136">Test and troubleshoot</span></span>

<span data-ttu-id="e3e30-137"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="e3e30-137"><a name="bk_preview"> </a></span></span>

 <span data-ttu-id="e3e30-138">**Il problema più comune che si verifica quando si configura la comunicazione business-to-business è ottenere i propri URL e intervalli di indirizzi IP per [Office 365.](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)**</span><span class="sxs-lookup"><span data-stu-id="e3e30-138">**The most common issue people encounter when setting up business-to-business communication is getting their [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) right.**</span></span>
  
<span data-ttu-id="e3e30-139">Per testare la configurazione, devi avere un contatto in Skype for Business che non sia dietro il firewall della tua azienda.</span><span class="sxs-lookup"><span data-stu-id="e3e30-139">To test your setup, you need a contact on Skype for Business who's not behind your company firewall.</span></span>
  
1. <span data-ttu-id="e3e30-140">Dopo aver modificato le impostazioni per le comunicazioni esterne, **ATTENDI FINO A 24 ORE PER TESTARE.**</span><span class="sxs-lookup"><span data-stu-id="e3e30-140">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>

2. <span data-ttu-id="e3e30-141">In Skype for Business, cerca il tuo contatto in Skype for Business e invia una richiesta di chat.</span><span class="sxs-lookup"><span data-stu-id="e3e30-141">In Skype for Business, search for your contact in Skype for Business, and send a request to chat.</span></span>

    <span data-ttu-id="e3e30-142">Se viene visualizzato un messaggio che indica che non è stato possibile inviare il messaggio a causa dei criteri aziendali, è necessario verificare gli URL e gli intervalli di indirizzi IP per [Office 365.](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="e3e30-142">If you get a message that it couldn't be sent due to company policy, you need to double-check your [Office 365 URLs and IP address ranges](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).</span></span>

3. <span data-ttu-id="e3e30-143">Chiedi al tuo contatto Skype for Business di inviarti una richiesta di chat.</span><span class="sxs-lookup"><span data-stu-id="e3e30-143">Ask your Skype for Business contact to send you a request to chat.</span></span> <span data-ttu-id="e3e30-144">Se non si riceve la richiesta, il problema sono le impostazioni del firewall, supponendo di aver già verificato che le impostazioni firewall dell'altra organizzazione siano corrette.</span><span class="sxs-lookup"><span data-stu-id="e3e30-144">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="e3e30-145">Un altro modo per verificare se il problema è il tuo firewall è accedere a un wi-fi che non si trova dietro il firewall, ad esempio in un bar.</span><span class="sxs-lookup"><span data-stu-id="e3e30-145">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall, such as a coffee shop.</span></span> <span data-ttu-id="e3e30-146">Usare Skype for Business per inviare una richiesta di chat al proprio contatto.</span><span class="sxs-lookup"><span data-stu-id="e3e30-146">Use Skype for Business to send a request to your contact to chat.</span></span> <span data-ttu-id="e3e30-147">Se il messaggio viene inviato da lì, ma non quando sei al lavoro, allora il problema è il tuo firewall.</span><span class="sxs-lookup"><span data-stu-id="e3e30-147">If the message goes through there, but not when you're at work, then you know the problem is your firewall.</span></span>

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a><span data-ttu-id="e3e30-148">Come trovare ed essere trovati quando ti contatti con un'altra azienda</span><span class="sxs-lookup"><span data-stu-id="e3e30-148">How to find others, and be found, when connecting with another business</span></span>

<span data-ttu-id="e3e30-149"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="e3e30-149"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="e3e30-150">Dopo aver abilitato la comunicazione esterna con altri utenti Skype for Business, gli utenti possono trovare utenti Skype for Business federati cercando i loro nomi di accesso.</span><span class="sxs-lookup"><span data-stu-id="e3e30-150">After you enable external communication with other Skype for Business users, your users can find federated Skype for Business users by searching for their sign-in names.</span></span> <span data-ttu-id="e3e30-151">Un esempio è Rob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e3e30-151">An example is Rob@contoso.com.</span></span> <span data-ttu-id="e3e30-152">La persona dovrà quindi essere aggiunta alla propria lista di contatti.</span><span class="sxs-lookup"><span data-stu-id="e3e30-152">Then they will need to add the person to their list of contacts.</span></span>
  
![Per trovare un utente in un'azienda federata, è necessario cercarne l'indirizzo di posta elettronica (in genere è anche il nome di accesso).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a><span data-ttu-id="e3e30-154">Suggerimenti sulla configurazione delle comunicazioni con le aziende federate</span><span class="sxs-lookup"><span data-stu-id="e3e30-154">Tips on setting up communications with federated businesses</span></span>

<span data-ttu-id="e3e30-155"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="e3e30-155"><a name="bk_preview"> </a></span></span>

- <span data-ttu-id="e3e30-156">Per configurare la federazione tra Skype for Business 2015 e Skype for Business online, vedere questo articolo: Configurare la [federazione con Skype for Business online.](https://technet.microsoft.com/library/jj205126.aspx)</span><span class="sxs-lookup"><span data-stu-id="e3e30-156">To configure federation between Skype for Business 2015 and Skype for Business Online, see this  article: [Configure federation with Skype for Business Online](https://technet.microsoft.com/library/jj205126.aspx).</span></span>

- <span data-ttu-id="e3e30-157">Per configurare la federazione tra Lync e Skype for Business online, vedere questo articolo: Configurazione del supporto della federazione per [un cliente di Lync Online.](https://technet.microsoft.com/library/hh202193.aspx)</span><span class="sxs-lookup"><span data-stu-id="e3e30-157">To configure federation between Lync and Skype for Business Online, see this  article: [Configuring Federation Support for a Lync Online Customer](https://technet.microsoft.com/library/hh202193.aspx).</span></span>

- <span data-ttu-id="e3e30-158">Quando due utenti di Skype for Business in Microsoft 365 o Office 365 comunicano tra loro in domini separati, possono utilizzare solo le funzionalità di Skype for Business (ad esempio le conversazioni video o la condivisione del desktop) attivate in entrambe le organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="e3e30-158">When two Skype for Business users in Microsoft 365 or Office 365 are communicating with each other on separate domains, they can only use Skype for Business features (for example, video conversations or desktop sharing) that are turned on in both organizations.</span></span>

- <span data-ttu-id="e3e30-159">Se a un utente Skype for Business all'interno dell'organizzazione viene messo in stato di In-Place o blocco per controversia legale, tutte le conversazioni istantanee tra tale utente e altri utenti Skype for Business o Skype verranno salvate **in** Elementi ripristinabili nella propria cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e3e30-159">If a Skype for Business user in your organization is put on an In-Place or Litigation Hold, any IM conversations between that user and other Skype for Business or Skype users will be saved in **Recoverable Items** in their mailbox.</span></span> <span data-ttu-id="e3e30-160">Queste conversazioni non vengono salvate nella **cartella** Cronologia conversazioni della propria cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e3e30-160">These conversations aren't saved in the **Conversations History** folder in their mailbox.</span></span>

## <a name="turn-off-external-communication-for-specific-individuals"></a><span data-ttu-id="e3e30-161">Disattivare la comunicazione esterna per persone specifiche</span><span class="sxs-lookup"><span data-stu-id="e3e30-161">Turn off external communication for specific individuals</span></span>

<span data-ttu-id="e3e30-162"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="e3e30-162"><a name="bk_preview"> </a></span></span>

<span data-ttu-id="e3e30-163">Dopo aver abilitato la comunicazione esterna per l'intera azienda, è possibile disattivarla solo per individui specifici.</span><span class="sxs-lookup"><span data-stu-id="e3e30-163">After you enable external communication for your entire business, you can turn it off for only specific individuals.</span></span>
  
1. <span data-ttu-id="e3e30-164">Accedere con l'account di amministratore di Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="e3e30-164">Sign in with your Microsoft 365 or Office 365 admin account.</span></span>

2. <span data-ttu-id="e3e30-165">Nell'interfaccia di amministrazione passare **a Utenti**  >  **attivi.**</span><span class="sxs-lookup"><span data-stu-id="e3e30-165">In the admin center, go to **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e3e30-166">Nell'elenco degli utenti, scegli l'utente e quindi, in Altre **impostazioni,** fai clic **su Modifica proprietà Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="e3e30-166">In the list of users, choose the user, and then, under **More Settings**, click **Edit Skype for Business properties**.</span></span>

    ![Scegli Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. <span data-ttu-id="e3e30-168">**Nell'interfaccia di amministrazione di Skype for Business** scegli Comunicazioni **esterne.**</span><span class="sxs-lookup"><span data-stu-id="e3e30-168">In the **Skype for Business admin center**, choose **External communications**.</span></span>

    <span data-ttu-id="e3e30-169">Nella pagina **Opzioni** saranno selezionate tutte le opzioni.</span><span class="sxs-lookup"><span data-stu-id="e3e30-169">On the **Options** page, all of the choices will be selected.</span></span> <span data-ttu-id="e3e30-170">Cancellare le comunicazioni da disabilitare.</span><span class="sxs-lookup"><span data-stu-id="e3e30-170">Clear the communications you want to disable.</span></span> <span data-ttu-id="e3e30-171">L'immagine seguente mostra che Jakob sarà in grado di comunicare con persone di altre aziende attendibili, ma non con altri utenti Skype.</span><span class="sxs-lookup"><span data-stu-id="e3e30-171">The following image shows that Jakob will be able to communicate with people in other trusted businesses, but not with other Skype users.</span></span>

    ![Scegliere Contatti esterni](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. <span data-ttu-id="e3e30-173">Scegliere **Save**.</span><span class="sxs-lookup"><span data-stu-id="e3e30-173">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="e3e30-174">Per l'applicazione delle modifiche potrebbe essere necessario attendere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="e3e30-174">You may have to wait for up to 24 hours for your changes to take effect.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a><span data-ttu-id="e3e30-175">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e3e30-175">Related topics</span></span>

<span data-ttu-id="e3e30-176"><a name="bk_preview"> </a></span><span class="sxs-lookup"><span data-stu-id="e3e30-176"><a name="bk_preview"> </a></span></span>

[<span data-ttu-id="e3e30-177">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="e3e30-177">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)
  
[<span data-ttu-id="e3e30-178">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="e3e30-178">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
  