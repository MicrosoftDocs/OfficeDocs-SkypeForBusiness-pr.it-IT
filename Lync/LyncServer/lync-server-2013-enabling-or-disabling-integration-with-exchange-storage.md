---
title: "Lync Server 2013: abilitare o disabilitare l'integrazione con l'archiviazione di Exchange"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5c8a52aabb504ce63ef6e340b5a68e9e8c4c0e7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a><span data-ttu-id="8c32f-102">Abilitazione o disabilitazione dell'integrazione di Lync Server 2013 con lo spazio di archiviazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="8c32f-102">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c32f-103">_**Argomento Ultima modifica:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="8c32f-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="8c32f-104">Nel pannello di controllo di Lync Server 2013 si usano le configurazioni di archiviazione per abilitare e disabilitare l'integrazione con lo spazio di archiviazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="8c32f-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable integration with Exchange storage.</span></span> <span data-ttu-id="8c32f-105">Sono incluse le configurazioni di archiviazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c32f-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="8c32f-106">Configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c32f-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="8c32f-107">Configurazioni facoltative a livello di sito e a livello di pool che è possibile creare e usare per specificare la modalità di implementazione dell'archiviazione per siti o pool specifici.</span><span class="sxs-lookup"><span data-stu-id="8c32f-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="8c32f-108">Per informazioni dettagliate sull'implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere funzionamento dell' [archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla documentazione di distribuzione o alla documentazione operativa.</span><span class="sxs-lookup"><span data-stu-id="8c32f-108">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="8c32f-109">Per abilitare o disabilitare l'integrazione con lo spazio di archiviazione di Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="8c32f-109">To enable or disable integration with Microsoft Exchange storage</span></span>

1.  <span data-ttu-id="8c32f-110">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8c32f-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8c32f-111">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c32f-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8c32f-112">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8c32f-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8c32f-113">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="8c32f-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="8c32f-114">Fare clic sul nome della configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **modifica**, fare clic su **Mostra dettagli**e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c32f-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="8c32f-115">Per abilitare l'integrazione con lo spazio di archiviazione di Exchange 2013, selezionare la casella di controllo **integrazione di Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="8c32f-115">To enable integration with Exchange 2013 storage, select the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="8c32f-116">Per disabilitare l'integrazione con lo spazio di archiviazione di Exchange 2013, deselezionare la casella di controllo **integrazione di Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="8c32f-116">To disable integration with Exchange 2013 storage, clear the **Microsoft Exchange integration** check box.</span></span>

5.  <span data-ttu-id="8c32f-117">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8c32f-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c32f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c32f-118">See Also</span></span>


[<span data-ttu-id="8c32f-119">Funzionamento dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c32f-119">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="8c32f-120">Gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool</span><span class="sxs-lookup"><span data-stu-id="8c32f-120">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

