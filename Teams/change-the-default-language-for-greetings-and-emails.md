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
description: Informazioni su come configurare Microsoft Teams e Skype for Business usare un'altra lingua per il messaggio di saluto della segreteria telefonica predefinito dell'organizzazione.
ms.openlocfilehash: f211a5e160ce05707a454e5100409840e4c781ac
ms.sourcegitcommit: eca3f5e83e4a07be197936db19f539cbfa2c2bd2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "52804523"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="6443b-103">Modificare la lingua predefinita per i messaggi di saluto e le e-mail</span><span class="sxs-lookup"><span data-stu-id="6443b-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="6443b-104">Se si è un [amministratore](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)globale, è possibile configurare Skype for Business per riprodurre il messaggio di saluto predefinito della segreteria telefonica in un'altra lingua.</span><span class="sxs-lookup"><span data-stu-id="6443b-104">If you are a [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="6443b-105">Il saluto di sistema predefinito è qualcosa come: "Per favore lascia un messaggio a Mario Rossi.</span><span class="sxs-lookup"><span data-stu-id="6443b-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="6443b-106">Registra il messaggio dopo il segnale acustico.</span><span class="sxs-lookup"><span data-stu-id="6443b-106">After the tone, please record your message.</span></span> <span data-ttu-id="6443b-107">Al termine della registrazione, interrompi la chiamata o premi il tasto cancelletto per altre opzioni".</span><span class="sxs-lookup"><span data-stu-id="6443b-107">When you finish recording, hang up, or press the pound key for more options."</span></span>
  
 <span data-ttu-id="6443b-108">**Prima di tutto, leggi questa importante informazione:**</span><span class="sxs-lookup"><span data-stu-id="6443b-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="6443b-109">**Le lingue disponibili sono determinate dalla località dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="6443b-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="6443b-110">Ad esempio, se la tua organizzazione si trova negli Stati Uniti, puoi impostare inglese o spagnolo come lingua predefinita.</span><span class="sxs-lookup"><span data-stu-id="6443b-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="6443b-111">Se la tua organizzazione si trova in Canada, puoi scegliere fra inglese e francese.</span><span class="sxs-lookup"><span data-stu-id="6443b-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="6443b-112">Per un elenco delle lingue supportate in Teams e Skype for Business, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="6443b-112">For a list of supported languages in Teams and Skype for Business, see the following:</span></span>
  - [<span data-ttu-id="6443b-113">Microsoft Teams lingue supportate</span><span class="sxs-lookup"><span data-stu-id="6443b-113">Microsoft Teams supported languages</span></span>](languages-for-voicemail-greetings-and-messages.md)
  - [<span data-ttu-id="6443b-114">Skype for Business lingue supportate</span><span class="sxs-lookup"><span data-stu-id="6443b-114">Skype for Business supported languages</span></span>](/skypeforbusiness/what-is-phone-system-in-office-365/phone-system-voicemail/languages-for-voicemail-greetings-and-messages)

