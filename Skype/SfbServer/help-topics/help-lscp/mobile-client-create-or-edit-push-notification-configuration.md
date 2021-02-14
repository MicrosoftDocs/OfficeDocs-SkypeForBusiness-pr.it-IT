---
title: Creazione o modifica della configurazione delle notifiche Push da parte del client mobile
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: La notifica Push e il PNCH (Push Notification Clearing House) sono due parti chiave della funzionalità per dispositivi mobili. La notifica push è il processo in cui un messaggio viene inviato al PNCH. Il messaggio viene mantenuto qui fino a quando non può essere recapitato al client mobile o fino alla scadenza del periodo di timeout.
ms.openlocfilehash: 0cd2b17f764891dbb1ad89ada27f6be0b6246ba0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810886"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a><span data-ttu-id="80154-105">Client mobile: creare o modificare la configurazione di notifiche push</span><span class="sxs-lookup"><span data-stu-id="80154-105">Mobile Client: Create or Edit Push Notification Configuration</span></span>
 
<span data-ttu-id="80154-106">La notifica Push e il PNCH (Push Notification Clearing House) sono due parti chiave della funzionalità per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="80154-106">Push Notification and the Push Notification Clearing House (PNCH) are two key parts of the mobility feature.</span></span> <span data-ttu-id="80154-107">La notifica push è il processo in cui un messaggio viene inviato al PNCH.</span><span class="sxs-lookup"><span data-stu-id="80154-107">Push notification is the process where a message is sent to the PNCH.</span></span> <span data-ttu-id="80154-108">Il messaggio viene mantenuto qui fino a quando non può essere recapitato al client mobile o fino alla scadenza del periodo di timeout.</span><span class="sxs-lookup"><span data-stu-id="80154-108">The message is held here until it can be delivered to the mobile client, or the timeout period expires.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="80154-109">Il periodo di tempo viene impostato presso il centro di raccolta delle notifiche Push e non è configurabile dall'utente o dall'amministratore della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="80154-109">The time period is set at the Push Notification Clearing House and is not configurable by the user or the administrator of your deployment.</span></span> 
  
<span data-ttu-id="80154-110">Per abilitare la notifica Push, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="80154-110">To enable Push Notification, you do the following:</span></span>
  
1. <span data-ttu-id="80154-111">**Ambito:** Prendere nota dell'ambito di questo criterio.</span><span class="sxs-lookup"><span data-stu-id="80154-111">**Scope:** Note the scope for this policy.</span></span> <span data-ttu-id="80154-112">Può essere **Global**, applicabile a tutti gli utenti della distribuzione, oppure **Site**, ovvero solo gli utenti assegnati ai server principali del sito specificato.</span><span class="sxs-lookup"><span data-stu-id="80154-112">It can either be **Global**, which applies to all users in this deployment, or **Site**, which is only users assigned to home servers in the specified site.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="80154-113">Le impostazioni criteri applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="80154-113">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="80154-114">La precedenza dei criteri è: i criteri utente (maggiore influenza) sostituiscono i criteri sito, quindi i criteri sito sostituiscono i criteri globali (meno influenza).</span><span class="sxs-lookup"><span data-stu-id="80154-114">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="80154-115">Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="80154-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
2. <span data-ttu-id="80154-116">Selezionare i servizi di notifica Push che si desidera abilitare facendo clic sulla casella di controllo per:</span><span class="sxs-lookup"><span data-stu-id="80154-116">Select which push notification services you want to enable by clicking the check box for:</span></span>
    
   - <span data-ttu-id="80154-117">**Abilitare la notifica push Microsoft** abiliterà la notifica push al PNCH basato sul cloud per Windows Phone con l'app Skype for Business</span><span class="sxs-lookup"><span data-stu-id="80154-117">**Enable Microsoft push notification** will enable the push notification to the cloud-based PNCH for Windows Phone with the Skype for Business app</span></span>
    
   - <span data-ttu-id="80154-118">**Abilita la** notifica push Apple abiliterà la notifica push al PNCH Apple per i dispositivi che eseguono iOS di Apple (ad esempio, iPhone, iPad) e l'uso dell'app Skype for Business</span><span class="sxs-lookup"><span data-stu-id="80154-118">**Enable Apple push notification** will enable the push notification to the Apple PNCH for devices running Apple's iOS (for example, iPhone, iPad) and using the Skype for Business app</span></span>
    
3. <span data-ttu-id="80154-119">Dopo aver completato le modifiche del criterio, fare clic su **Salva** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="80154-119">When you have completed the edits of the policy, click **Commit** to save your changes.</span></span> <span data-ttu-id="80154-120">Se è necessario eliminare le modifiche apportate, selezionare **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="80154-120">If you need to delete the changes you have made, select **Cancel**.</span></span> <span data-ttu-id="80154-121">Nessuna modifica verrà salvata nel criterio.</span><span class="sxs-lookup"><span data-stu-id="80154-121">No changes will be saved to the policy.</span></span>
    

