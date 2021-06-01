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
description: "Scopri come consentire alle persone che usano Skype for Business contattare Skype for Business utenti esterni all'organizzazione e aggiungerli al loro elenco di contatti. "
ms.openlocfilehash: d68fc27dfb1c77935ce74e278092f6ed4ae3d7dc
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239835"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="e46e3-103">Consentire agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="e46e3-103">Let Skype for Business users add Skype contacts</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="e46e3-104">Con Skype for Business, gli utenti possono cercare e messaggistica istantanea con chiunque usi Skype, l'app gratuita!</span><span class="sxs-lookup"><span data-stu-id="e46e3-104">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app!</span></span> <span data-ttu-id="e46e3-105">Questo articolo spiega cosa è necessario fare in modo che possano aggiungere Skype contatti.</span><span class="sxs-lookup"><span data-stu-id="e46e3-105">This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="e46e3-106">Per eseguire questa [operazione,](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) è Microsoft 365 o Office 365 autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="e46e3-106">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Microsoft 365 or Office 365 to do this.</span></span>

<span data-ttu-id="e46e3-107">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="e46e3-107">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="e46e3-108">Accedere con l'account Microsoft 365 o Office 365 amministratore di [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage) .</span><span class="sxs-lookup"><span data-stu-id="e46e3-108">Sign in with your Microsoft 365 or Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="e46e3-109">Nell'interfaccia di amministrazione passare a **Interfaccia di amministrazione**  >  **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="e46e3-109">In the admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Scegliere l'Skype for Business di amministrazione.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="e46e3-111">Nell'**interfaccia di amministrazione di Skype for Business** scegliere **Organizzazione** > **Comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="e46e3-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="e46e3-112">Per impostazione predefinita, gli utenti possono comunicare con tutte le altre persone del mondo che usano Skype for Business (presupponendo che il firewall sia stato configurato per consentire questa operazione).</span><span class="sxs-lookup"><span data-stu-id="e46e3-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Scegliere Consenti agli utenti di Skype for Business comunicare con Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="e46e3-114">Se si vuole che gli utenti chattino con gli utenti di Skype, ma non si vuole che chattino con altri utenti che usano Skype for Business, scegliere Sì solo per i **domini consentiti.**</span><span class="sxs-lookup"><span data-stu-id="e46e3-114">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**.</span></span> <span data-ttu-id="e46e3-115">Quando si abilita il contatto con Skype utenti, skype.com viene aggiunto automaticamente come dominio consentito dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="e46e3-115">When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="e46e3-116">Se si vuole consentire ai contatti di tutte le altre aziende del mondo di usare Skype for Business, ad eccezione di quelli specifici, scegliere Sì ad eccezione dei domini bloccati **e** scegliere di aggiungere **+** tali domini.</span><span class="sxs-lookup"><span data-stu-id="e46e3-116">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains.</span></span> <span data-ttu-id="e46e3-117">Tutti saranno in grado di contattare l'utente tranne le persone di tali domini specifici.</span><span class="sxs-lookup"><span data-stu-id="e46e3-117">Everyone will be able to contact you except people on those specific domains.</span></span> <span data-ttu-id="e46e3-118">Alcune aziende potrebbero scegliere questa opzione, ad esempio, se sono in controversia legale e devono assicurarsi che non ci siano contatti con l'altra azienda.</span><span class="sxs-lookup"><span data-stu-id="e46e3-118">(Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="e46e3-119">Scegliere **Consenti agli utenti di Skype for Business di comunicare con Skype utenti esterni all'organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="e46e3-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="e46e3-120">Se si usa firewall Windows, Skype for Business automaticamente le porte necessarie.</span><span class="sxs-lookup"><span data-stu-id="e46e3-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="e46e3-121">Se l'organizzazione usa un'altra soluzione per limitare la connessione a Internet dei computer della rete, verificare che i computer client siano in grado di accedere a tutti gli indirizzi [IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) e gli URL per la connettività Skype e la ricerca nella directory Skype.</span><span class="sxs-lookup"><span data-stu-id="e46e3-121">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search.</span></span> <span data-ttu-id="e46e3-122">Potrebbe essere necessario aggiungerli all'elenco di indirizzi consentiti in uscita nella configurazione del firewall o dell'infrastruttura proxy.</span><span class="sxs-lookup"><span data-stu-id="e46e3-122">This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="e46e3-123">**ATTENDERE FINO A 24 ORE PER TESTARE**.</span><span class="sxs-lookup"><span data-stu-id="e46e3-123">**WAIT UP TO 24 HOURS TO TEST**.</span></span> <span data-ttu-id="e46e3-124">Ogni volta che si modificano le impostazioni delle comunicazioni esterne, possono essere necessarie fino a 24 ore prima che le modifiche possano essere popolate in tutti i data center.</span><span class="sxs-lookup"><span data-stu-id="e46e3-124">Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="e46e3-125">Mostra agli utenti come trovare e aggiungere Skype contatti all'elenco di Skype for Business contatti.</span><span class="sxs-lookup"><span data-stu-id="e46e3-125">Show your users how to find and add Skype contacts to their list of Skype for Business contacts.</span></span> <span data-ttu-id="e46e3-126">Selezionare Cerca [persone in Skype for Business](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="e46e3-126">Point them to [Search for people in Skype for Business](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="e46e3-127">Testare e risolvere i problemi</span><span class="sxs-lookup"><span data-stu-id="e46e3-127">Test and troubleshoot</span></span>

<span data-ttu-id="e46e3-128">Per testare la configurazione, è necessario un contatto Skype che non sia dietro il firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="e46e3-128">To test your setup, you need a contact on Skype who's not behind your company firewall.</span></span> <span data-ttu-id="e46e3-129">Possono essere connessi a un account Skype un account Gmail, un account Outlook.com o un altro tipo di account di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e46e3-129">They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="e46e3-130">Dopo aver modificato le impostazioni delle comunicazioni esterne, **ATTENDERE FINO A 24 ORE PER VERIFICARE**.</span><span class="sxs-lookup"><span data-stu-id="e46e3-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="e46e3-131">Disconnettersi da Skype for Business e quindi accedere di nuovo in modo da visualizzare l'opzione per eseguire la ricerca nella Skype directory.</span><span class="sxs-lookup"><span data-stu-id="e46e3-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![Quando Skype è evidenziata, è possibile cercare le persone che hanno Skype account.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="e46e3-133">In Skype for Business, cercare il contatto in Skype e inviare una richiesta di chat.</span><span class="sxs-lookup"><span data-stu-id="e46e3-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="e46e3-134">Se viene visualizzato il messaggio che non è stato possibile inviare a causa dei criteri aziendali, è necessario verificare le impostazioni [del firewall.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)</span><span class="sxs-lookup"><span data-stu-id="e46e3-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="e46e3-135">Un altro modo per verificare se il problema è il firewall è passare a una posizione WiFi non dietro il firewall, ad esempio una caffetteria, e usare Skype for Business per inviare una richiesta al contatto di Skype per chattare.</span><span class="sxs-lookup"><span data-stu-id="e46e3-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
   - <span data-ttu-id="e46e3-136">**Se hai inviato il tuo Skype contatta una richiesta** e non l'ha mai ricevuta, chiedigli di inviarti una richiesta di chat.</span><span class="sxs-lookup"><span data-stu-id="e46e3-136">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat.</span></span> <span data-ttu-id="e46e3-137">Se il problema stava stabilendo una connessione tra Skype e Skype for Business, questo spesso lo risolve.</span><span class="sxs-lookup"><span data-stu-id="e46e3-137">If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
   - <span data-ttu-id="e46e3-138">Ora, se il messaggio viene inviato al bar, ma non al lavoro, il problema è il firewall.</span><span class="sxs-lookup"><span data-stu-id="e46e3-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="e46e3-139">Cosa si può e non si può fare</span><span class="sxs-lookup"><span data-stu-id="e46e3-139">What you can and can't do</span></span>

- <span data-ttu-id="e46e3-140">**Skype for Business in Mac** non è possibile cercare e comunicare con i Skype contatti.</span><span class="sxs-lookup"><span data-stu-id="e46e3-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="e46e3-141">Quando la ricerca nella directory è abilitata, è possibile cercare e trovare Skype e Skype for Business utenti.</span><span class="sxs-lookup"><span data-stu-id="e46e3-141">When directory search is enabled, you can search for and find Skype and Skype for Business users.</span></span> <span data-ttu-id="e46e3-142">Se per qualche motivo non è possibile trovarli eseguendo una ricerca nella directory, è possibile inviare una richiesta di contatto e chiedere loro di accedere a Skype e accettarla, in modo da potervi inviare messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="e46e3-142">If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="e46e3-143">Non è possibile consentire la connettività di messaggistica istantanea con altri provider di messaggistica istantanea, ad esempio Google o Facebook.</span><span class="sxs-lookup"><span data-stu-id="e46e3-143">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook.</span></span> <span data-ttu-id="e46e3-144">Non è possibile usare le Skype for Business per inviare SMS al cellulare.</span><span class="sxs-lookup"><span data-stu-id="e46e3-144">You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="e46e3-145">Non è possibile registrare chiamate audio o video tra un contatto Skype contatto Skype for Business contatto.</span><span class="sxs-lookup"><span data-stu-id="e46e3-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="e46e3-146">Quali funzionalità sono disponibili quando si aggiungono Skype contatti?</span><span class="sxs-lookup"><span data-stu-id="e46e3-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="e46e3-147">Skype i contatti che hanno eseguito l'accesso con il proprio account Microsoft (in precedenza Windows Live ID) possono ottenere alcune funzionalità, ma non tutte, quando parlano con gli Skype for Business utenti.</span><span class="sxs-lookup"><span data-stu-id="e46e3-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="e46e3-148">**Disponibile con Skype contatti**</span><span class="sxs-lookup"><span data-stu-id="e46e3-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="e46e3-149">**Non disponibile con i Skype contatti**</span><span class="sxs-lookup"><span data-stu-id="e46e3-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="e46e3-150">Conversazioni video</span><span class="sxs-lookup"><span data-stu-id="e46e3-150">Video conversations</span></span> <br/>  <span data-ttu-id="e46e3-151">Messaggistica istantanea da persona a persona</span><span class="sxs-lookup"><span data-stu-id="e46e3-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="e46e3-152">Icone di presenza</span><span class="sxs-lookup"><span data-stu-id="e46e3-152">Presence</span></span> <br/> | <span data-ttu-id="e46e3-153">Conversazioni di messaggistica istantanea tra più parti</span><span class="sxs-lookup"><span data-stu-id="e46e3-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="e46e3-154">Conversazioni audio e video con tre o più persone</span><span class="sxs-lookup"><span data-stu-id="e46e3-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="e46e3-155">Condivisione di desktop e programmi</span><span class="sxs-lookup"><span data-stu-id="e46e3-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="e46e3-156">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e46e3-156">Related topics</span></span>

[<span data-ttu-id="e46e3-157">Consentire agli utenti di contattare utenti Skype for Business esterni</span><span class="sxs-lookup"><span data-stu-id="e46e3-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="e46e3-158">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="e46e3-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 
