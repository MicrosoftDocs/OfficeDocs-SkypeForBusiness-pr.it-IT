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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
- LIL_Placement
description: "Informazioni su come consentire alle persone che usano Skype for business di contattare utenti Skype for business all'esterno dell'organizzazione e aggiungerli al proprio elenco di contatti. "
ms.openlocfilehash: d6251e8e86527172e6818d11b1e07da892b4b0ef
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692881"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="2fcde-103">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="2fcde-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="2fcde-104">Con Skype for business, gli utenti possono cercare e inviare messaggi istantanei con tutti coloro che usano Skype, l'app gratuita.</span><span class="sxs-lookup"><span data-stu-id="2fcde-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="2fcde-105">In questo articolo vengono illustrate le operazioni da eseguire in modo che possano aggiungere contatti Skype.</span><span class="sxs-lookup"><span data-stu-id="2fcde-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="2fcde-106">Per eseguire questa operazione, è necessario disporre [delle autorizzazioni di amministratore](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365.</span><span class="sxs-lookup"><span data-stu-id="2fcde-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>

<span data-ttu-id="2fcde-107">![Icona che mostra il logo](../images/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business**</span><span class="sxs-lookup"><span data-stu-id="2fcde-107">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="2fcde-108">Accedere con l'account di amministratore di Office 365 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="2fcde-108">Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="2fcde-109">Nell'interfaccia di amministrazione accedere a interfaccia di **Amministrazione** > di**Skype for business**.</span><span class="sxs-lookup"><span data-stu-id="2fcde-109">In the admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Scegliere l'interfaccia di amministrazione di Skype for business.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="2fcde-111">Nell'interfaccia di **amministrazione di Skype for business**scegli \*\*\*\* > **comunicazioni esterne**dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2fcde-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="2fcde-112">Per impostazione predefinita, gli utenti possono comunicare con tutte le altre persone del mondo che usano Skype for business (supponendo che il firewall sia stato configurato per consentire questa operazione).</span><span class="sxs-lookup"><span data-stu-id="2fcde-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Scegli consentire agli utenti di usare Skype for business per comunicare con Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="2fcde-114">Se vuoi che gli utenti possano chattare con gli utenti Skype, ma non vuoi che vengano chattati con altri che usano Skype for business, scegli **solo per i domini consentiti**.</span><span class="sxs-lookup"><span data-stu-id="2fcde-114">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="2fcde-115">Quando si Abilita il contatto con utenti Skype, skype.com viene automaticamente aggiunto come dominio consentito dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="2fcde-115">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="2fcde-116">Se vuoi consentire il contatto di tutte le altre aziende del mondo usando Skype for business, eccetto quelle specifiche, scegli attivato **eccetto i domini bloccati**e scegli **+** di aggiungere tali domini.</span><span class="sxs-lookup"><span data-stu-id="2fcde-116">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="2fcde-117">Tutti saranno in grado di contattare l'utente, eccetto gli utenti di questi specifici domini.</span><span class="sxs-lookup"><span data-stu-id="2fcde-117">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="2fcde-118">Alcune aziende potrebbero scegliere questa opzione, ad esempio se sono in contenzioso ed è necessario assicurarsi che non ci siano contatti con l'altra azienda.</span><span class="sxs-lookup"><span data-stu-id="2fcde-118">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="2fcde-119">Scegli **consentire alle persone di usare Skype for business per comunicare con gli utenti Skype all'esterno dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="2fcde-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="2fcde-120">Se si usa Windows Firewall, Skype for Business apre automaticamente le porte necessarie.</span><span class="sxs-lookup"><span data-stu-id="2fcde-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="2fcde-121">Se l'organizzazione usa un'altra soluzione per limitare la connessione a Internet da parte dei computer della rete, assicurarsi che i computer client siano in grado di accedere a tutti gli [indirizzi IP e agli URL](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per la connettività Skype e la ricerca nella directory Skype.</span><span class="sxs-lookup"><span data-stu-id="2fcde-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="2fcde-122">Potrebbe essere necessario aggiungerli all'elenco Consenti in uscita nella configurazione del firewall o dell'infrastruttura proxy.</span><span class="sxs-lookup"><span data-stu-id="2fcde-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="2fcde-123">**Attendere fino a 24 ore per eseguire il test**.</span><span class="sxs-lookup"><span data-stu-id="2fcde-123">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="2fcde-124">Ogni volta che si modificano le impostazioni di comunicazione esterna, è possibile che le modifiche vengano inserite in tutti i centri dati fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="2fcde-124">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="2fcde-125">Mostra agli utenti come trovare e aggiungere contatti Skype all'elenco dei contatti di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="2fcde-125">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="2fcde-126">Puntali alla [ricerca di persone in Skype for business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="2fcde-126">Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="2fcde-127">Test e risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="2fcde-127">Test and troubleshoot</span></span>

<span data-ttu-id="2fcde-128">Per testare la configurazione, è necessario un contatto su Skype che non si trova dietro il firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="2fcde-128">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="2fcde-129">Possono essere connessi a Skype usando un account di Gmail, un account di Outlook.com o un altro tipo di account di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="2fcde-129">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="2fcde-130">Dopo aver modificato le impostazioni di comunicazione esterna, **attendere fino a 24 ore per**eseguire il test.</span><span class="sxs-lookup"><span data-stu-id="2fcde-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="2fcde-131">Disconnettersi da Skype for business e quindi eseguire di nuovo l'accesso per visualizzare l'opzione per cercare nella directory Skype.</span><span class="sxs-lookup"><span data-stu-id="2fcde-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Quando viene evidenziata la directory Skype, è possibile cercare persone con account Skype.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="2fcde-133">In Skype for business cercare il contatto in Skype e inviare una richiesta di chat.</span><span class="sxs-lookup"><span data-stu-id="2fcde-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="2fcde-134">Se viene visualizzato il messaggio che non è stato possibile inviare a causa di criteri aziendali, è necessario effettuare un doppio controllo sulle [impostazioni del firewall](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="2fcde-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="2fcde-135">Un altro modo per verificare se il problema è il firewall consiste nell'accedere a una posizione WiFi non dietro il firewall, ad esempio un coffee shop, e usare Skype for business per inviare una richiesta al contatto Skype per chattare.</span><span class="sxs-lookup"><span data-stu-id="2fcde-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="2fcde-136">**Se il contatto Skype è stato inviato a una richiesta e non è mai stato ricevuto**, chiedere loro di inviare una richiesta di chat.</span><span class="sxs-lookup"><span data-stu-id="2fcde-136">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="2fcde-137">Se il problema è stato stabilire una connessione tra Skype e Skype for business, che spesso lo risolve.</span><span class="sxs-lookup"><span data-stu-id="2fcde-137">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="2fcde-138">Ora, se il messaggio passa al Coffee Shop, ma non quando sei al lavoro, allora sai che il problema è il tuo firewall.</span><span class="sxs-lookup"><span data-stu-id="2fcde-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="2fcde-139">Cosa si può o non si può fare</span><span class="sxs-lookup"><span data-stu-id="2fcde-139">What you can and can't do</span></span>

- <span data-ttu-id="2fcde-140">**Skype for business per Mac** non ha la possibilità di cercare e comunicare con i contatti Skype.</span><span class="sxs-lookup"><span data-stu-id="2fcde-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="2fcde-141">Quando la ricerca directory è abilitata, è possibile cercare e trovare utenti Skype e Skype for business.</span><span class="sxs-lookup"><span data-stu-id="2fcde-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="2fcde-142">Se per qualche motivo non è possibile trovarli eseguendo una ricerca nella directory, è possibile inviare una richiesta di contatto e quindi accedervi in Skype e accettarla, in modo che sia possibile inviarla tramite chat.</span><span class="sxs-lookup"><span data-stu-id="2fcde-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="2fcde-143">Non è possibile consentire la connettività di messaggistica istantanea con altri provider di messaggistica istantanea, ad esempio Google o Facebook.</span><span class="sxs-lookup"><span data-stu-id="2fcde-143">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="2fcde-144">Non è possibile usare Skype for business per inviare messaggi di testo tramite telefono cellulare.</span><span class="sxs-lookup"><span data-stu-id="2fcde-144">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="2fcde-145">Non è possibile registrare chiamate audio o video tra un contatto Skype e un contatto Skype for business.</span><span class="sxs-lookup"><span data-stu-id="2fcde-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="2fcde-146">Quali funzionalità sono disponibili quando si aggiungono contatti Skype?</span><span class="sxs-lookup"><span data-stu-id="2fcde-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="2fcde-147">I contatti di Skype che hanno effettuato l'accesso con il proprio account Microsoft (in precedenza Windows Live ID) possono ottenere alcune funzionalità, ma non tutte, quando parlano con gli utenti di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="2fcde-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="2fcde-148">**Disponibile con i contatti Skype**</span><span class="sxs-lookup"><span data-stu-id="2fcde-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="2fcde-149">**Non disponibile con i contatti Skype**</span><span class="sxs-lookup"><span data-stu-id="2fcde-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="2fcde-150">Conversazioni video</span><span class="sxs-lookup"><span data-stu-id="2fcde-150">Video conversations</span></span> <br/>  <span data-ttu-id="2fcde-151">Messaggistica istantanea da persona a persona</span><span class="sxs-lookup"><span data-stu-id="2fcde-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="2fcde-152">Icone di presenza</span><span class="sxs-lookup"><span data-stu-id="2fcde-152">Presence</span></span> <br/> | <span data-ttu-id="2fcde-153">Conversazioni di messaggistica istantanea con più partecipanti</span><span class="sxs-lookup"><span data-stu-id="2fcde-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="2fcde-154">Conversazioni audio e video con tre o più persone</span><span class="sxs-lookup"><span data-stu-id="2fcde-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="2fcde-155">Condivisione di desktop e programmi</span><span class="sxs-lookup"><span data-stu-id="2fcde-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="2fcde-156">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2fcde-156">Related topics</span></span>

[<span data-ttu-id="2fcde-157">Consentire agli utenti di contattare utenti Skype for Business esterni</span><span class="sxs-lookup"><span data-stu-id="2fcde-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="2fcde-158">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="2fcde-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
