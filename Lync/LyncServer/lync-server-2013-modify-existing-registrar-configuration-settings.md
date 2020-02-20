---
title: 'Lync Server 2013: modificare le impostazioni di configurazione di registrazione esistenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32d59c31497f4a7d1a67087f47175184bd5665f9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="dc4cb-102">Modificare le impostazioni di configurazione di registrazione esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc4cb-102">Modify existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc4cb-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dc4cb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dc4cb-104">È possibile utilizzare la funzione di registrazione per configurare i protocolli di autenticazione dei server proxy.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-104">You can use the Registrar to configure proxy server authentication protocols.</span></span> <span data-ttu-id="dc4cb-105">Per informazioni sui protocolli disponibili, vedere [creare le impostazioni di configurazione di registrazione in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="dc4cb-105">For information about the available protocols, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dc4cb-p102">Se un server supporta l'autenticazione sia per client remoti che per client aziendali, è consigliabile abilitare sia Kerberos che NTLM. Il server perimetrale e i server interni sono in comunicazione per garantire che ai client remoti sia fornita solo l'autenticazione NTLM. Se in questi server è abilitato solo Kerberos, non sono in grado di autenticare gli utenti remoti. Se attraverso questi server avviene anche l'autenticazione degli utenti aziendali, viene utilizzato Kerberos.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-p102">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span>



</div>

<span data-ttu-id="dc4cb-110">Per modificare una funzione di registrazione esistente, seguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-110">Follow these steps to modify an existing Registrar.</span></span>

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="dc4cb-111">Per modificare le impostazioni di configurazione di registrazione esistenti</span><span class="sxs-lookup"><span data-stu-id="dc4cb-111">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="dc4cb-112">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="dc4cb-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dc4cb-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dc4cb-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dc4cb-115">Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Funzione di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-115">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="dc4cb-116">Nella pagina **Funzione di registrazione** fare clic su un servizio, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-116">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="dc4cb-117">In **Modifica impostazione funzione di registrazione** selezionare una o più delle opzioni seguenti in base alle capacità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="dc4cb-117">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="dc4cb-118">**Abilita autenticazione Kerberos** perché i server del pool emettano richieste utilizzando l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-118">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="dc4cb-119">**Abilita autenticazione NTLM** per fare in modo che tutti i server del pool emettano richieste utilizzando l'autenticazione NTLM.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-119">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="dc4cb-120">**Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-120">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

6.  <span data-ttu-id="dc4cb-121">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="dc4cb-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

