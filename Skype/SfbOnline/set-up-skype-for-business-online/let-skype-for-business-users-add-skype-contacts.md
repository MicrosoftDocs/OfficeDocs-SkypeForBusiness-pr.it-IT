---
title: Consenti agli utenti di Skype for Business di aggiungere contatti Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
- LIL_Placement
description: 'See how to  let people who are using Skype for Business contact Skype for Business users from outside your organization and add them to their list of contacts. '
ms.openlocfilehash: 37f028c6a7347f13c6f41d88bfdb23907dfa92c3
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500616"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a><span data-ttu-id="e4e83-103">Consenti agli utenti di Skype for Business di aggiungere contatti Skype</span><span class="sxs-lookup"><span data-stu-id="e4e83-103">Let Skype for Business users add Skype contacts</span></span>

<span data-ttu-id="e4e83-p101">[] Con Skype for Business, gli utenti possono cercare e scambiare messaggi istantanei con tutti gli utenti di Skype, l'app gratuita. Questo articolo spiega di cosa hai bisogno perché la tua azienda possa aggiungere contatti Skype.</span><span class="sxs-lookup"><span data-stu-id="e4e83-p101">With Skype for Business, your users can search for and IM with everyone who uses Skype, the free app! This article explains what you need to do so they can add Skype contacts.</span></span> 
  