- <span data-ttu-id="6443b-115">**Modifica delle lingue per i messaggi di saluto e i messaggi della segreteria telefonica dei singoli utenti.**</span><span class="sxs-lookup"><span data-stu-id="6443b-115">**Changing languages for individual user's voicemail greeting and voicemail messages.**</span></span> <span data-ttu-id="6443b-116">È possibile cambiare la lingua preferita per gli utenti, che cambierà la lingua dei messaggi di saluto della segreteria telefonica e della segreteria telefonica inviati alla cassetta postale Outlook messaggi.</span><span class="sxs-lookup"><span data-stu-id="6443b-116">You can change the preferred language for users, which will change the language of their voicemail greeting and voicemail messages sent to their Outlook mailbox.</span></span> <span data-ttu-id="6443b-117">Per altre informazioni, vedere Come impostare le impostazioni della lingua e dell'area [geografica Microsoft 365 o Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span><span class="sxs-lookup"><span data-stu-id="6443b-117">For more information, see [How to set language and region settings for Microsoft 365 or Office 365](/office365/troubleshoot/access-management/set-language-and-region).</span></span>

  > [!NOTE]
  > <span data-ttu-id="6443b-118">Gli utenti possono modificare la lingua del saluto attraverso le impostazioni dopo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="6443b-118">Users can change their own greeting language through their settings after they sign in.</span></span> <span data-ttu-id="6443b-119">Per altre informazioni, vedere [Cambiare la lingua di visualizzazione e il](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US) fuso orario in Microsoft 365 for Business</span><span class="sxs-lookup"><span data-stu-id="6443b-119">For more information, see [Change your display language and time zone in Microsoft 365 for Business](https://support.office.com/article/change-your-display-language-and-time-zone-in-microsoft-365-for-business-6f238bff-5252-441e-b32b-655d5d85d15b?ui=en-US&rs=en-US&ad=US)</span></span>
  
- <span data-ttu-id="6443b-120">**Vuoi registrare il messaggio in uscita della segreteria telefonica?**</span><span class="sxs-lookup"><span data-stu-id="6443b-120">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="6443b-121">Vedi [Controllare le opzioni e la segreteria telefonica di Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="6443b-121">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="6443b-122">Per Microsoft Teams - Gli utenti possono modificare le impostazioni della segreteria telefonica dalle Teams [del client desktop](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="6443b-122">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="6443b-123">**Si vuole cambiare la lingua del prompt della segreteria telefonica?**</span><span class="sxs-lookup"><span data-stu-id="6443b-123">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="6443b-124">Per Skype for Business e [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) scegliere una nuova lingua in Lingua **richiesta.**</span><span class="sxs-lookup"><span data-stu-id="6443b-124">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="6443b-125">Per Microsoft Teams - Gli utenti possono modificare il messaggio di saluto della segreteria telefonica dalle Teams [del client desktop](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="6443b-125">For Microsoft Teams - Users can change their voicemail greeting from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="6443b-126">Cambiare la lingua di sistema per tutti i membri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6443b-126">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="6443b-127">Accedere con l'account [di amministratore globale](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) all'indirizzo [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="6443b-127">Sign in with your [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="6443b-128">Nell'Microsoft 365 di amministrazione scegliere **Impostazioni**  >    >  **Impostazioni'organizzazione.**</span><span class="sxs-lookup"><span data-stu-id="6443b-128">In the Microsoft 365 admin center, choose **Settings** > **Settings** > **Organization profile**.</span></span>

     ![Screenshot che mostra la scelta Impostazioni e quindi profilo organizzazione.](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="6443b-130">Scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6443b-130">Choose **Edit**.</span></span>

    ![Screenshot che mostra l'opzione Modifica.](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="6443b-132">Scegli una lingua dall'elenco **Lingua preferita** per tutti i membri dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6443b-132">Select a language from the **Preferred language** list for everyone in your organization.</span></span>

5. <span data-ttu-id="6443b-133">Scegli **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6443b-133">Choose **Save**.</span></span>

## <a name="related-articles-for-the-admin"></a><span data-ttu-id="6443b-134">Articoli correlati per l'amministratore</span><span class="sxs-lookup"><span data-stu-id="6443b-134">Related articles for the admin</span></span>

- [<span data-ttu-id="6443b-135">Sistema telefonico e piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="6443b-135">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="6443b-136">Configurare i piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="6443b-136">Set up Calling Plans</span></span>](set-up-calling-plans.md)

- [<span data-ttu-id="6443b-137">Pianificare Sistema telefonico in Microsoft 365 o Office 365 con la connettività PSTN locale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6443b-137">Plan Phone System in Microsoft 365 or Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)

## <a name="related-topics"></a><span data-ttu-id="6443b-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6443b-138">Related topics</span></span>

- [<span data-ttu-id="6443b-139">Modificare la lingua di visualizzazione e il fuso orario in Microsoft 365 o Office 365 for Business</span><span class="sxs-lookup"><span data-stu-id="6443b-139">Change your display language and time zone in Microsoft 365 or Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)

- <span data-ttu-id="6443b-140">[Aggiungere una lingua o impostare le preferenze di lingua di Office 2010 e versioni successive](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="6443b-140">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>

- [<span data-ttu-id="6443b-141">Abilitare o cambiare la lingua del layout di tastiera</span><span class="sxs-lookup"><span data-stu-id="6443b-141">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
