---
title: 'Lync Server 2013: prerequisiti del plug-in VDI di Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63ee7f494b131fc194d6bf9d028525efd71cf0a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534683"
---
# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a><span data-ttu-id="c756d-102">Prerequisiti del plug-in VDI di Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c756d-102">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c756d-103">_**Ultimo argomento modificato:** 2017-03-07_</span><span class="sxs-lookup"><span data-stu-id="c756d-103">_**Topic Last Modified:** 2017-03-07_</span></span>

<span data-ttu-id="c756d-104">In un ambiente VDI (Virtual Desktop Infrastructure), le macchine virtuali e il computer locale dell'utente devono soddisfare i requisiti descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="c756d-104">In a virtual desktop infrastructure (VDI) environment, the virtual machines and the user’s local computer must meet the requirements outlined in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c756d-105">Per informazioni dettagliate su come installare e distribuire l'ambiente virtualizzato, fare riferimento al provider di soluzioni di virtualizzazione.</span><span class="sxs-lookup"><span data-stu-id="c756d-105">Refer to your virtualization solution provider for details about how to install and deploy the virtualized environment.</span></span> <span data-ttu-id="c756d-106">Per informazioni sulla distribuzione di un ambiente virtualizzato basato su Hyper-V e Servizi Desktop remoto, vedere i seguenti articoli della Microsoft TechNet Library:</span><span class="sxs-lookup"><span data-stu-id="c756d-106">For information about deploying a virtualized environment based on Hyper-V and Remote Desktop Services, see the following articles in the Microsoft TechNet Library:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c756d-107">Hyper-V in <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span><span class="sxs-lookup"><span data-stu-id="c756d-107">Hyper-V at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></span></span></P>
> <LI>
> <P><span data-ttu-id="c756d-108">Servizi Desktop remoto in Windows Server &nbsp; 2008 &nbsp; R2 all'indirizzo <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span><span class="sxs-lookup"><span data-stu-id="c756d-108">Remote Desktop Services in Windows Server&nbsp;2008&nbsp;R2 at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="c756d-109">Di seguito sono elencati i requisiti per le macchine virtuali in esecuzione nel computer del Data Center:</span><span class="sxs-lookup"><span data-stu-id="c756d-109">The following are requirements for the virtual machines running on the data center computer:</span></span>

  - <span data-ttu-id="c756d-110">Le macchine virtuali devono essere configurate con Windows 10, Windows 8,1, Windows 8, Windows 7 o Windows Server 2008 R2 con i Service Pack più recenti.</span><span class="sxs-lookup"><span data-stu-id="c756d-110">Virtual machines must be configured with Windows 10, Windows 8.1, Windows 8, Windows 7, or Windows Server 2008 R2 with the latest service packs.</span></span>

