---
title: 'Lync Server 2013: installare i file per Mediation Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3172b2db7197cfec13249bdff4490128d8b664a1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="71a04-102">Installare i file per Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71a04-102">Install the files for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71a04-103">_**Ultimo argomento modificato:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="71a04-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="71a04-104">Per eseguire questa procedura, è necessario accedere al server almeno come amministratore locale e come utente di dominio appartenente almeno al gruppo RTCUniversalReadOnlyAdmin.</span><span class="sxs-lookup"><span data-stu-id="71a04-104">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="71a04-105">Utilizzare la procedura descritta in questo argomento per eseguire la distribuzione guidata di Lync Server 2013 per installare i file per Mediation Server in un computer aggiunto a un pool di Mediation Server quando è stato utilizzato il generatore di topologie per definire e pubblicare il pool.</span><span class="sxs-lookup"><span data-stu-id="71a04-105">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="71a04-106">Quando si installano i file Mediation Server, è inoltre necessario installare e assegnare il certificato richiesto da ogni computer in un pool di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="71a04-106">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="71a04-107">In questo sito, se sono già stati distribuiti i Mediation Server collocati nei pool Front end o nel server Standard Edition, è possibile ignorare questo argomento e, invece, continuare con la [configurazione dei trunk in Lync server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="71a04-107">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="71a04-108">In questo argomento si presuppone che sia già stato definito e pubblicato un pool di Mediation Server autonomo, come descritto in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">define a Mediation Server in Generatore di topologie in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">pubblicare la topologia in Lync Server 2013</A> nella documentazione relativa alla distribuzione. e di aver verificato che i computer nel pool di Mediation server soddisfino i prerequisiti descritti nei prerequisiti <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">software per voip aziendale in Lync Server 2013</A> e <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">prerequisiti per la sicurezza e la configurazione per l'organizzazione Voce in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="71a04-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="71a04-109">Per installare i file per un pool Mediation Server autonomo</span><span class="sxs-lookup"><span data-stu-id="71a04-109">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="71a04-110">Dal supporto di installazione, fare clic con \<il pulsante\>destro del mouse su installazione media**\\Setup\\amd64\\Setup. exe**e quindi fare clic su **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="71a04-110">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="71a04-111">Nella pagina **Percorso di installazione** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="71a04-111">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="71a04-p102">Nella pagina **Contratto di licenza con l'utente finale** fare clic su **Accetto** e quindi su **OK**. Questa operazione è obbligatoria per proseguire.</span><span class="sxs-lookup"><span data-stu-id="71a04-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>

4.  <span data-ttu-id="71a04-114">Nella pagina **Distribuzione guidata di Lync Server 2010** fare clic su **Installa o aggiorna il sistema Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="71a04-114">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="71a04-115">Accanto a **Passaggio 1: Installazione dell'archivio di configurazione locale** fare clic su **Esegui** e quindi seguire le istruzioni visualizzate sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="71a04-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="71a04-116">Nella pagina **Configura la replica locale dell'archivio di gestione centrale** accettare l'impostazione predefinita **Recupera direttamente dall'archivio di gestione centrale** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="71a04-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="71a04-117">Nella pagina **Esecuzione comandi in corso**, quando lo stato dell'attività risulta completato,\*\*\*\* fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="71a04-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="71a04-118">Accanto a **Passaggio 2: Installazione o rimozione componenti di Lync Server** fare clic su **Esegui** e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="71a04-118">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="71a04-119">Nella pagina **Esecuzione comandi in corso**, quando lo stato dell'attività risulta completato,\*\*\*\* fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="71a04-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="71a04-p103">Accanto a **Passaggio 3: Richiesta, installazione o assegnazione dei certificati** fare clic su **Esegui**. Seguire le istruzioni visualizzate sullo schermo, accettando le impostazioni predefinite. Il Mediation Server richiede un certificato, quindi il **Passaggio 3** verrà eseguito due volte, una per emettere il certificato necessario e l'altra per assegnarlo.</span><span class="sxs-lookup"><span data-stu-id="71a04-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="71a04-123">Dopo che il certificato è stato emesso e assegnato correttamente, accanto **Passaggio 4: Avvia servizi** fare clic su **Esegui** e quindi seguire le istruzioni visualizzate sullo schermo.</span><span class="sxs-lookup"><span data-stu-id="71a04-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="71a04-124">Al termine del **Passaggio 4**, riavviare il server e accedere come membro del gruppo DomainAdmins.</span><span class="sxs-lookup"><span data-stu-id="71a04-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="71a04-125">Nel computer in cui è in esecuzione il pannello di controllo di Lync Server, verificare nella pagina **topologia** del pannello di controllo di Lync Server che lo stato del servizio del Mediation Server sia visualizzato come segno di spunta verde.</span><span class="sxs-lookup"><span data-stu-id="71a04-125">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="71a04-126">Se invece appare una X rossa, selezionare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="71a04-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="71a04-127">Scegliere **Avvia tutti i servizi** dal menu **Azione**.</span><span class="sxs-lookup"><span data-stu-id="71a04-127">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="71a04-128">Se è stato aggiunto più di un computer al pool di Mediation Server, eseguire i passaggi descritti in questa procedura in tutti gli altri computer del pool di Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="71a04-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="71a04-129">Se non è necessario installare i file per Mediation Server per altri computer, seguire le procedure illustrate in [Configuring Trunks in Lync server 2013](lync-server-2013-configuring-trunks.md) per configurare le impostazioni per la connessione trunk tra il pool di Mediation Server (o tutti i Mediation Server in un sito) e il relativo peer.</span><span class="sxs-lookup"><span data-stu-id="71a04-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="71a04-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71a04-130">See Also</span></span>


[<span data-ttu-id="71a04-131">Requisiti dei certificati per i server interni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71a04-131">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

