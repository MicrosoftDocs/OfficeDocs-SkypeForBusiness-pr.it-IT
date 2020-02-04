---
title: 'Lync Server 2013: modificare le impostazioni di configurazione del registrar esistenti'
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
ms.openlocfilehash: 5fe12f85f7ea8501f478d570612ad52cd350fdca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="133cc-102">Modificare le impostazioni di configurazione del registrar esistenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="133cc-102">Modify existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="133cc-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="133cc-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="133cc-104">È possibile usare il registrar per configurare i protocolli di autenticazione del server proxy.</span><span class="sxs-lookup"><span data-stu-id="133cc-104">You can use the Registrar to configure proxy server authentication protocols.</span></span> <span data-ttu-id="133cc-105">Per informazioni sui protocolli disponibili, vedere [creare impostazioni di configurazione del registrar in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="133cc-105">For information about the available protocols, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="133cc-106">È consigliabile abilitare sia Kerberos che NTLM quando un server supporta l'autenticazione sia per i client remoti che per quelli aziendali.</span><span class="sxs-lookup"><span data-stu-id="133cc-106">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients.</span></span> <span data-ttu-id="133cc-107">Il server perimetrale e i server interni comunicano per garantire che solo l'autenticazione NTLM venga offerta ai client remoti.</span><span class="sxs-lookup"><span data-stu-id="133cc-107">The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients.</span></span> <span data-ttu-id="133cc-108">Se in questi server è abilitato solo Kerberos, non è possibile eseguire l'autenticazione degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="133cc-108">If only Kerberos is enabled on these servers, they cannot authenticate remote users.</span></span> <span data-ttu-id="133cc-109">Se gli utenti aziendali eseguono l'autenticazione anche sul server, viene usato Kerberos.</span><span class="sxs-lookup"><span data-stu-id="133cc-109">If enterprise users also authenticate against the server, Kerberos is used.</span></span>



</div>

<span data-ttu-id="133cc-110">Seguire questa procedura per modificare un registrar esistente.</span><span class="sxs-lookup"><span data-stu-id="133cc-110">Follow these steps to modify an existing Registrar.</span></span>

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="133cc-111">Per modificare le impostazioni di configurazione del registrar esistenti</span><span class="sxs-lookup"><span data-stu-id="133cc-111">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="133cc-112">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="133cc-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="133cc-113">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="133cc-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="133cc-114">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="133cc-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="133cc-115">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **registrar**.</span><span class="sxs-lookup"><span data-stu-id="133cc-115">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="133cc-116">Nella pagina **registrar** fare clic su un servizio, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="133cc-116">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="133cc-117">In **modifica registrar**selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="133cc-117">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="133cc-118">**Abilitare l'autenticazione Kerberos per consentire** ai server del pool di emettere problemi con l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="133cc-118">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="133cc-119">**Abilitare l'autenticazione NTLM per consentire** ai server del pool di emettere problemi con NTLM.</span><span class="sxs-lookup"><span data-stu-id="133cc-119">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="133cc-120">**Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.</span><span class="sxs-lookup"><span data-stu-id="133cc-120">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

6.  <span data-ttu-id="133cc-121">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="133cc-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

