---
title: 'Lync Server 2013: creare impostazioni di configurazione del registrar'
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
ms.openlocfilehash: 81aec9ee6923dc125769ad16a26390b23155852c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="9156f-102">Creare impostazioni di configurazione del registrar in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9156f-102">Create Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9156f-103">_**Argomento Ultima modifica:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="9156f-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="9156f-104">È possibile usare il registrar per configurare i metodi di autenticazione del server proxy.</span><span class="sxs-lookup"><span data-stu-id="9156f-104">You can use the Registrar to configure proxy server authentication methods.</span></span> <span data-ttu-id="9156f-105">Il protocollo di autenticazione specificato determina il tipo di problemi che i server del pool rilasciano ai client.</span><span class="sxs-lookup"><span data-stu-id="9156f-105">The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients.</span></span> <span data-ttu-id="9156f-106">I protocolli disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="9156f-106">The available protocols are:</span></span>

  - <span data-ttu-id="9156f-107">**Kerberos**   questo è lo schema di autenticazione basato su password più forte disponibile per i client, ma in genere è disponibile solo per i client aziendali, perché richiede la connessione del client a un centro distribuzione chiave (controller di dominio Kerberos).</span><span class="sxs-lookup"><span data-stu-id="9156f-107">**Kerberos**   This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="9156f-108">Questa impostazione è appropriata se il server autentica solo i client aziendali.</span><span class="sxs-lookup"><span data-stu-id="9156f-108">This setting is appropriate if the server authenticates only enterprise clients.</span></span>

  - <span data-ttu-id="9156f-109">**NTLM**   questa è l'autenticazione basata su password disponibile per i client che usano uno schema di hash per la risposta alla richiesta di verifica sulla password.</span><span class="sxs-lookup"><span data-stu-id="9156f-109">**NTLM**   This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="9156f-110">Questa è l'unica forma di autenticazione disponibile per i client senza connettività a un centro distribuzione chiave (controller di dominio Kerberos), ad esempio utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="9156f-110">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="9156f-111">Se un server esegue l'autenticazione solo per gli utenti remoti, è necessario scegliere NTLM.</span><span class="sxs-lookup"><span data-stu-id="9156f-111">If a server authenticates only remote users, you should choose NTLM.</span></span>

  - <span data-ttu-id="9156f-112">**Autenticazione del certificato**   questo è il nuovo metodo di autenticazione quando il server deve ottenere certificati da client di Lync Phone Edition, telefoni area comune, Lync 2013 e l'app Lync di Windows Store.</span><span class="sxs-lookup"><span data-stu-id="9156f-112">**Certificate authentication**   This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Lync 2013 and the Lync Windows Store app.</span></span> <span data-ttu-id="9156f-113">Nei client di Lync Phone Edition, dopo che un utente ha eseguito l'accesso e viene autenticato fornendo un PIN (Personal Identification Number), Lync Server 2013 fornisce quindi l'URI SIP al telefono e prevede un certificato firmato da Lync Server o un certificato utente che identifica Joe (es: SN=joe@contoso.com) sul telefono.</span><span class="sxs-lookup"><span data-stu-id="9156f-113">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Lync Server 2013 then provisions the SIP URI to the phone and provisions a Lync Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="9156f-114">Questo certificato viene usato per l'autenticazione con il registrar e i servizi Web.</span><span class="sxs-lookup"><span data-stu-id="9156f-114">This certificate is used for authenticating with the Registrar and Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9156f-115">È consigliabile abilitare sia Kerberos che NTLM quando un server supporta l'autenticazione sia per i client remoti che per quelli aziendali.</span><span class="sxs-lookup"><span data-stu-id="9156f-115">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients.</span></span> <span data-ttu-id="9156f-116">Il server perimetrale e i server interni comunicano per garantire che solo l'autenticazione NTLM venga offerta ai client remoti.</span><span class="sxs-lookup"><span data-stu-id="9156f-116">The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients.</span></span> <span data-ttu-id="9156f-117">Se in questi server è abilitato solo Kerberos, non è possibile eseguire l'autenticazione degli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="9156f-117">If only Kerberos is enabled on these servers, they cannot authenticate remote users.</span></span> <span data-ttu-id="9156f-118">Se gli utenti aziendali eseguono l'autenticazione anche sul server, viene usato Kerberos.</span><span class="sxs-lookup"><span data-stu-id="9156f-118">If enterprise users also authenticate against the server, Kerberos is used.</span></span><BR><span data-ttu-id="9156f-119">Se si utilizzeranno i client delle app Lync di Windows Store, è necessario abilitare l'autenticazione dei certificati.</span><span class="sxs-lookup"><span data-stu-id="9156f-119">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>



</div>

<span data-ttu-id="9156f-120">Seguire questa procedura per creare un nuovo registrar.</span><span class="sxs-lookup"><span data-stu-id="9156f-120">Follow these steps to create a new Registrar.</span></span>

<div>

## <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="9156f-121">Per creare nuove impostazioni di configurazione del registrar</span><span class="sxs-lookup"><span data-stu-id="9156f-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="9156f-122">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9156f-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="9156f-123">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9156f-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9156f-124">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9156f-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9156f-125">Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **registrar**.</span><span class="sxs-lookup"><span data-stu-id="9156f-125">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="9156f-126">Nella pagina **registrar** fare clic su **nuovo**</span><span class="sxs-lookup"><span data-stu-id="9156f-126">On the **Registrar** page, click **New**</span></span>

5.  <span data-ttu-id="9156f-127">In **Seleziona un servizio**fare clic sul servizio a cui deve essere applicato il registrar e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9156f-127">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>

6.  <span data-ttu-id="9156f-128">In **nuova impostazione registrar**selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:</span><span class="sxs-lookup"><span data-stu-id="9156f-128">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="9156f-129">**Abilitare l'autenticazione Kerberos per consentire** ai server del pool di emettere problemi con l'autenticazione Kerberos.</span><span class="sxs-lookup"><span data-stu-id="9156f-129">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
      - <span data-ttu-id="9156f-130">**Abilitare l'autenticazione NTLM per consentire** ai server del pool di emettere problemi con NTLM.</span><span class="sxs-lookup"><span data-stu-id="9156f-130">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
      - <span data-ttu-id="9156f-131">**Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.</span><span class="sxs-lookup"><span data-stu-id="9156f-131">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>

7.  <span data-ttu-id="9156f-132">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="9156f-132">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

