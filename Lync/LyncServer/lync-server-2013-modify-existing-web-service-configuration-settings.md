---
title: 'Lync Server 2013: modificare le impostazioni di configurazione del servizio Web esistenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a6d29868c6f4b18bd4bb02dac651a671684ecc0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="723c1-102">Modificare le impostazioni di configurazione del servizio Web esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="723c1-102">Modify existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="723c1-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="723c1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="723c1-104">È possibile utilizzare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="723c1-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="723c1-105">Eseguire la procedura seguente per modificare i criteri per un servizio Web esistente.</span><span class="sxs-lookup"><span data-stu-id="723c1-105">Follow these steps to modify an existing Web Service policy.</span></span>

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="723c1-106">Per modificare le impostazioni di configurazione del servizio Web esistenti</span><span class="sxs-lookup"><span data-stu-id="723c1-106">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="723c1-107">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="723c1-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="723c1-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="723c1-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="723c1-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="723c1-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="723c1-110">Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="723c1-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="723c1-111">Nella pagina **Servizio Web** fare clic su una configurazione, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="723c1-111">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="723c1-112">In **Modifica impostazione servizio Web**, in **Autenticazione integrata di Windows**, selezionare **Negoziazione**, **Autenticazione integrata di Windows** o **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="723c1-112">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="723c1-113">Selezionare una o più delle opzioni seguenti in base alle capacità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="723c1-113">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="723c1-114">**Abilita autenticazione PIN** per consentire l'autenticazione dei client tramite numeri PIN.</span><span class="sxs-lookup"><span data-stu-id="723c1-114">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="723c1-115">**Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.</span><span class="sxs-lookup"><span data-stu-id="723c1-115">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="723c1-116">**Abilita download catena di certificati** per fare in modo che i server a cui viene presentato un certificato di autenticazione eseguano il download della catena di certificati per tale certificato.</span><span class="sxs-lookup"><span data-stu-id="723c1-116">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="723c1-117">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="723c1-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="723c1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="723c1-118">See Also</span></span>


[<span data-ttu-id="723c1-119">Configurazione dell'autenticazione nel pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="723c1-119">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