<span data-ttu-id="e4e83-106">Per eseguire questa procedura, è necessario avere autorizzazioni di [Informazioni sui ruoli di amministratore di Office 365](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4e83-106">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US) in Office 365 to do this.</span></span>

<span data-ttu-id="e4e83-107">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="e4e83-107">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="e4e83-108">Accedere con l'account di amministrazione di Office 365 in [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span><span class="sxs-lookup"><span data-stu-id="e4e83-108">Sign in with your Office 365 admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage).</span></span>
    
2. <span data-ttu-id="e4e83-109">In Interfaccia di amministrazione di Office 365, vai a **Interfacce di amministrazione** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="e4e83-109">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span> 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. <span data-ttu-id="e4e83-111">In **Interfaccia di amministrazione di Skype for Business**, scegli **Organizzazione** > **Comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="e4e83-111">In the **Skype for Business admin center**, choose **Organization** > **External communications**.</span></span> 
    
4. <span data-ttu-id="e4e83-112">Per impostazione predefinita, gli utenti possono comunicare con tutte le altre persone nel mondo che usano Skype for Business (supponendo che il firewall sia stato configurato per permetterlo).</span><span class="sxs-lookup"><span data-stu-id="e4e83-112">By default, your users can communicate with all other people in the world who use Skype for Business (assuming your firewall has been configured to allow this).</span></span> 
    
    ![Choose Let people use Skype for Business to communicate with Skype.](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    <span data-ttu-id="e4e83-p102">Se desideri che i tuoi utenti possano comunicare in chat con gli utenti Skype MA non con altri utenti che usano Skype for Business, nella casella di riepilogo a discesa, scegli **Attiva solo per i domini consentiti**. (Quando consenti agli utenti di contattare utenti Skype, skype.com viene automaticamente aggiunto come dominio consentito dietro le quinte.)</span><span class="sxs-lookup"><span data-stu-id="e4e83-p102">If you want your users to chat with Skype users, BUT you don't want them to chat with others who use Skype for Business, choose **On only for allowed domains**. When you enable contact with Skype users, skype.com is automatically added as an allowed domain behind the scenes.</span></span> 
    
    <span data-ttu-id="e4e83-p103">Se vuoi consentire il contatto da tutte le altre aziende al mondo che usano Skype for Business, tranne alcune specifiche, scegli **Attiva eccetto i domini bloccati**, quindi scegli **+** per aggiungere tali domini. Tutti potranno contattare la tua azienda tranne le persone in quei domini specifici. Alcune aziende possono scegliere questa opzione, ad esempio, in caso di controversia legale, qualora fosse necessario assicurarsi che non ci sia alcun contatto con l'altra azienda.</span><span class="sxs-lookup"><span data-stu-id="e4e83-p103">If you want to allow contact from all other businesses in the world using Skype for Business, except specific ones, choose **On except for blocked domains**, and choose **+** to add those domains. Everyone will be able to contact you except people on those specific domains. (Some businesses might choose this option, for example, if they are in litigation and need to ensure there's no contact with the other business.)</span></span>
    
5. <span data-ttu-id="e4e83-119">Scegli **Consenti l'utilizzo di Skype for Business per comunicare con utenti Skype all'esterno dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="e4e83-119">Choose **Let people use Skype for Business to communicate with Skype users outside your organization**.</span></span> 
    
6.  <span data-ttu-id="e4e83-120">Se si utilizza Windows Firewall, Skype for Business apre automaticamente le porte necessarie.</span><span class="sxs-lookup"><span data-stu-id="e4e83-120">If you're using Windows Firewall, Skype for Business opens the required ports automatically.</span></span>
    
    <span data-ttu-id="e4e83-p104">Se la tua organizzazione usa un'altra soluzione per limitare la connessione a Internet dei computer sulla rete, assicurati che i computer client siano in grado di accedere a tutti gli [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) per la connettività di Skype e la ricerca directory Skype. A tale scopo, potrebbe essere necessario aggiungerli all'elenco degli elementi consentiti in uscita nella configurazione dell'infrastruttura del firewall o del proxy.</span><span class="sxs-lookup"><span data-stu-id="e4e83-p104">If your organization uses another solution to restrict computers on your network from connecting to the Internet, ensure client computers are able to access all of the [IP addresses and URLs](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) for Skype connectivity and Skype Directory Search. This may require adding them to the outbound allow list in your firewall or proxy infrastructure configuration.</span></span>
    
7. <span data-ttu-id="e4e83-p105">**ATTENDI FINO A 24 ORE PRIMA DEL TEST**. Ogni volta che modifichi le impostazioni per le comunicazioni esterne, possono occorrere fino a 24 ore perché le modifiche vengano distribuite su tutti i data center.</span><span class="sxs-lookup"><span data-stu-id="e4e83-p105">**WAIT UP TO 24 HOURS TO TEST**. Any time you change the external communications settings, it can take up to 24 hours for the changes to populate across all the data centers.</span></span>
    
8. <span data-ttu-id="e4e83-p106">Mostra ai tuoi utenti come trovare e aggiungere contatti di Skype ai propri elenchi di contatti Skype for Business. Invitali a consultare l'articolo [Cercare persone in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span><span class="sxs-lookup"><span data-stu-id="e4e83-p106">Show your users how to find and add Skype contacts to their list of Skype for Business contacts. Point them to [Search for people in Skype for Business](https://support.office.com/en-us/article/b12500ef-e37f-4d22-aade-c11277e53f19).</span></span>
    
## <a name="test-and-troubleshoot"></a><span data-ttu-id="e4e83-127">Test e risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="e4e83-127">Test and troubleshoot</span></span>

<span data-ttu-id="e4e83-p107">Per testare le tue impostazioni, ti servirà un contatto in Skype che non sia dietro il firewall della tua azienda. Può essere connesso a Skype mediante un account Gmail, Outlook.com o altro tipo di account di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e4e83-p107">To test your setup, you need a contact on Skype who's not behind your company firewall. They can be signed in to Skype using a Gmail account, Outlook.com account, or other type of email account.</span></span>
  
1. <span data-ttu-id="e4e83-130">Dopo aver modificato le impostazioni di comunicazione esterna, **ASPETTA FINO A 24 ORE PER TESTARLE**.</span><span class="sxs-lookup"><span data-stu-id="e4e83-130">After you change your external communications settings, **WAIT UP TO 24 HOURS TO TEST**.</span></span>
    
2. <span data-ttu-id="e4e83-131">Esci da Skype for Business e poi accedi di nuovo, in modo da visualizzare la possibilità di cercare nella Directory Skype.</span><span class="sxs-lookup"><span data-stu-id="e4e83-131">Sign out of Skype for Business and then sign in again so you see the option to search the Skype Directory.</span></span> 
    
    ![When Skype Directory is highlighted, you can search for people who have Skype accounts.](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. <span data-ttu-id="e4e83-133">In Skype for Business, cerca il tuo contatto Skype e inviagli una richiesta di chat.</span><span class="sxs-lookup"><span data-stu-id="e4e83-133">In Skype for Business, search for your contact in Skype, and send a request to chat.</span></span> 
    
    <span data-ttu-id="e4e83-134">Se viene visualizzato un errore che indica che non è stato possibile inviare il messaggio a causa di criteri aziendali, devi verificare le [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="e4e83-134">If you get the message it couldn't be sent due to company policy, you need to double-check your [firewall settings](https://support.office.com/en-us/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span> 
    
4. <span data-ttu-id="e4e83-135">Un altro metodo per testare se il problema è causato dal firewall è spostarti in un luogo dove la rete WiFi non si trova dietro il firewall, ad esempio in un bar, e utilizzare Skype for Business per inviare una richiesta di chat al tuo contatto Skype.</span><span class="sxs-lookup"><span data-stu-id="e4e83-135">Another way to test whether the problem is your firewall is to go to a wifi location not behind your firewall such as a coffee shop, and use Skype for Business to send a request to your Skype contact to chat.</span></span> 
    
  - <span data-ttu-id="e4e83-p108">**Se hai inviato una richiesta al tuo contatto Skype e lui non l'ha mai ricevuta**, chiedigli di inviarti una richiesta di chat. Se il problema è stabilire una connessione tra Skype e Skype for Business, in questo modo spesso si risolve.</span><span class="sxs-lookup"><span data-stu-id="e4e83-p108">**If you sent your Skype contact a request and they never received it**, ask them to send you a request to chat. If the problem was establishing a connection between Skype and Skype for Business, that often solves it.</span></span>
    
  - <span data-ttu-id="e4e83-138">Se il messaggio viene consegnato dal bar ma non quando sei al lavoro, allora il problema è senz'altro il tuo firewall.</span><span class="sxs-lookup"><span data-stu-id="e4e83-138">Now if the message goes through at the coffee shop but not when you're at work, then you know the problem is your firewall.</span></span> 
    
## <a name="what-you-can-and-cant-do"></a><span data-ttu-id="e4e83-139">Funzionalità disponibili e non disponibili</span><span class="sxs-lookup"><span data-stu-id="e4e83-139">What you can and can't do</span></span>

- <span data-ttu-id="e4e83-140">**Skype for Businessper Mac** non consente di cercare e comunicare con contatti Skype.</span><span class="sxs-lookup"><span data-stu-id="e4e83-140">**Skype for Business on Mac** doesn't have the ability to search for and communicate with Skype contacts.</span></span>
    
- <span data-ttu-id="e4e83-p109">Mentre tu puoi cercare e trovare utenti Skype, loro non possono cercare e trovare utenti Skype for Business. Devi inviare loro una richiesta di contatto e loro devono accedere a Skype e accettare la richiesta prima che possiate comunicare con i messaggi istantanei.</span><span class="sxs-lookup"><span data-stu-id="e4e83-p109">When directory search is enabled, you can search for and find Skype and Skype for Business users. If for some reason you can't find them by searching the directory, you can send them a contact request, and then have them sign in to Skype and accept it, so you can IM with them.</span></span> 
    
- <span data-ttu-id="e4e83-p110">Non è possibile consentire la connettività per la messaggistica istantanea con altri provider come Google o Facebook. Non puoi utilizzare Skype for Business per inviare messaggi di testo da cellulare.</span><span class="sxs-lookup"><span data-stu-id="e4e83-p110">It's not possible to allow IM connectivity with other IM providers such as Google or Facebook. You can't use Skype for Business to send cell phone text messages.</span></span>

- <span data-ttu-id="e4e83-145">Quali funzionalità sono disponibili quando aggiungi contatti Skype?</span><span class="sxs-lookup"><span data-stu-id="e4e83-145">It is not possible to record audio or video calls between a Skype Contact and Skype for Business contact.</span></span>
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a><span data-ttu-id="e4e83-146">I contatti di Skype che hanno effettuato l'accesso con il loro account Microsoft (noto in precedenza come Windows Live ID) possono beneficiare di una parte ma non di tutte le funzioni disponibili quando parlano con un utente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e4e83-146">What features are available when adding Skype contacts?</span></span>

<span data-ttu-id="e4e83-147">I contatti Skype che hanno effettuato l'accesso con il loro account Microsoft (noto in precedenza come Windows Live ID) possono beneficiare di una parte ma non di tutte le funzioni disponibili quando parlano con un utente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e4e83-147">Skype contacts who signed in with their Microsoft account (formerly Windows Live ID) can get some, but not all, features when they are talking to your Skype for Business users.</span></span>
  
|<span data-ttu-id="e4e83-148">**Non disponibile con contatti di Skype**</span><span class="sxs-lookup"><span data-stu-id="e4e83-148">**Available with Skype contacts**</span></span>|<span data-ttu-id="e4e83-149">Conversazioni video</span><span class="sxs-lookup"><span data-stu-id="e4e83-149">**Not available with Skype contacts**</span></span>|
|:-----|:-----|
| <span data-ttu-id="e4e83-150">Messaggi istantanei tra due persone</span><span class="sxs-lookup"><span data-stu-id="e4e83-150">Video conversations</span></span> <br/>  <span data-ttu-id="e4e83-151">Presenza</span><span class="sxs-lookup"><span data-stu-id="e4e83-151">Person-to-person instant messaging</span></span> <br/>  <span data-ttu-id="e4e83-152">Conversazioni di messaggistica istantanea tra più utenti</span><span class="sxs-lookup"><span data-stu-id="e4e83-152">Presence</span></span> <br/> | <span data-ttu-id="e4e83-153">Conversazioni audio e video con tre o più persone</span><span class="sxs-lookup"><span data-stu-id="e4e83-153">Multi-party IM conversations</span></span> <br/>  <span data-ttu-id="e4e83-154">Condivisione di desktop e programmi</span><span class="sxs-lookup"><span data-stu-id="e4e83-154">Audio and video conversations with three or more people</span></span> <br/>  <span data-ttu-id="e4e83-155">Condivisione di desktop e programmi</span><span class="sxs-lookup"><span data-stu-id="e4e83-155">Desktop and program sharing</span></span> <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="e4e83-156">See also</span><span class="sxs-lookup"><span data-stu-id="e4e83-156">Related topics</span></span>

[<span data-ttu-id="e4e83-157">Consentire agli utenti di contattare utenti Skype for Business esterni</span><span class="sxs-lookup"><span data-stu-id="e4e83-157">Allow users to contact external Skype for Business users</span></span>](allow-users-to-contact-external-skype-for-business-users.md)
  
[<span data-ttu-id="e4e83-158">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="e4e83-158">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

  
 