<span data-ttu-id="c756d-111">Di seguito sono elencati i requisiti per l'utente e il computer locale dell'utente:</span><span class="sxs-lookup"><span data-stu-id="c756d-111">The following are requirements for the user and the user’s local computer:</span></span>

  - <span data-ttu-id="c756d-112">L'utente deve essere ospitato in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c756d-112">The user must be homed on Lync Server 2013.</span></span>

  - <span data-ttu-id="c756d-113">È necessario che il computer locale esegua Windows Embedded Standard 7 con SP1, Windows 7 con SP1, Windows 8, Windows 8,1 Embedded o Windows 8,1 (non incorporato).</span><span class="sxs-lookup"><span data-stu-id="c756d-113">The local computer must be running Windows Embedded Standard 7 with SP1, Windows 7 with SP1, Windows 8, Windows 8.1 Embedded, or Windows 8.1 (not embedded).</span></span>

  - <span data-ttu-id="c756d-114">Se si utilizzano Servizi Desktop remoto, il plug-in VDI di Lync bit (ovvero se l'applicazione è 32 bit o 64 bit) deve corrispondere al sistema operativo del computer locale bit.</span><span class="sxs-lookup"><span data-stu-id="c756d-114">If you are using Remote Desktop Services, the Lync VDI plug-in bitness (that is, whether the application is 32-bit or 64-bit) must match the local computer’s operating system bitness.</span></span> <span data-ttu-id="c756d-115">Non è necessario che la bit del sistema operativo nel computer locale e il sistema operativo della macchina virtuale corrispondano.</span><span class="sxs-lookup"><span data-stu-id="c756d-115">The bitness of the operating system on the local computer and the operating system on the virtual machine do not need to match.</span></span> <span data-ttu-id="c756d-116">Se si utilizza un'altra soluzione o piattaforma di virtualizzazione, fare riferimento alle indicazioni del provider di soluzioni di virtualizzazione sui requisiti di bit.</span><span class="sxs-lookup"><span data-stu-id="c756d-116">If you are using another virtualization solution or platform, refer to guidance from your virtualization solution provider about bitness requirements.</span></span>

  - <span data-ttu-id="c756d-117">È necessario che il computer locale esegua la versione più recente del client desktop remoto.</span><span class="sxs-lookup"><span data-stu-id="c756d-117">The local computer must be running the latest version of the remote desktop client.</span></span> <span data-ttu-id="c756d-118">Installare gli aggiornamenti più recenti del client dei Servizi Desktop remoto da Microsoft o dall'ultimo software client desktop remoto dal provider di soluzioni di virtualizzazione.</span><span class="sxs-lookup"><span data-stu-id="c756d-118">Install the latest updates of Remote Desktop Services client from Microsoft or the latest remote desktop client software from your virtualization solution provider.</span></span> <span data-ttu-id="c756d-119">Per gli aggiornamenti più recenti dei Servizi Desktop remoto, vedere [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) .</span><span class="sxs-lookup"><span data-stu-id="c756d-119">For the latest Remote Desktop Services updates, see [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

  - <span data-ttu-id="c756d-120">Nel computer locale, è necessario configurare le impostazioni del client desktop remoto in modo che le riproduzioni audio sul computer locale e sulla registrazione remota siano disabilitate.</span><span class="sxs-lookup"><span data-stu-id="c756d-120">On the local computer, the remote desktop client settings must be configured so that audio plays on the local computer and remote recording is disabled.</span></span> <span data-ttu-id="c756d-121">Per configurare queste impostazioni per la connessione Desktop remoto in Windows, vedere la sezione successiva "per configurare le impostazioni di connessione Desktop remoto".</span><span class="sxs-lookup"><span data-stu-id="c756d-121">To configure these settings for Remote Desktop Connection in Windows, see the next section, "To configure Remote Desktop Connection settings."</span></span>

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a><span data-ttu-id="c756d-122">Per configurare le impostazioni di connessione Desktop remoto</span><span class="sxs-lookup"><span data-stu-id="c756d-122">To configure Remote Desktop Connection settings</span></span>

<span data-ttu-id="c756d-123">Per preparare la connessione Desktop remoto in Windows per il plug-in VDI di Lync, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="c756d-123">To prepare Remote Desktop Connection in Windows for the Lync VDI plug-in, follow these steps.</span></span>

1.  <span data-ttu-id="c756d-124">Se il computer locale esegue Windows 8, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="c756d-124">If the local computer is running Windows 8, skip this step.</span></span> <span data-ttu-id="c756d-125">Se il computer locale esegue Windows 7 con SP1, installare la versione più recente di Windows 8 del client Servizi Desktop remoto, disponibile all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032) .</span><span class="sxs-lookup"><span data-stu-id="c756d-125">If the local computer is running Windows 7 with SP1, install the latest Windows 8 version of the Remote Desktop Services client, available at [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032).</span></span>

2.  <span data-ttu-id="c756d-126">Avviare il client Servizi Desktop remoto facendo clic sul pulsante **Start**e quindi su **Connessione desktop remoto**.</span><span class="sxs-lookup"><span data-stu-id="c756d-126">Start the Remote Desktop Services client by clicking **Start**, and then clicking **Remote Desktop Connection**.</span></span>

3.  <span data-ttu-id="c756d-127">Fare clic su **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="c756d-127">Click **Options**.</span></span>

4.  <span data-ttu-id="c756d-128">Fare clic sulla scheda **risorse locali** . In **audio remoto**fare clic su **Impostazioni**e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c756d-128">Click the **Local Resources** tab. Under **Remote audio**, click **Settings**, and then do the following:</span></span>
    
      - <span data-ttu-id="c756d-129">In **riproduzione audio remota**selezionare **Riproduci su questo computer**.</span><span class="sxs-lookup"><span data-stu-id="c756d-129">Under **Remote audio playback**, select **Play on this computer**.</span></span>
    
      - <span data-ttu-id="c756d-130">In **registrazione audio remota**selezionare **non registrare**.</span><span class="sxs-lookup"><span data-stu-id="c756d-130">Under **Remote audio recording**, select **Do not record**.</span></span>
    
      - <span data-ttu-id="c756d-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c756d-131">Click **OK**.</span></span>

5.  <span data-ttu-id="c756d-132">Fare clic sulla scheda **Experience** . In **prestazioni**, deselezionare la casella di controllo relativa alla **memorizzazione nella cache della bitmap persistente** .</span><span class="sxs-lookup"><span data-stu-id="c756d-132">Click the **Experience** tab. Under **Performance**, clear the **Persistent bitmap caching** check box.</span></span>

6.  <span data-ttu-id="c756d-133">Fare clic sulla scheda **generale** . In **computer**, digitare il nome della macchina virtuale, quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="c756d-133">Click the **General** tab. In **Computer**, type the name of the virtual machine, and then click **Connect**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

