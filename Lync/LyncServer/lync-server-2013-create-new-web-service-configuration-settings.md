---
title: 'Lync Server 2013: creare nuove impostazioni di configurazione del servizio Web'
description: 'Lync Server 2013: creare nuove impostazioni di configurazione del servizio Web.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc66b0c8f394260fbe30e444f800640c774b6bcf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553962"
---
# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="93aa6-103">Creare nuove impostazioni di configurazione del servizio Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93aa6-103">Create new Web Service configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93aa6-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="93aa6-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="93aa6-105">È possibile utilizzare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93aa6-105">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="93aa6-106">Eseguire la procedura seguente per creare un nuovo criterio di servizio Web.</span><span class="sxs-lookup"><span data-stu-id="93aa6-106">Follow these steps to create a new Web Service policy.</span></span>

<div>

## <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="93aa6-107">Per creare nuove impostazioni di configurazione del servizio Web</span><span class="sxs-lookup"><span data-stu-id="93aa6-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="93aa6-108">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93aa6-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="93aa6-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93aa6-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="93aa6-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="93aa6-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="93aa6-111">Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="93aa6-111">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="93aa6-112">Nella pagina **servizio Web** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="93aa6-112">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="93aa6-113">Per configurare il servizio Web per un sito, fare clic su **configurazione sito**.</span><span class="sxs-lookup"><span data-stu-id="93aa6-113">To configure the Web Service for a site, click **Site configuration**.</span></span> <span data-ttu-id="93aa6-114">In **Seleziona un sito**fare clic sul sito a cui verranno applicati i criteri del servizio Web e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="93aa6-114">In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
      - <span data-ttu-id="93aa6-115">Per configurare il servizio Web per un pool, fare clic su **Configurazione pool**.</span><span class="sxs-lookup"><span data-stu-id="93aa6-115">To configure the Web Service for a pool, click **Pool configuration**.</span></span> <span data-ttu-id="93aa6-116">In **Seleziona un servizio**fare clic sul servizio a cui verranno applicati i criteri del servizio Web e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="93aa6-116">In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span>

5.  <span data-ttu-id="93aa6-117">In **nuova impostazione del servizio Web**, in **autenticazione integrata di Windows**, selezionare **negozia**, **autenticazione integrata di Windows**o **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="93aa6-117">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="93aa6-118">Selezionare una o più delle opzioni seguenti in base alle capacità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="93aa6-118">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="93aa6-119">**Abilita autenticazione PIN** per consentire l'autenticazione dei client tramite numeri PIN.</span><span class="sxs-lookup"><span data-stu-id="93aa6-119">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="93aa6-120">**Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.</span><span class="sxs-lookup"><span data-stu-id="93aa6-120">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="93aa6-121">**Abilita download catena di certificati** per fare in modo che i server a cui viene presentato un certificato di autenticazione eseguano il download della catena di certificati per tale certificato.</span><span class="sxs-lookup"><span data-stu-id="93aa6-121">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="93aa6-122">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="93aa6-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

