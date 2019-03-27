---
title: Consentire agli utenti di Skype for Business di aggiungere contatti Skype
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: "Vedere come consentire agli utenti che utilizzano Skype per contatto commerciale Skype per gli utenti aziendali di all'esterno dell'organizzazione e aggiungerli all'elenco dei contatti. "
ms.openlocfilehash: 212393154cb2b730ce18f5be9b03495e747e207c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885461"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="b09fa-103">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="b09fa-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="b09fa-104">Con Skype per le aziende, gli utenti possono cercare e messaggistica immediata con tutti gli utenti Skype, gratuitamente l'app!</span><span class="sxs-lookup"><span data-stu-id="b09fa-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="b09fa-105">In questo articolo viene illustrato che cosa è necessario eseguire in modo che è possibile aggiungere contatti Skype.</span><span class="sxs-lookup"><span data-stu-id="b09fa-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="b09fa-106">In Office 365 a tale scopo, è necessario disporre [delle autorizzazioni di amministratore](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) .</span><span class="sxs-lookup"><span data-stu-id="b09fa-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>

<span data-ttu-id="b09fa-107">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="b09fa-107">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="b09fa-108">Accedere con l'account di amministrazione di Office 365 in [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span><span class="sxs-lookup"><span data-stu-id="b09fa-108">Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="b09fa-109">Nell'interfaccia di amministrazione di Office 365 andare a **Admin Center** > **Skype per le aziende**.</span><span class="sxs-lookup"><span data-stu-id="b09fa-109">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Scegliere Skype per interfaccia di amministrazione di Business.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="b09fa-111">**Skype per interfaccia di amministrazione di Business**, selezionare **organizzazione** > **comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="b09fa-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="b09fa-112">Per impostazione predefinita, gli utenti possono comunicare con tutti gli altri utenti in tutto il mondo Skype per le aziende (presupponendo che il firewall è stato configurato per consentire questa operazione).</span><span class="sxs-lookup"><span data-stu-id="b09fa-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Selezionare Consenti Skype per le aziende utilizzato dagli utenti per comunicare con Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="b09fa-114">Se si desidera che gli utenti in chat con gli utenti Skype, ma non si desidera loro di parlare con altri utenti che utilizzano Skype per le aziende, fare clic **su solo per domini consentiti**.</span><span class="sxs-lookup"><span data-stu-id="b09fa-114">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="b09fa-115">Quando si abilita contatto con gli utenti Skype, skype.com viene aggiunto automaticamente come un dominio consentito in background.</span><span class="sxs-lookup"><span data-stu-id="b09fa-115">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="b09fa-116">Se si desidera consentire contatto da tutte le altre aziende in tutto il mondo utilizzo Skype for Business, ad eccezione di quelle specifiche, scegliere **su ad eccezione dei domini bloccati**e fare clic su **+** per aggiungere tali domini.</span><span class="sxs-lookup"><span data-stu-id="b09fa-116">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="b09fa-117">Tutti gli utenti saranno in grado di contattare l'utente, ad eccezione di persone in tali domini specifici.</span><span class="sxs-lookup"><span data-stu-id="b09fa-117">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="b09fa-118">(Alcune aziende possono scegliere questa opzione, ad esempio, se sono in controversie legali ed è necessario verificare che non esiste alcun contatto con altri business).</span><span class="sxs-lookup"><span data-stu-id="b09fa-118">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="b09fa-119">Scegliere **gli utenti utilizzano Skype per le aziende di comunicare con utenti Skype all'esterno dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="b09fa-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="b09fa-120">Se si utilizza Windows Firewall, Skype per le aziende apre le porte necessarie automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b09fa-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="b09fa-121">Se l'organizzazione utilizza un'altra soluzione per limitare i computer della rete di connettersi a Internet, verificare che i computer client siano in grado di accedere a tutti i [gli indirizzi IP e URL](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per la connettività Skype e ricerca nella Directory Skype.</span><span class="sxs-lookup"><span data-stu-id="b09fa-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="b09fa-122">Può essere necessario aggiungerli a in uscita elenco Consenti nella configurazione dell'infrastruttura di firewall o proxy.</span><span class="sxs-lookup"><span data-stu-id="b09fa-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="b09fa-123">**ATTENDERE fino a 24 ore da TESTARE**.</span><span class="sxs-lookup"><span data-stu-id="b09fa-123">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="b09fa-124">Ogni volta che si modificano le impostazioni di comunicazioni esterne, può richiedere fino a 24 ore per le modifiche da popolare in tutti i data center.</span><span class="sxs-lookup"><span data-stu-id="b09fa-124">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="b09fa-125">Mostra agli utenti come trovare e aggiungere Skype contatti al proprio elenco di Skype per i contatti aziendali.</span><span class="sxs-lookup"><span data-stu-id="b09fa-125">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="b09fa-126">Puntino a [ricerca per i partecipanti Skype per le aziende](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="b09fa-126">Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="b09fa-127">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="b09fa-127">Test and troubleshoot</span></span>

