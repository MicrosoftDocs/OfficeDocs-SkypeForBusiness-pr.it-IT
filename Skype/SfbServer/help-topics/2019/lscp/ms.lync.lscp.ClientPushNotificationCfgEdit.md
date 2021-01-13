---
title: Client per dispositivi mobili creare o modificare la configurazione delle notifiche push
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
ROBOTS: NOINDEX, NOFOLLOW
description: La notifica push e la casa di compensazione delle notifiche push (centro PNCH) sono due parti principali della funzionalità per dispositivi mobili. La notifica push è il processo in cui viene inviato un messaggio al centro PNCH. Il messaggio viene mantenuto qui finché non può essere recapitato al client per dispositivi mobili o scade il periodo di timeout.
ms.openlocfilehash: 3c72c5b123a906d74cfeb0a1fef5c1e765fe030c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808746"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="c2f7f-105">Client mobile: creare o modificare la configurazione di notifiche push</span><span class="sxs-lookup"><span data-stu-id="c2f7f-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="c2f7f-106">La notifica push e la casa di compensazione delle notifiche push (centro PNCH) sono due parti principali della funzionalità per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="c2f7f-106">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature.</span></span> <span data-ttu-id="c2f7f-107">La notifica push è il processo in cui viene inviato un messaggio al centro PNCH.</span><span class="sxs-lookup"><span data-stu-id="c2f7f-107">Push notification is the process where a message is sent to the PNCH.</span></span> <span data-ttu-id="c2f7f-108">Il messaggio viene mantenuto qui finché non può essere recapitato al client per dispositivi mobili o scade il periodo di timeout.</span><span class="sxs-lookup"><span data-stu-id="c2f7f-108">The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c2f7f-109">Il periodo di tempo è impostato nella barra di compensazione notifiche push e non può essere configurato dall'utente o dall'amministratore della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c2f7f-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="c2f7f-110">Per abilitare la notifica push, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2f7f-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="c2f7f-111">**Ambito:** Tenere presente l'ambito per questo criterio.</span><span class="sxs-lookup"><span data-stu-id="c2f7f-111">**Scope:** Note the scope for this policy.</span></span> <span data-ttu-id="c2f7f-112">Può essere **globale**, che si applica a tutti gli utenti in questa distribuzione o **sito**, che è solo gli utenti assegnati ai server Home nel sito specificato.</span><span class="sxs-lookup"><span data-stu-id="c2f7f-112">It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c2f7f-113">Le impostazioni criteri applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="c2f7f-113">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="c2f7f-114">La precedenza dei criteri è: criteri utente (la maggior parte influenza) sostituisce un criterio di sito e quindi un criterio sito sostituisce un criterio globale (meno influenza).</span><span class="sxs-lookup"><span data-stu-id="c2f7f-114">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="c2f7f-115">Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="c2f7f-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="c2f7f-116">Selezionare i servizi di notifica push che si desidera abilitare facendo clic sulla casella di controllo per:</span><span class="sxs-lookup"><span data-stu-id="c2f7f-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="c2f7f-117">**Abilita notifica push Microsoft** consentirà la notifica push al centro PNCH basato sul cloud per Windows Phone con l'app Skype for business</span><span class="sxs-lookup"><span data-stu-id="c2f7f-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="c2f7f-118">**Consenti notifiche push di Apple** consentirà la notifica push alla centro PNCH Apple per i dispositivi che eseguono iOS di Apple (ad esempio, iPhone, iPad) e l'utilizzo dell'app Skype for business</span><span class="sxs-lookup"><span data-stu-id="c2f7f-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="c2f7f-119">Dopo aver completato le modifiche del criterio, fare clic su **commit** per salvarle.</span><span class="sxs-lookup"><span data-stu-id="c2f7f-119">When you have completed the edits of the policy, click **Commit** to save your changes.</span></span> <span data-ttu-id="c2f7f-120">Se è necessario eliminare le modifiche apportate, selezionare **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="c2f7f-120">If you need to delete the changes you have made, select **Cancel**.</span></span> <span data-ttu-id="c2f7f-121">Nessuna modifica verrà salvata nel criterio.</span><span class="sxs-lookup"><span data-stu-id="c2f7f-121">No changes will be saved to the policy.</span></span>
    

