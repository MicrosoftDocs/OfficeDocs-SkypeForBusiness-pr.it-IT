---
title: Creazione o modifica della configurazione delle notifiche push tramite client mobile
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: La notifica Push e il fornitore di servizi di accesso a terze parti per notifiche Push sono due elementi chiave della funzionalità per dispositivi mobili. La notifica Push è il processo di invio di un messaggio a un fornitore di servizi di accesso a terze parti per notifiche Push, che trattiene i messaggi fino a quando sarà possibile recapitarli al client mobile o fino allo scadere del periodo di timeout.
ms.openlocfilehash: 3a15e88e40b37da4570d04a93ef13a793d6dabaf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195166"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="5c482-105">Client mobile: creare o modificare la configurazione di notifiche Push</span><span class="sxs-lookup"><span data-stu-id="5c482-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="5c482-p102">La notifica Push e il fornitore di servizi di accesso a terze parti per notifiche Push sono due elementi chiave della funzionalità per dispositivi mobili. La notifica Push è il processo di invio di un messaggio a un fornitore di servizi di accesso a terze parti per notifiche Push, che trattiene i messaggi fino a quando sarà possibile recapitarli al client mobile o fino allo scadere del periodo di timeout.</span><span class="sxs-lookup"><span data-stu-id="5c482-p102">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature. Push notification is the process where a message is sent to the PNCH. The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5c482-109">Il periodo di timeout è impostato dal fornitore di servizi di accesso a terze parti per notifiche Push e non può essere configurato dall'utente o dall'amministratore della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5c482-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="5c482-110">Per abilitare la notifica Push, si eseguono le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5c482-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="5c482-p103">**Ambito:** notare l'ambito di questo criterio. Può essere **Globale**, ovvero applicabile a tutti gli utenti in questa distribuzione, oppure **Sito**, ovvero relativo solo agli utenti assegnati ai server principali del sito specificato.</span><span class="sxs-lookup"><span data-stu-id="5c482-p103">**Scope:** Note the scope for this policy. It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="5c482-113">Le impostazioni dei criteri applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="5c482-113">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="5c482-114">La precedenza dei criteri è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza).</span><span class="sxs-lookup"><span data-stu-id="5c482-114">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="5c482-115">Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="5c482-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="5c482-116">Selezionare i servizi di notifica Push da abilitare, facendo clic sulla relativa casella di controllo:</span><span class="sxs-lookup"><span data-stu-id="5c482-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="5c482-117">**Abilitare la notifica push Microsoft** consentirà la notifica push al centro PNCH basato su cloud per Windows Phone con l'app Skype for business</span><span class="sxs-lookup"><span data-stu-id="5c482-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="5c482-118">**Abilitare la notifica push Apple** consentirà la notifica push all'Apple centro PNCH per i dispositivi che usano iOS di Apple, ad esempio iPhone, iPad, e l'uso dell'app Skype for business</span><span class="sxs-lookup"><span data-stu-id="5c482-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="5c482-p105">Al termine delle modifiche del criterio, fare clic su **Commit** per salvare le modifiche. Per eliminare le modifiche eseguite, selezionare **Annulla**. Non verranno salvate modifiche al criterio.</span><span class="sxs-lookup"><span data-stu-id="5c482-p105">When you have completed the edits of the policy, click **Commit** to save your changes. If you need to delete the changes you have made, select **Cancel**. No changes will be saved to the policy.</span></span>
    