<span data-ttu-id="b09fa-128">Per testare l'installazione, è necessario disporre di un contatto in Skype che non sono protetti dal firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="b09fa-128">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="b09fa-129">È possibile eseguire l'accesso a Skype utilizzando un account Gmail, Outlook.com account o un altro tipo di account di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b09fa-129">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="b09fa-130">Dopo aver modificare le impostazioni di comunicazioni esterne, **ATTENDERE fino a 24 ore a TEST**.</span><span class="sxs-lookup"><span data-stu-id="b09fa-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="b09fa-131">Disconnettersi da Skype per le aziende e quindi effettuare nuovamente l'accesso in modo che viene visualizzata l'opzione di eseguire ricerche nella Skype Directory.</span><span class="sxs-lookup"><span data-stu-id="b09fa-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Quando viene evidenziato Skype Directory, è possibile cercare persone che dispongono di account Skype.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="b09fa-133">In Skype per le aziende, cercare il contatto in Skype e inviare una richiesta a chat.</span><span class="sxs-lookup"><span data-stu-id="b09fa-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="b09fa-134">Se viene visualizzato il messaggio che non è stato inviato a causa di politica aziendale, è necessario controllare le [impostazioni del firewall](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="b09fa-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="b09fa-135">Un altro modo per verificare se il problema è il firewall sia passare a una posizione wifi non protetti dal firewall, ad esempio un Internet café e utilizzare Skype for Business per inviare una richiesta per il Skype rivolgersi alla chat.</span><span class="sxs-lookup"><span data-stu-id="b09fa-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="b09fa-136">**Se è stata inviata dal contatto Skype una richiesta e che non ricevuti**, chiedere di inviare una richiesta a chat.</span><span class="sxs-lookup"><span data-stu-id="b09fa-136">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="b09fa-137">Se il problema è stato stabilire una connessione tra Skype e Skype per le aziende, che spesso consente di risolvere lo.</span><span class="sxs-lookup"><span data-stu-id="b09fa-137">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="b09fa-138">Se il messaggio attraversa in bar, ma non quando si è in ufficio, si conosce il problema è ora del firewall.</span><span class="sxs-lookup"><span data-stu-id="b09fa-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="b09fa-139">Che cosa è possibile e non consentite</span><span class="sxs-lookup"><span data-stu-id="b09fa-139">What you can and can't do</span></span>

- <span data-ttu-id="b09fa-140">**Skype per le aziende in Mac** non hanno la possibilità di cercare e comunicare con contatti Skype.</span><span class="sxs-lookup"><span data-stu-id="b09fa-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="b09fa-141">Durante la ricerca nella directory è abilitata, è possibile cercare e trovare Skype e Skype per gli utenti aziendali.</span><span class="sxs-lookup"><span data-stu-id="b09fa-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="b09fa-142">Se per qualche motivo che è Impossibile trovare eseguendo una ricerca nella directory, è possibile inviare loro una richiesta di contatto e sono li accedere a Skype e accettare il documento, pertanto è possibile messaggistica Istantanea con loro.</span><span class="sxs-lookup"><span data-stu-id="b09fa-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="b09fa-143">Non è possibile consentire di connettività per messaggistica immediata con altri provider di messaggistica immediata, ad esempio Google o Facebook.</span><span class="sxs-lookup"><span data-stu-id="b09fa-143">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="b09fa-144">È possibile utilizzare Skype per le aziende a inviare messaggi di testo di un telefono cellulare.</span><span class="sxs-lookup"><span data-stu-id="b09fa-144">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="b09fa-145">Non è possibile registrare l'audio o video chiamate tra un contatto Skype e Skype per contatto commerciale.</span><span class="sxs-lookup"><span data-stu-id="b09fa-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="b09fa-146">Le funzionalità sono disponibili quando si aggiungono contatti Skype?</span><span class="sxs-lookup"><span data-stu-id="b09fa-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="b09fa-147">Contatti Skype che ha effettuato l'accesso con l'account Microsoft (precedenza account Windows Live ID) è possono ottenere alcuni, ma non tutti, funzionalità trattano con i Skype per gli utenti aziendali.</span><span class="sxs-lookup"><span data-stu-id="b09fa-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="b09fa-148">**Disponibile con i contatti Skype**</span><span class="sxs-lookup"><span data-stu-id="b09fa-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="b09fa-149">**Non disponibile con i contatti Skype**</span><span class="sxs-lookup"><span data-stu-id="b09fa-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="b09fa-150">Conversazioni video</span><span class="sxs-lookup"><span data-stu-id="b09fa-150">Video conversations</span></span> <br/>  <span data-ttu-id="b09fa-151">Messaggistica immediata tra due persone</span><span class="sxs-lookup"><span data-stu-id="b09fa-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="b09fa-152">Presenza</span><span class="sxs-lookup"><span data-stu-id="b09fa-152">Presence</span></span> <br/> | <span data-ttu-id="b09fa-153">Conversazioni di messaggistica Istantanea con più partecipanti</span><span class="sxs-lookup"><span data-stu-id="b09fa-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="b09fa-154">Conversazioni audio e video con tre o più persone</span><span class="sxs-lookup"><span data-stu-id="b09fa-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="b09fa-155">Condivisione desktop e programmi</span><span class="sxs-lookup"><span data-stu-id="b09fa-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="b09fa-156">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b09fa-156">Related topics</span></span>

[<span data-ttu-id="b09fa-157">Consentire agli utenti di contattare utenti Skype for Business esterni</span><span class="sxs-lookup"><span data-stu-id="b09fa-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="b09fa-158">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="b09fa-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
