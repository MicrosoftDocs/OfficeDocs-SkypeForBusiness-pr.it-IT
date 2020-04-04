---
title: Modificare la lingua predefinita per i messaggi di saluto e le e-mail
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Informazioni su come configurare Skype for Businesss per usare un'altra lingua per il messaggio di saluto predefinito della segreteria telefonica dell'organizzazione.
ms.openlocfilehash: 829776be347f2453f3b87a150b19e2334e876f40
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139135"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="86869-103">Modificare la lingua predefinita per i messaggi di saluto e le e-mail</span><span class="sxs-lookup"><span data-stu-id="86869-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="86869-104">Se sei un [amministratore globale di Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), puoi configurare Skype for Business per riprodurre il messaggio di saluto predefinito della segreteria in un'altra lingua.</span><span class="sxs-lookup"><span data-stu-id="86869-104">If you are an [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="86869-105">Il saluto di sistema predefinito è qualcosa come: "Per favore lascia un messaggio a Mario Rossi.</span><span class="sxs-lookup"><span data-stu-id="86869-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="86869-106">Registra il messaggio dopo il segnale acustico.</span><span class="sxs-lookup"><span data-stu-id="86869-106">After the tone, please record your message.</span></span> <span data-ttu-id="86869-107">Al termine della registrazione, interrompi la chiamata o premi il tasto cancelletto per altre opzioni".</span><span class="sxs-lookup"><span data-stu-id="86869-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="86869-108">**Prima di tutto, leggi questa importante informazione:**</span><span class="sxs-lookup"><span data-stu-id="86869-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="86869-109">**Le lingue disponibili sono determinate dalla località dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="86869-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="86869-110">Ad esempio, se la tua organizzazione si trova negli Stati Uniti, puoi impostare inglese o spagnolo come lingua predefinita.</span><span class="sxs-lookup"><span data-stu-id="86869-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="86869-111">Se la tua organizzazione si trova in Canada, puoi scegliere fra inglese e francese.</span><span class="sxs-lookup"><span data-stu-id="86869-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="86869-112">Per l'elenco delle lingue disponibili, vedi la sezione [Lingue per saluti e messaggi della segreteria telefonica da Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="86869-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="86869-p103">**Non c'è modo di cambiare la lingua del sistema per una sola persona nell'organizzazione.** Puoi solo cambiare la lingua del saluto per tutti.</span><span class="sxs-lookup"><span data-stu-id="86869-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="86869-115">Gli utenti possono modificare la lingua del saluto attraverso le impostazioni dopo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="86869-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="86869-116">**Vuoi registrare il messaggio in uscita della segreteria telefonica?**</span><span class="sxs-lookup"><span data-stu-id="86869-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="86869-117">Vedi [Controllare le opzioni e la segreteria telefonica di Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="86869-117">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="86869-118">Per Microsoft teams-gli utenti possono modificare le impostazioni della segreteria telefonica dalle [impostazioni del client desktop teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="86869-118">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="86869-119">**Si desidera modificare la lingua della richiesta della segreteria telefonica?**</span><span class="sxs-lookup"><span data-stu-id="86869-119">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="86869-120">Per Skype for business- [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) e scegli una nuova lingua in **lingua prompt**.</span><span class="sxs-lookup"><span data-stu-id="86869-120">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="86869-121">Per Microsoft teams-gli utenti possono modificare le impostazioni della segreteria telefonica dalle [impostazioni del client desktop teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="86869-121">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="86869-122">Cambiare la lingua di sistema per tutti i membri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="86869-122">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="86869-123">Accedere con l'account di [amministratore globale di Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) all'indirizzo[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="86869-123">Sign in with your [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="86869-124">Nell'interfaccia di amministrazione di Microsoft 365 scegliere **Impostazioni** > **organizzazione profilo**.</span><span class="sxs-lookup"><span data-stu-id="86869-124">In the Microsoft 365 admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Screenshot che Mostra come scegliere le impostazioni e quindi profilo organizzazione.](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="86869-126">Scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="86869-126">Choose **Edit**.</span></span>
    
    ![Screenshot che mostra l'opzione di modifica.](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="86869-128">Scegli una lingua dall'elenco **Lingua preferita** per tutti i membri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="86869-128">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="86869-129">Scegli **Salva**.</span><span class="sxs-lookup"><span data-stu-id="86869-129">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="86869-130">Articoli correlati per l'amministratore</span><span class="sxs-lookup"><span data-stu-id="86869-130">Related articles for the admin</span></span>

- [<span data-ttu-id="86869-131">Sistema telefonico e piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="86869-131">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="86869-132">Configurare i piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="86869-132">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="86869-133">Pianificare il sistema telefonico in Office 365 con connettività PSTN locale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="86869-133">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="86869-134">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="86869-134">Related topics</span></span>

- [<span data-ttu-id="86869-135">Cambiare la lingua visualizzata e il fuso orario in Office 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="86869-135">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="86869-136">[Aggiungere una lingua o impostare le preferenze di lingua di Office 2010 e versioni successive](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="86869-136">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="86869-137">Abilitare o cambiare la lingua del layout di tastiera</span><span class="sxs-lookup"><span data-stu-id="86869-137">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 
