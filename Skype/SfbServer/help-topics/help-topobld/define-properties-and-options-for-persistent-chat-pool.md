---
title: Definire proprietà e opzioni per il pool Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Si configurano le opzioni per il server di chat persistente o per il pool di server di chat persistente definendo le proprietà seguenti:'
ms.openlocfilehash: f719a4c76be88dd571c551645bacd13ef22e9a19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195745"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="632ef-103">Definire proprietà e opzioni per il pool Chat persistente</span><span class="sxs-lookup"><span data-stu-id="632ef-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="632ef-104">Si configurano le opzioni per il server di chat persistente o per il pool di server di chat persistente definendo le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="632ef-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="632ef-105">**Nome visualizzato del pool di chat persistente**: una proprietà obbligatoria che definisce un nome descrittivo dell'utente che verrà visualizzato per questo server di chat persistente o per il pool di server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="632ef-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="632ef-106">**Porta della chat persistente**: una proprietà obbligatoria che definirà il numero di porta che verrà ascoltato da questo server di chat persistente o dal pool di server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="632ef-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="632ef-107">**Abilitare la conformità**: selezionare la casella di controllo se si prevede di distribuire e implementare la funzionalità e il database di conformità delle chat persistenti facoltative.</span><span class="sxs-lookup"><span data-stu-id="632ef-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="632ef-108">**Usare gli archivi di SQL Server di backup per abilitare il ripristino di emergenza**: selezionare questa casella di controllo se si prevede di distribuire e implementare il ripristino di emergenza degli archivi di SQL Server di chat persistenti da un set di backup configurato di archivi in un altro server SQL.</span><span class="sxs-lookup"><span data-stu-id="632ef-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="632ef-109">Per informazioni dettagliate, vedere [configurare la disponibilità elevata e il ripristino di emergenza per il server di chat persistente in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="632ef-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="632ef-110">Questa opzione è disponibile solo per pool con più server.</span><span class="sxs-lookup"><span data-stu-id="632ef-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="632ef-111">**Usare questo pool come predefinito per il sito \<del sito in\>cui è configurato questo server o pool**: selezionare questa casella di controllo se si tratta del server di chat persistente predefinito o del pool di server di chat persistente per il sito.</span><span class="sxs-lookup"><span data-stu-id="632ef-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="632ef-112">È necessario disporre di un server di chat persistente predefinito o pol per sito.</span><span class="sxs-lookup"><span data-stu-id="632ef-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="632ef-113">Se la topologia include più siti, viene visualizzata una casella di controllo anche per **Usa questo pool come predefinito per tutti i siti**.</span><span class="sxs-lookup"><span data-stu-id="632ef-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="632ef-114">Fare clic su **Indietro** per tornare alla precedente finestra di dialogo per la definizione del pool.</span><span class="sxs-lookup"><span data-stu-id="632ef-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="632ef-115">Fare clic su **Avanti** dopo aver completato l'immissione delle opzioni per il pool per procedere con la definizione del pool del server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="632ef-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="632ef-116">Fare clic su **Annulla** per eliminare tutte le modifiche e chiudere la procedura guidata **Definisci nuovo pool di Chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="632ef-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="632ef-117">Fare clic su **?** per accedere alla Guida sensibile al contesto, come questa pagina.</span><span class="sxs-lookup"><span data-stu-id="632ef-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="632ef-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="632ef-118">See also</span></span>

[<span data-ttu-id="632ef-119">Pianificare il server Chat persistente in Skype per Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="632ef-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="632ef-120">Aggiungere il server di chat persistente alla topologia di Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="632ef-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
