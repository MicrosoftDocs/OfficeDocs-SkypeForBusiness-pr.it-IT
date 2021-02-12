---
title: Configurare l'integrazione con l'archiviazione di Exchange per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: "Riepilogo: leggere questo argomento per informazioni su come configurare l'integrazione con l'archiviazione di Exchange in Skype for Business Server."
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825066"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="0e382-103">Configurare l'integrazione con l'archiviazione di Exchange per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0e382-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="0e382-104">**Riepilogo:** Leggere questo argomento per informazioni su come configurare l'integrazione con l'archiviazione di Exchange in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e382-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="0e382-105">Se si utilizza l'integrazione di Microsoft Exchange per tutti gli utenti nella distribuzione, non è necessario configurare i criteri di archiviazione di Skype for Business Server per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="0e382-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="0e382-106">Al contrario, si configurano i criteri di In-Place archiviazione per supportare l'archiviazione per gli utenti ospitati in Exchange, con le cassette postali In-Place conservazione.</span><span class="sxs-lookup"><span data-stu-id="0e382-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="0e382-107">Prima di configurare l'integrazione con l'archiviazione di Exchange, leggere [Pianificare l'archiviazione in Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="0e382-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="0e382-108">Per informazioni dettagliate sui criteri di In-Place exchange, vedere la documentazione del prodotto Exchange.</span><span class="sxs-lookup"><span data-stu-id="0e382-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="0e382-109">Configurare l'integrazione con l'archiviazione di Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="0e382-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="0e382-110">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="0e382-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0e382-111">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e382-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="0e382-112">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="0e382-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="0e382-113">Fare clic sul nome della configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **Modifica**, su **Mostra dettagli** e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e382-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="0e382-114">Per abilitare l'integrazione con l'archiviazione di Exchange, selezionare la casella di controllo **Integrazione di Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="0e382-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="0e382-115">Per disabilitare l'integrazione con l'archiviazione di Exchange, deselezionare la casella di controllo **integrazione di Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="0e382-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="0e382-116">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="0e382-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="0e382-117">Quando Skype for Business Server e Microsoft Exchange vengono distribuiti in foreste diverse</span><span class="sxs-lookup"><span data-stu-id="0e382-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="0e382-118">Se si utilizza l'integrazione di Microsoft Exchange e Microsoft Exchange Server non viene distribuito nella stessa foresta di Skype for Business Server, è necessario assicurarsi che i seguenti attributi di Exchange Active Directory siano sincronizzati con la foresta in cui è distribuito Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="0e382-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="0e382-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="0e382-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="0e382-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="0e382-120">proxyAddresses</span></span>
    
<span data-ttu-id="0e382-p102">Si tratta di un attributo a valore multiplo. Quando si sincronizza questo attributo, è necessario unire i valori, e non sostituirli, per evitare che i valori esistenti vengano persi.</span><span class="sxs-lookup"><span data-stu-id="0e382-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

