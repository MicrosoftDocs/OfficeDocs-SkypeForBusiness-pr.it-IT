---
title: Configurazione della notifica push per i client mobili
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Per configurare le Notifiche Push di Microsoft e le Notifiche Push di Apple, è necessario creare un criterio per definire quali tipi di notifiche push sono necessari.
ms.openlocfilehash: 493c8138e7c5dcaeab154ce1a44054cc082d1672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810876"
---
# <a name="mobile-client-push-notification-configuration"></a><span data-ttu-id="1711a-103">Client dispositivo mobile: configurazione di notifiche push</span><span class="sxs-lookup"><span data-stu-id="1711a-103">Mobile Client: Push Notification Configuration</span></span>
 
<span data-ttu-id="1711a-104">Per configurare le **Notifiche Push di Microsoft** e le **Notifiche Push di Apple**, è necessario creare un criterio per definire quali tipi di notifiche push sono necessari.</span><span class="sxs-lookup"><span data-stu-id="1711a-104">To configure the **Microsoft push notifications** and **Apple push notifications**, you must create a policy to define which types of push notification you require.</span></span>
  
<span data-ttu-id="1711a-p101">Nella schermata di configurazione principale è possibile fare clic su **Aggiorna** per aggiornare e popolare di nuovo l'elenco di criteri. È disponibile una casella di ricerca per limitare l'elenco di criteri visualizzati. Man mano che si digita il nome da cercare, l'elenco di criteri si restringe automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1711a-p101">On the main configuration screen, you can click **Refresh** to refresh and re-populate the list of policies. A search box is provided for narrowing the list of displayed policies. As you type the name that you are searching for, the list of policies narrows automatically.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1711a-108">Le impostazioni criteri applicate a un determinato livello di criteri possono sostituire le impostazioni applicate a un altro livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="1711a-108">Policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="1711a-109">La precedenza dei criteri è: criteri utente (la maggior parte influenza) sostituisce un criterio di sito e quindi un criterio sito sostituisce un criterio globale (meno influenza).</span><span class="sxs-lookup"><span data-stu-id="1711a-109">Policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="1711a-110">Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="1711a-110">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> 
  
<span data-ttu-id="1711a-111">Sono disponibili due selezioni per la creazione e la modifica dei criteri:</span><span class="sxs-lookup"><span data-stu-id="1711a-111">Two selections are available for policy creation and editing:</span></span>
  
1. <span data-ttu-id="1711a-p103">**Nuovo**: fare clic su questa opzione per creare un nuovo criterio. È necessario fornire un sito a cui applicare il criterio e quindi configurare le impostazioni per le notifiche push. Per **Configurazione notifica Push** è possibile creare criteri solo per i siti già creati.</span><span class="sxs-lookup"><span data-stu-id="1711a-p103">**New**: Click to create a new policy. You must provide a site for the policy to apply to. You then configure the settings for the push notification. For **Push Notification Configuration**, you can only create policies for Sites that you have already created.</span></span>
    
2. <span data-ttu-id="1711a-p104">**Modifica**: selezionare un criterio e fare clic su Modifica per selezionare un'azione dal menu a discesa. È possibile modificare solo i siti già creati o modificare il criterio Globale.</span><span class="sxs-lookup"><span data-stu-id="1711a-p104">**Edit**: Select a policy and click Edit to select an action from a drop-down. You can only edit sites that you have already created or edit the Global policy:</span></span>
    
   - <span data-ttu-id="1711a-p105">**Mostra dettagli…**: mostra informazioni sul criterio attualmente selezionato. È possibile modificare solo il criterio esistente.</span><span class="sxs-lookup"><span data-stu-id="1711a-p105">**Show details…**: Displays information about the currently selected policy. You will be able to make changes to the existing policy.</span></span>
    
   - <span data-ttu-id="1711a-120">**Seleziona tutto**: se sono disponibili alcuni criteri ed è necessario selezionarli tutti, fare clic su Seleziona tutto.</span><span class="sxs-lookup"><span data-stu-id="1711a-120">**Select all**: If you have a number of policies and need to select all policies, click Select all</span></span>
    
   - <span data-ttu-id="1711a-p106">**Elimina**: rimuove il criterio selezionato. Usando **Seleziona tutto** ed **Elimina** si rimuoveranno tutti i criteri.</span><span class="sxs-lookup"><span data-stu-id="1711a-p106">**Delete**: Will remove the selected policy. Using **Select all** and **Delete** will remove all policies</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="1711a-p107">Non è invece possibile eliminare il criterio **Globale**. Se si tenta di eliminarlo, verrà segnalato che tale criterio è stato ripristinato ai valori predefiniti (ovvero tutte le impostazioni sono state cancellate), ma non può essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="1711a-p107">You cannot delete the default **Global** policy. If you attempt to delete it, you will be notified that the Global policy has been returned to the default values (that is, all settings are cleared), but the policy cannot be removed.</span></span>
  
<span data-ttu-id="1711a-125">La creazione di un nuovo criterio o la modifica di un criterio esistente sono associate a due azioni:</span><span class="sxs-lookup"><span data-stu-id="1711a-125">Creating a new policy or editing an existing policy is associated with two actions:</span></span>
  
- <span data-ttu-id="1711a-126">**Commit** L'azione commit consente di creare o aggiornare il criterio e di salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1711a-126">**Commit** The commit action creates or updates the policy and saves the changes</span></span>
    
- <span data-ttu-id="1711a-127">**Annulla** L'azione Annulla rimuove tutte le modifiche apportate dopo l'ultima operazione di commit.</span><span class="sxs-lookup"><span data-stu-id="1711a-127">**Cancel** The cancel action discards any changes that have been made since the last commit action.</span></span> <span data-ttu-id="1711a-128">Se si sceglie di annullare, tutte le modifiche eseguite andranno perse.</span><span class="sxs-lookup"><span data-stu-id="1711a-128">If you cancel, any changes made will be lost.</span></span>
    
<span data-ttu-id="1711a-p109">Sono possibili due impostazioni per **Configurazione notifica Push** che sono associate ai servizi di notifica Push per Microsoft e per Apple. Per abilitare la notifica Push per questi servizi, selezionare la casella di controllo accanto al nome del servizio. È possibile deselezionare la casella di controllo facendo clic su di essa. Dopo aver eseguito le selezioni, eseguire il commit o annullare. Facendo clic su Commit si salveranno le modifiche al criterio.</span><span class="sxs-lookup"><span data-stu-id="1711a-p109">Two settings are possible for **Push Notification Configuration**. The settings are associated with the push notification services for Microsoft and for Apple. You enable push notification for either service by selecting the check box next to the name of the service. You can clear the check box by selecting it to clear it. Once you have made your selections, you either commit or cancel. Clicking commit will save the changes to the policy.</span></span>
  

