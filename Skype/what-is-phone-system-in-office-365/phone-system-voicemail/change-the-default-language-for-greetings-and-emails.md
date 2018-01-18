---
title: Cambiare la lingua predefinita del messaggio di saluto e messaggi di posta elettronica
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Phone System
description: 'Learn how to setup Skype for Busineses to use another language for your organization''s default voicemail greeting. '
ms.openlocfilehash: cfbdcfec46a79c6fcef2aff970a05837460f6e72
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="5b330-103">Cambiare la lingua predefinita del messaggio di saluto e messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="5b330-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="5b330-104">Se si è un [amministratore globale di Office 365](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), è possibile impostare Skype per riprodurre la segreteria telefonica predefinito messaggio di saluto in altre lingue di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5b330-104">If you are an [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="5b330-105">Il messaggio di saluto di sistema predefinito è un'operazione di "lasciare un messaggio di John Smith.</span><span class="sxs-lookup"><span data-stu-id="5b330-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="5b330-106">Dopo il tono, registrare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="5b330-106">After the tone, please record your message.</span></span> <span data-ttu-id="5b330-107">Al termine della registrazione, riappende o premere il tasto cancelletto per visualizzare altre opzioni."</span><span class="sxs-lookup"><span data-stu-id="5b330-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="5b330-108">**Prima di tutto, leggi questa importante informazione:**</span><span class="sxs-lookup"><span data-stu-id="5b330-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="5b330-109">**Le lingue disponibili per l'utente sono determinate dalla posizione dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="5b330-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="5b330-110">Ad esempio, se l'organizzazione si trova negli Stati Uniti, è possibile impostare la lingua predefinita all'inglese e spagnolo.</span><span class="sxs-lookup"><span data-stu-id="5b330-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="5b330-111">Se l'organizzazione si trova in Canada, è possibile scegliere tra inglese e il francese.</span><span class="sxs-lookup"><span data-stu-id="5b330-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="5b330-112">Per un elenco delle lingue supportate, vedere [lingue per i messaggi di saluto di segreteria telefonica e messaggi da Skype per le aziende](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="5b330-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="5b330-p103">**Non c'è modo di cambiare la lingua del sistema per una sola persona nell'organizzazione.** Puoi solo cambiare la lingua del saluto per tutti.</span><span class="sxs-lookup"><span data-stu-id="5b330-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5b330-115">Gli utenti possono modificare i propri messaggio di saluto lingua mediante le relative impostazioni dopo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5b330-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="5b330-116">**Si desidera registrare il messaggio di posta vocale in uscita?**</span><span class="sxs-lookup"><span data-stu-id="5b330-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="5b330-117">Vedere [Controllo Skype per le opzioni e segreteria telefonica aziendale](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="5b330-117">See [Check Skype for Business voicemail and options](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="5b330-118">Cambiare la lingua di sistema per tutti i membri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b330-118">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="5b330-119">Accedere con l'account di [amministratore globale di Office 365](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="5b330-119">Sign in with your [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="5b330-120">Nell'interfaccia di amministrazione, scegliere **Impostazioni** > **profilo dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="5b330-120">In the admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Choose Settings and then choose Organization profile.](../../images/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="5b330-122">Scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5b330-122">Choose **Edit**.</span></span>
    
    ![Choose Edit.](../../images/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="5b330-124">Selezionare una lingua dall'elenco **lingua preferita** per tutti gli utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b330-124">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="5b330-125">Scegliere **Save**.</span><span class="sxs-lookup"><span data-stu-id="5b330-125">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="5b330-126">Articoli correlati per l'amministratore</span><span class="sxs-lookup"><span data-stu-id="5b330-126">Related articles for the admin</span></span>

- [<span data-ttu-id="5b330-127">Che cosa sono i piani di chiamata in Office 365?</span><span class="sxs-lookup"><span data-stu-id="5b330-127">What are Calling Plans in Office 365?</span></span>](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
    
- [<span data-ttu-id="5b330-128">Impostare le tariffe di chiamate</span><span class="sxs-lookup"><span data-stu-id="5b330-128">Set up Calling Plans</span></span>](../../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
    
- [<span data-ttu-id="5b330-129">Pianificare il sistema telefonico in Office 365 con connettività PSTN locale in Skype Business Server 2015 o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b330-129">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server 2015 or Lync Server 2013</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="5b330-130">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5b330-130">Related topics</span></span>

- [<span data-ttu-id="5b330-131">Cambiare la lingua visualizzata e il fuso orario in Office 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="5b330-131">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/en-us/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="5b330-132">[Aggiungere una lingua o impostare le preferenze della lingua in Office 2010 e versioni successive](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span><span class="sxs-lookup"><span data-stu-id="5b330-132">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="5b330-133">Abilitare o cambiare la lingua del layout di tastiera</span><span class="sxs-lookup"><span data-stu-id="5b330-133">Enable or change a keyboard layout language</span></span>](https://support.office.com/en-us/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    

