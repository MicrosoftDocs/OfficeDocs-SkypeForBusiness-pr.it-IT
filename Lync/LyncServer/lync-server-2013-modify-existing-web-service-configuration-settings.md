---
title: 'Lync Server 2013: modificare le impostazioni di configurazione del servizio Web esistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f53d0eb34412c746332a0f74d140b6c41c9c257f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="dae23-102">Modificare le impostazioni di configurazione del servizio Web esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dae23-102">Modify existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dae23-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dae23-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dae23-104">È possibile usare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dae23-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="dae23-105">Seguire questa procedura per modificare un criterio di servizio Web esistente.</span><span class="sxs-lookup"><span data-stu-id="dae23-105">Follow these steps to modify an existing Web Service policy.</span></span>

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="dae23-106">Per modificare le impostazioni di configurazione del servizio Web esistente</span><span class="sxs-lookup"><span data-stu-id="dae23-106">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="dae23-107">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dae23-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="dae23-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dae23-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dae23-109">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dae23-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dae23-110">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="dae23-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="dae23-111">Nella pagina **servizio Web** fare clic su una configurazione, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="dae23-111">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="dae23-112">In **Modifica impostazione servizio Web**, in **autenticazione di Windows integrata**, selezionare **negozia**, **autenticazione di Windows integrata**o **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="dae23-112">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="dae23-113">Selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="dae23-113">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="dae23-114">**Abilitare l'autenticazione PIN** per consentire ai client di essere autenticati usando i numeri di pin.</span><span class="sxs-lookup"><span data-stu-id="dae23-114">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="dae23-115">**Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.</span><span class="sxs-lookup"><span data-stu-id="dae23-115">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="dae23-116">**Abilitare il download della catena di certificati per consentire** ai server presentati con un certificato di autenticazione di scaricare la catena di certificati per tale certificato.</span><span class="sxs-lookup"><span data-stu-id="dae23-116">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="dae23-117">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="dae23-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dae23-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dae23-118">See Also</span></span>


[<span data-ttu-id="dae23-119">Configurazione dell'autenticazione nel pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dae23-119">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

