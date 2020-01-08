---
title: 'Lync Server 2013: Installazione dei componenti server di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895047715bfa632970adbabb20311d8c68182499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a><span data-ttu-id="ed6bf-102">Installazione dei componenti server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed6bf-102">Install server components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed6bf-103">_**Argomento Ultima modifica:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="ed6bf-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="ed6bf-104">Prima di eseguire questa procedura, verificare di aver effettuato l'accesso al server con un account utente di dominio che sia un amministratore locale e un membro del gruppo RTCUniversalReadOnlyAdmins in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ed6bf-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmins group in Active Directory.</span></span>

<span data-ttu-id="ed6bf-105">La distribuzione guidata di Lync Server viene usata per installare i componenti necessari per ogni ruolo di Lync Server e per attivare il server.</span><span class="sxs-lookup"><span data-stu-id="ed6bf-105">The Lync Server Deployment Wizard is used to install the needed components for each Lync server role and to activate the server.</span></span> <span data-ttu-id="ed6bf-106">In questo articolo vengono illustrati i passaggi della distribuzione di un server Standard Edition o di un server front-end nell'infrastruttura Lync.</span><span class="sxs-lookup"><span data-stu-id="ed6bf-106">This article walks you through the steps of deploying a Standard Edition server or a Front End Server in your Lync infrastructure.</span></span>

<div>

## <a name="to-install-lync-server-components"></a><span data-ttu-id="ed6bf-107">Per installare i componenti di Lync Server</span><span class="sxs-lookup"><span data-stu-id="ed6bf-107">To install Lync Server components</span></span>

1.  <span data-ttu-id="ed6bf-108">Se la distribuzione guidata di Lync Server non è in corso, avviarla nel server in cui si vuole installare Lync.</span><span class="sxs-lookup"><span data-stu-id="ed6bf-108">If the Lync Server Deployment Wizard isn’t running, start it on the server you want to install Lync onto.</span></span>

2.  <span data-ttu-id="ed6bf-109">Fare clic su **Installa o aggiorna Lync Server System**.</span><span class="sxs-lookup"><span data-stu-id="ed6bf-109">Click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="ed6bf-110">Nella distribuzione guidata verificare che il **passaggio 1: install Local Configuration Store** contenga un segno di spunta verde, il che significa che il server ha una copia locale dello Store installata correttamente.</span><span class="sxs-lookup"><span data-stu-id="ed6bf-110">In the Deployment Wizard, confirm that **Step 1: Install Local Configuration Store** has a green check mark, which means that this server has a local copy of the store installed successfully.</span></span> <span data-ttu-id="ed6bf-111">Se non è selezionata, è necessario installare l'archivio di configurazione locale nel server.</span><span class="sxs-lookup"><span data-stu-id="ed6bf-111">If it’s not checked, you need to install the Local Configuration store on the server.</span></span> <span data-ttu-id="ed6bf-112">Seguire i passaggi descritti in [installare l'archivio di configurazione locale in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) e quindi tornare qui.</span><span class="sxs-lookup"><span data-stu-id="ed6bf-112">Follow the steps at [Install the Local Configuration store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) and then come back here.</span></span>

4.  <span data-ttu-id="ed6bf-113">Quando si è pronti per installare i componenti di Lync Server 2013 nel server, fare clic su **Esegui** accanto al **passaggio 2: configurare o rimuovere i componenti di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ed6bf-113">When you’re ready to install the Lync Server 2013 components on your server, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

5.  <span data-ttu-id="ed6bf-114">Nella pagina **configurare i componenti di Lync Server** fare clic su **Avanti** per configurare i componenti come definiti nella topologia pubblicata.</span><span class="sxs-lookup"><span data-stu-id="ed6bf-114">On the **Set Up Lync Server Components** page, click **Next** to set up components as defined in your published topology.</span></span>

6.  <span data-ttu-id="ed6bf-115">Nella pagina **comandi in esecuzione** viene visualizzato un riepilogo dei comandi e delle informazioni di installazione Man mano che viene eseguita la configurazione.</span><span class="sxs-lookup"><span data-stu-id="ed6bf-115">The **Executing Commands** page will display a summary of commands and installation information as the set up takes place.</span></span> <span data-ttu-id="ed6bf-116">Al termine, è possibile usare l'elenco per selezionare un log da visualizzare e quindi fare clic su **Visualizza log**.</span><span class="sxs-lookup"><span data-stu-id="ed6bf-116">When it’s done, you can use the list to select a log to view, and then click **View Log**.</span></span>

7.  <span data-ttu-id="ed6bf-117">Quando è stata eseguita la configurazione dei componenti di Lync Server 2013 e i registri sono stati esaminati in base alle esigenze, fare clic su **fine** per completare questo passaggio nell'installazione.</span><span class="sxs-lookup"><span data-stu-id="ed6bf-117">When Lync Server 2013 components setup is done, and you’ve reviewed the logs as needed, click **Finish** to complete this step in the installation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ed6bf-118">Se viene richiesto di riavviare il server (che potrebbe verificarsi se l'esperienza desktop di Windows dovesse essere installata), eseguire definitivamente questa operazione.</span><span class="sxs-lookup"><span data-stu-id="ed6bf-118">If you’re prompted to restart the server (which might happen if Windows Desktop Experience needed to be installed), definitely do that.</span></span> <span data-ttu-id="ed6bf-119">Quando il computer viene eseguito il backup e l'esecuzione, è necessario eseguire di nuovo questi passaggi, a partire dal passaggio tre elencato sopra (in pratica eseguire il passaggio 2 nella distribuzione guidata).</span><span class="sxs-lookup"><span data-stu-id="ed6bf-119">When the computer is back up and running, you need to do these steps over again, starting from step three listed above (basically run Step 2 in the Deployment Wizard one more time).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

