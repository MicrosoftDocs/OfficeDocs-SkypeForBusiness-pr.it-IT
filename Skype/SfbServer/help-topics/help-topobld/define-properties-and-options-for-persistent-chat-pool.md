---
title: Definire proprietà e opzioni per il pool Persistent Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'È possibile configurare le opzioni per il server Chat persistente o per il pool di server Chat persistente definendo le proprietà seguenti:'
ms.openlocfilehash: acc80c76e79364be730ec56a2b64e5dcd001f661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818426"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="46064-103">Definire le proprietà e le opzioni per il pool di Chat persistente</span><span class="sxs-lookup"><span data-stu-id="46064-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="46064-104">È possibile configurare le opzioni per il server Chat persistente o per il pool di server Chat persistente definendo le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="46064-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="46064-105">**Nome visualizzato del pool di chat persistente**: proprietà obbligatoria che definisce un nome descrittivo che verrà visualizzato per il server Chat persistente o per il pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="46064-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="46064-106">**Porta di chat persistente**: proprietà obbligatoria che definirà il numero di porta che questo server Chat persistente o il pool di server Chat persistente terrà in attesa.</span><span class="sxs-lookup"><span data-stu-id="46064-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="46064-107">**Consenti conformità**: selezionare la casella di controllo se si prevede di distribuire e implementare la funzionalità e il database di conformità di Persistent Chat opzionali.</span><span class="sxs-lookup"><span data-stu-id="46064-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="46064-108">**Utilizzare gli archivi SQL Server di backup per abilitare il ripristino di emergenza**: selezionare questa casella di controllo se si prevede di distribuire e implementare il ripristino di emergenza degli archivi SQL Server di chat persistente da un set di backup configurato di archivi in un altro SQL Server.</span><span class="sxs-lookup"><span data-stu-id="46064-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="46064-109">Per ulteriori informazioni, vedere [configurare la disponibilità elevata e il ripristino di emergenza per il server Chat persistente in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="46064-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="46064-110">Questa opzione è disponibile solo per pool con più server.</span><span class="sxs-lookup"><span data-stu-id="46064-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="46064-111">**Utilizzare questo pool come predefinito per il sito \<site that this server or pool is being configured in\>**: selezionare questa casella di controllo se si tratta del server Chat persistente predefinito o del pool di server Chat persistente per il sito.</span><span class="sxs-lookup"><span data-stu-id="46064-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="46064-112">È necessario disporre di un server di chat persistente predefinito o pol per sito.</span><span class="sxs-lookup"><span data-stu-id="46064-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="46064-113">Se la topologia include più siti, viene visualizzata una casella di controllo anche per **Usa questo pool come predefinito per tutti i siti**.</span><span class="sxs-lookup"><span data-stu-id="46064-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="46064-114">Fare clic su **Indietro** per tornare alla precedente finestra di dialogo per la definizione del pool.</span><span class="sxs-lookup"><span data-stu-id="46064-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="46064-115">Fare clic su **Avanti** dopo aver immesso le opzioni per il pool per continuare con la definizione del pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="46064-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="46064-116">Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool Persistent Chat**.</span><span class="sxs-lookup"><span data-stu-id="46064-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="46064-117">Fare clic su **Guida** per accedere alla Guida sensibile al contesto, come questa pagina.</span><span class="sxs-lookup"><span data-stu-id="46064-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="46064-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46064-118">See also</span></span>

[<span data-ttu-id="46064-119">Pianificare il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="46064-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="46064-120">Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="46064-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
