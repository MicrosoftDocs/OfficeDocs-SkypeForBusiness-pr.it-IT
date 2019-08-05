---
title: Configurazione delle notifiche push del client mobile
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: Per configurare le notifiche push Microsoft e le notifiche push di Apple, è necessario creare un criterio per definire i tipi di notifica push necessari.
ms.openlocfilehash: 0211b3a8306297bd68402ad47d3c243541adf2bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195162"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="040cd-103">Client mobile: configurazione della notifica push</span><span class="sxs-lookup"><span data-stu-id="040cd-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="040cd-104">Per configurare le **notifiche push Microsoft** e le **notifiche push di Apple**, è necessario creare un criterio per definire i tipi di notifica push necessari.</span><span class="sxs-lookup"><span data-stu-id="040cd-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="040cd-105">Nella schermata principale di configurazione è possibile fare clic su **Aggiorna** per aggiornare e ripopolare l'elenco dei criteri.</span><span class="sxs-lookup"><span data-stu-id="040cd-105">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies.</span></span> <span data-ttu-id="040cd-106">Viene fornita una casella di ricerca per limitare l'elenco dei criteri visualizzati.</span><span class="sxs-lookup"><span data-stu-id="040cd-106">A search box is provided for narrowing the list of displayed policies.</span></span> <span data-ttu-id="040cd-107">Quando si digita il nome che si sta cercando, l'elenco dei criteri si restringe automaticamente.</span><span class="sxs-lookup"><span data-stu-id="040cd-107">As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="040cd-108">Le impostazioni dei criteri applicate a un livello di criteri possono eseguire l'override delle impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="040cd-108">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="040cd-109">La precedenza dei criteri è: criteri utente (la maggior parte delle influenze) esegue l'override di un criterio del sito e quindi un criterio del sito sostituisce un criterio globale (almeno l'influenza).</span><span class="sxs-lookup"><span data-stu-id="040cd-109">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="040cd-110">Ciò significa che l'impostazione del criterio è più vicina all'oggetto che il criterio sta influenzando, più influenza ha sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="040cd-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="040cd-111">Sono disponibili due selezioni per la creazione e la modifica dei criteri:</span><span class="sxs-lookup"><span data-stu-id="040cd-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="040cd-112">**Nuovo**: fare clic per creare un nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="040cd-112">**New**: Click to create a new policy.</span></span> <span data-ttu-id="040cd-113">È necessario specificare un sito per cui applicare i criteri.</span><span class="sxs-lookup"><span data-stu-id="040cd-113">You must provide a site for the policy to apply to.</span></span> <span data-ttu-id="040cd-114">Le impostazioni per la notifica push vengono quindi configurate.</span><span class="sxs-lookup"><span data-stu-id="040cd-114">You then configure the settings for the push notification.</span></span> <span data-ttu-id="040cd-115">Per la **configurazione delle notifiche push**, è possibile creare solo criteri per i siti già creati.</span><span class="sxs-lookup"><span data-stu-id="040cd-115">For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="040cd-116">**Modifica**: selezionare un criterio e fare clic su modifica per selezionare un'azione da un elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="040cd-116">**Edit**: Select a policy and click Edit to select an action from a drop-down.</span></span> <span data-ttu-id="040cd-117">È possibile modificare solo i siti già creati o modificare i criteri globali:</span><span class="sxs-lookup"><span data-stu-id="040cd-117">You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="040cd-118">**Mostra dettagli...**: Visualizza le informazioni sui criteri attualmente selezionati.</span><span class="sxs-lookup"><span data-stu-id="040cd-118">**Show details…**: Displays information about the currently selected policy.</span></span> <span data-ttu-id="040cd-119">Sarà possibile apportare modifiche ai criteri esistenti.</span><span class="sxs-lookup"><span data-stu-id="040cd-119">You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="040cd-120">**Selezionare tutto**: se si hanno diversi criteri e occorre selezionare tutti i criteri, fare clic su Seleziona tutto</span><span class="sxs-lookup"><span data-stu-id="040cd-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="040cd-121">**Elimina**: verrà rimosso il criterio selezionato.</span><span class="sxs-lookup"><span data-stu-id="040cd-121">**Delete**: Will remove the selected policy.</span></span> <span data-ttu-id="040cd-122">Se si usa **Seleziona tutto** ed **Elimina** verranno rimossi tutti i criteri</span><span class="sxs-lookup"><span data-stu-id="040cd-122">Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="040cd-123">Non è possibile eliminare i criteri **globali** predefiniti.</span><span class="sxs-lookup"><span data-stu-id="040cd-123">You cannot delete the default **Global** policy.</span></span> <span data-ttu-id="040cd-124">Se si tenta di eliminarlo, verrà visualizzato un avviso che indica che i criteri globali sono stati restituiti ai valori predefiniti, ovvero tutte le impostazioni sono deselezionate, ma non è possibile rimuoverlo.</span><span class="sxs-lookup"><span data-stu-id="040cd-124">If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="040cd-125">La creazione di un nuovo criterio o la modifica di un criterio esistente è associata a due azioni:</span><span class="sxs-lookup"><span data-stu-id="040cd-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="040cd-126">**Commit** L'azione di commit crea o aggiorna il criterio e salva le modifiche</span><span class="sxs-lookup"><span data-stu-id="040cd-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="040cd-127">**Annulla** L'azione Annulla Elimina tutte le modifiche apportate dopo l'ultima azione di commit.</span><span class="sxs-lookup"><span data-stu-id="040cd-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="040cd-128">Se si Annulla, le modifiche apportate andranno perse.</span><span class="sxs-lookup"><span data-stu-id="040cd-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="040cd-129">Sono possibili due impostazioni per la **configurazione della notifica push**.</span><span class="sxs-lookup"><span data-stu-id="040cd-129">Two settings are possible for **Push Notification Configuration**.</span></span> <span data-ttu-id="040cd-130">Le impostazioni sono associate ai servizi di notifica push per Microsoft e per Apple.</span><span class="sxs-lookup"><span data-stu-id="040cd-130">The settings are associated with the push notification services for Microsoft and for Apple.</span></span> <span data-ttu-id="040cd-131">È possibile abilitare la notifica push per un servizio qualsiasi selezionando la casella di controllo accanto al nome del servizio.</span><span class="sxs-lookup"><span data-stu-id="040cd-131">You enable push notification for either service by selecting the check box next to the name of the service.</span></span> <span data-ttu-id="040cd-132">Per deselezionare la casella di controllo, è possibile selezionarla.</span><span class="sxs-lookup"><span data-stu-id="040cd-132">You can clear the check box by selecting it to clear it.</span></span> <span data-ttu-id="040cd-133">Dopo aver eseguito le selezioni, è possibile eseguire il commit o l'annullamento.</span><span class="sxs-lookup"><span data-stu-id="040cd-133">Once you have made your selections, you either commit or cancel.</span></span> <span data-ttu-id="040cd-134">Se si fa clic su commit, le modifiche apportate al criterio verranno salvate.</span><span class="sxs-lookup"><span data-stu-id="040cd-134">Clicking commit will save the changes to the policy.</span></span>
  

