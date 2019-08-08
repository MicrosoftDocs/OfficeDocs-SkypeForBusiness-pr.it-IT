---
title: Configurare l'integrazione con lo spazio di archiviazione di Exchange per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: "Riepilogo: leggere questo argomento per informazioni su come configurare l'integrazione con lo spazio di archiviazione di Exchange in Skype for Business Server."
ms.openlocfilehash: 72caf77c81dae538f793afe6f0a94ad6b61d0fa5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234547"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="5dd6f-103">Configurare l'integrazione con lo spazio di archiviazione di Exchange per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5dd6f-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="5dd6f-104">**Riepilogo:** Leggere questo argomento per informazioni su come configurare l'integrazione con lo spazio di archiviazione di Exchange in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5dd6f-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="5dd6f-105">Se si usa l'integrazione di Microsoft Exchange per tutti gli utenti della distribuzione, non è necessario configurare i criteri di archiviazione di Skype for Business Server per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5dd6f-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="5dd6f-106">Puoi invece configurare i criteri di blocco sul posto di Exchange per supportare l'archiviazione per gli utenti ospitati in Exchange, con le cassette postali inserite sul posto.</span><span class="sxs-lookup"><span data-stu-id="5dd6f-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="5dd6f-107">Prima di configurare l'integrazione con lo spazio di archiviazione di Exchange, leggere [piano per l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="5dd6f-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="5dd6f-108">Per informazioni dettagliate sui criteri di blocco sul posto di Exchange, vedere la documentazione del prodotto Exchange.</span><span class="sxs-lookup"><span data-stu-id="5dd6f-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="5dd6f-109">Configurare l'integrazione con lo spazio di archiviazione di Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="5dd6f-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="5dd6f-110">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="5dd6f-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5dd6f-111">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5dd6f-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="5dd6f-112">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="5dd6f-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="5dd6f-113">Fare clic sul nome della configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **modifica**, fare clic su **Mostra dettagli**e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5dd6f-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="5dd6f-114">Per abilitare l'integrazione con l'archiviazione di Exchange, selezionare la casella di controllo **integrazione di Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="5dd6f-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="5dd6f-115">Per disabilitare l'integrazione con l'archiviazione di Exchange, deselezionare la casella di controllo **integrazione di Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="5dd6f-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="5dd6f-116">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="5dd6f-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="5dd6f-117">Quando Skype for Business Server e Microsoft Exchange vengono distribuiti in foreste diverse</span><span class="sxs-lookup"><span data-stu-id="5dd6f-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="5dd6f-118">Se si usa l'integrazione di Microsoft Exchange e Microsoft Exchange Server non è distribuito nella stessa foresta di Skype for Business Server, è necessario verificare che gli attributi di Exchange Active Directory seguenti siano sincronizzati con la foresta in cui Skype for Server aziendale distribuito:</span><span class="sxs-lookup"><span data-stu-id="5dd6f-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="5dd6f-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5dd6f-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="5dd6f-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5dd6f-120">proxyAddresses</span></span>
    
<span data-ttu-id="5dd6f-121">Questo è un attributo multivalore.</span><span class="sxs-lookup"><span data-stu-id="5dd6f-121">This is a multi-value attribute.</span></span> <span data-ttu-id="5dd6f-122">Quando si sincronizza questo attributo, è necessario unire i valori, non sostituirli per evitare che i valori esistenti vengano persi.</span><span class="sxs-lookup"><span data-stu-id="5dd6f-122">When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

