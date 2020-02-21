---
title: Impedire nuove connessioni a Lync Server per la manutenzione del server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc787dee62152e9ace76663a084fe5c1c428b1f2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="952c3-102">Impedire nuove connessioni a Lync Server 2013 per la manutenzione del server</span><span class="sxs-lookup"><span data-stu-id="952c3-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="952c3-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="952c3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="952c3-104">Lync Server consente di utilizzare un server offline, ad esempio per applicare aggiornamenti software o hardware, senza perdita di servizio per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="952c3-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="952c3-p101">Quando si specifica l'opzione per impedire nuove connessioni o chiamate a un server di un pool, smette di accettare nuove connessioni e chiamate non appena si implementa questa opzione. Le nuove connessioni e le nuove chiamate vengono indirizzate attraverso altri server del pool. Un server che impedisce nuove connessioni consente alle sessioni su connessioni esistenti di continuare fino alla loro fine naturale. Quando tutte le sessioni esistenti sono terminate, il server è pronto per essere portato offline.</span><span class="sxs-lookup"><span data-stu-id="952c3-p101">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option. These new connections and calls are routed through other servers in the pool. A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end. When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="952c3-109">Quando si impediscono nuove connessioni a un front end server, alcune funzionalità e servizi di Lync Server si basano sul bilanciamento del carico DNS per garantire che funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="952c3-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="952c3-110">Se non si utilizza il bilanciamento del carico DNS sul pool, le connessioni tramite questi servizi potrebbero non essere reinstradate ad altri server durante il periodo in cui il server sta impedendo nuove connessioni e, pertanto, quando il server viene portato in modalità non in linea alcune sessioni e le chiamate possono essere interrotto.</span><span class="sxs-lookup"><span data-stu-id="952c3-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="952c3-111">Le caratteristiche che si basano sul bilanciamento del carico DNS per garantire che questa opzione funzioni correttamente sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="952c3-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="952c3-112">Operatore</span><span class="sxs-lookup"><span data-stu-id="952c3-112">Attendant</span></span>

  - <span data-ttu-id="952c3-113">Applicazione Annuncio conferenza</span><span class="sxs-lookup"><span data-stu-id="952c3-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="952c3-114">Applicazione Response Group</span><span class="sxs-lookup"><span data-stu-id="952c3-114">Response Group application</span></span>

  - <span data-ttu-id="952c3-115">Applicazione Annuncio</span><span class="sxs-lookup"><span data-stu-id="952c3-115">Announcement application</span></span>

  - <span data-ttu-id="952c3-116">Applicazione Parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="952c3-116">Call Park application</span></span>

<span data-ttu-id="952c3-117">Per informazioni dettagliate sul bilanciamento del carico DNS, vedere [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="952c3-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="952c3-118">Oltre a impedire nuove connessioni per tutti i servizi su un server che esegue Lync Server, è inoltre possibile impedire nuove connessioni per singoli servizi di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="952c3-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="952c3-119">Ad esempio, questo metodo è utile in una situazione in cui è necessario applicare un aggiornamento di Lync Server che non richiede l'arresto dell'intero server.</span><span class="sxs-lookup"><span data-stu-id="952c3-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="952c3-120">Si noti che quando si impediscono le connessioni per un servizio, è necessario selezionare un servizio nel modo in cui è raggruppato e visualizzato nell'elenco dei servizi di Windows.</span><span class="sxs-lookup"><span data-stu-id="952c3-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="952c3-121">Ad esempio, il servizio front-end di Lync Server e l'agente di raccolta dati per il monitoraggio sono servizi di Lync Server distinti, ma nell'elenco dei servizi di Windows vengono consolidati e visualizzati come servizio front end di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="952c3-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="952c3-122">È possibile impedire le nuove connessioni per il servizio front end di Lync Server, ma non è possibile impedire la presenza di nuove connessioni per i due singoli servizi di Lync Server sottostanti.</span><span class="sxs-lookup"><span data-stu-id="952c3-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="952c3-p104">Quando si imposta un server per impedire nuove connessioni e quindi si riavvia il server, per impostazione predefinita il server inizierà immediatamente ad accettare nuove connessioni dopo l'avvio. Per evitarlo, impostare il server solo per la sospensione e la ripresa manuali, prima di riavviarlo.</span><span class="sxs-lookup"><span data-stu-id="952c3-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="952c3-125">Per impedire nuove connessioni a Lync Server:</span><span class="sxs-lookup"><span data-stu-id="952c3-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="952c3-126">Accedere al computer locale come membro del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="952c3-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="952c3-127">Aprire la console snap-in Servizi: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi fare clic su **Servizi**.</span><span class="sxs-lookup"><span data-stu-id="952c3-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="952c3-128">Nell'elenco fare doppio clic sul servizio Windows Lync Server per cui si desidera impedire nuove connessioni.</span><span class="sxs-lookup"><span data-stu-id="952c3-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="952c3-129">In **Stato servizio: In sospeso** nella finestra di dialogo Proprietà fare clic su **Pausa**.</span><span class="sxs-lookup"><span data-stu-id="952c3-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="952c3-130">Accanto a **Tipo di avvio** fare clic su **Manuale**. Questa operazione è facoltativa, ma consigliata.</span><span class="sxs-lookup"><span data-stu-id="952c3-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="952c3-p105">Quando si imposta un server per impedire nuove connessioni e quindi si riavvia il server, per impostazione predefinita il server inizierà immediatamente ad accettare nuove connessioni dopo l'avvio. Per evitarlo, impostare il server solo per la sospensione e la ripresa manuali, prima di riavviarlo.</span><span class="sxs-lookup"><span data-stu-id="952c3-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="952c3-133">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="952c3-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

