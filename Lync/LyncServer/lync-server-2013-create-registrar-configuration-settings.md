---
title: 'Lync Server 2013: creare impostazioni di configurazione del servizio di registrazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6167e82679aa0124b2ae8833be9d4a9a56df2009
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="60909-102">Creare le impostazioni di configurazione di registrazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60909-102">Create Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60909-103">_**Ultimo argomento modificato:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="60909-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="60909-p101">È possibile utilizzare la funzione di registrazione per configurare metodi di autenticazione di server proxy. Il protocollo di autenticazione specificato determina il tipo di richieste dei server del pool per i client. I protocolli disponibili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="60909-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>

  - <span data-ttu-id="60909-107">**Kerberos**   questo è il più potente schema di autenticazione basato su password disponibile per i client, ma è in genere disponibile solo per i client aziendali perché richiede la connessione client a un centro distribuzione chiavi (controller di dominio Kerberos).</span><span class="sxs-lookup"><span data-stu-id="60909-107">**Kerberos**   This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="60909-108">Questa impostazione è appropriata se il server deve eseguire solo l'autenticazione dei client aziendali.</span><span class="sxs-lookup"><span data-stu-id="60909-108">This setting is appropriate if the server authenticates only enterprise clients.</span></span>

  - <span data-ttu-id="60909-109">**NTLM**   questa è l'autenticazione basata su password disponibile per i client che utilizzano uno schema di hashing Challenge-Response sulla password.</span><span class="sxs-lookup"><span data-stu-id="60909-109">**NTLM**   This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="60909-110">È l'unica forma di autenticazione disponibile per i client senza connettività a un Centro distribuzione chiavi (controller di dominio Kerberos), ad esempio gli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="60909-110">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="60909-111">Se un server autentica solo utenti remoti, è consigliabile scegliere NTLM.</span><span class="sxs-lookup"><span data-stu-id="60909-111">If a server authenticates only remote users, you should choose NTLM.</span></span>

  - <span data-ttu-id="60909-112">**Autenticazione dei certificati**   questo è il nuovo metodo di autenticazione quando il server deve ottenere i certificati da client Lync Phone Edition, telefoni area comune, Lync 2013 e l'app Lync Windows Store.</span><span class="sxs-lookup"><span data-stu-id="60909-112">**Certificate authentication**   This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Lync 2013 and the Lync Windows Store app.</span></span> <span data-ttu-id="60909-113">Nei client di Lync Phone Edition, dopo che un utente ha eseguito l'accesso ed è stato autenticato fornendo un PIN (Personal Identification Number), Lync Server 2013 quindi accantona l'URI SIP sul telefono e fornisce un certificato firmato Lync Server o un certificato utente che identifica Joe (ex: SN=joe@contoso.com) nel telefono.</span><span class="sxs-lookup"><span data-stu-id="60909-113">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Lync Server 2013 then provisions the SIP URI to the phone and provisions a Lync Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="60909-114">Questo certificato viene utilizzato per l'autenticazione con la funzione di Registrazione avanzata e i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="60909-114">This certificate is used for authenticating with the Registrar and Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60909-p105">È consigliabile abilitare sia Kerberos sia NTLM quando un server supporta l'autenticazione per client remoti e aziendali. Il server perimetrale e i server interni comunicano per assicurare che ai client remoti venga offerta solo l'autenticazione NTLM. I server in cui è abilitata solo l'autenticazione Kerberos non sono in grado di autenticare gli utenti remoti. Se il server autentica anche gli utenti aziendali, viene utilizzato Kerberos.</span><span class="sxs-lookup"><span data-stu-id="60909-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span><BR><span data-ttu-id="60909-119">Se si utilizzeranno i client app di Windows Store di Lync, è necessario abilitare l'autenticazione dei certificati.</span><span class="sxs-lookup"><span data-stu-id="60909-119">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>



</div>

<span data-ttu-id="60909-120">Eseguire la procedura seguente per creare una nuova funzione di registrazione.</span><span class="sxs-lookup"><span data-stu-id="60909-120">Follow these steps to create a new Registrar.</span></span>

<div>

## <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="60909-121">Per creare nuove impostazioni di configurazione del servizio di registrazione</span><span class="sxs-lookup"><span data-stu-id="60909-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="60909-122">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="60909-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="60909-123">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="60909-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="60909-124">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="60909-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="60909-125">Sulla barra di spostamento sinistra fare clic su **Sicurezza**, quindi su **Funzione di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="60909-125">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="60909-126">Nella pagina **Funzione di registrazione** fare clic su **Nuovo**</span><span class="sxs-lookup"><span data-stu-id="60909-126">On the **Registrar** page, click **New**</span></span>

5.  <span data-ttu-id="60909-127">In **Seleziona un servizio** fare clic sul servizio a cui applicare la funzione di registrazione e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="60909-127">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>

6.  <span data-ttu-id="60909-128">In **Impostazione funzione di registrazione** selezionare una o più opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="60909-128">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="60909-129">**Abilita autenticazione Kerberos** per fare in modo che tutti i server del pool emettano richieste utilizzando l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="60909-129">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="60909-130">**Abilita autenticazione NTLM** per fare in modo che tutti i server del pool emettano richieste utilizzando l'autenticazione NTLM.</span><span class="sxs-lookup"><span data-stu-id="60909-130">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="60909-131">**Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.</span><span class="sxs-lookup"><span data-stu-id="60909-131">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

7.  <span data-ttu-id="60909-132">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="60909-132">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

