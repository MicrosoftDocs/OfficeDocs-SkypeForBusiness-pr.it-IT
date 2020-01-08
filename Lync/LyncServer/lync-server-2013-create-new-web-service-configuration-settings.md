---
title: 'Lync Server 2013: creare nuove impostazioni di configurazione del servizio Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86105e4dbf6b624f87844a68ebe5fca6bba02247
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="acdb0-102">Creare nuove impostazioni di configurazione del servizio Web in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acdb0-102">Create new Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acdb0-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="acdb0-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="acdb0-104">È possibile usare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="acdb0-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="acdb0-105">Seguire questa procedura per creare un nuovo criterio di servizio Web.</span><span class="sxs-lookup"><span data-stu-id="acdb0-105">Follow these steps to create a new Web Service policy.</span></span>

<div>

## <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="acdb0-106">Per creare nuove impostazioni di configurazione del servizio Web</span><span class="sxs-lookup"><span data-stu-id="acdb0-106">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="acdb0-107">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="acdb0-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="acdb0-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="acdb0-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="acdb0-109">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="acdb0-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="acdb0-110">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **servizio Web**.</span><span class="sxs-lookup"><span data-stu-id="acdb0-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="acdb0-111">Nella pagina **servizio Web** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="acdb0-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="acdb0-112">Per configurare il servizio Web per un sito, fare clic su **configurazione sito**.</span><span class="sxs-lookup"><span data-stu-id="acdb0-112">To configure the Web Service for a site, click **Site configuration**.</span></span> <span data-ttu-id="acdb0-113">In **Seleziona un sito**fare clic sul sito a cui verranno applicati i criteri di servizio Web e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="acdb0-113">In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
      - <span data-ttu-id="acdb0-114">Per configurare il servizio Web per un pool, fare clic su **Configurazione pool**.</span><span class="sxs-lookup"><span data-stu-id="acdb0-114">To configure the Web Service for a pool, click **Pool configuration**.</span></span> <span data-ttu-id="acdb0-115">In **Seleziona un servizio**fare clic sul servizio a cui verranno applicati i criteri di servizio Web e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="acdb0-115">In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span>

5.  <span data-ttu-id="acdb0-116">Nell' **impostazione di un nuovo servizio Web**, nell' **autenticazione integrata di Windows**, selezionare **negozia**, **autenticazione di Windows integrata**o **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="acdb0-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="acdb0-117">Selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="acdb0-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="acdb0-118">**Abilitare l'autenticazione PIN** per consentire ai client di essere autenticati usando i numeri di pin.</span><span class="sxs-lookup"><span data-stu-id="acdb0-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="acdb0-119">**Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.</span><span class="sxs-lookup"><span data-stu-id="acdb0-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="acdb0-120">**Abilitare il download della catena di certificati per consentire** ai server presentati con un certificato di autenticazione di scaricare la catena di certificati per tale certificato.</span><span class="sxs-lookup"><span data-stu-id="acdb0-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="acdb0-121">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="acdb0-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

