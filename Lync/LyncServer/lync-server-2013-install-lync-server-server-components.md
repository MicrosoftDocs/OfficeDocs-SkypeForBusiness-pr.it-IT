---
title: 'Lync Server 2013: installare i componenti server di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9237ed0b60e14383f69ff1e7ef0b0927afe49c98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498703"
---
# <a name="install-server-components-for-lync-server-2013"></a><span data-ttu-id="4aabe-102">Installare componenti server per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aabe-102">Install server components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4aabe-103">_**Ultimo argomento modificato:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="4aabe-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="4aabe-104">Prima di eseguire la procedura seguente, verificare di aver eseguito l'accesso al server con un account utente di dominio che sia un amministratore locale e un membro del gruppo RTCUniversalReadOnlyAdmins in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4aabe-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmins group in Active Directory.</span></span>

<span data-ttu-id="4aabe-105">La distribuzione guidata di Lync Server viene utilizzata per installare i componenti necessari per ogni ruolo di Lync Server e per attivare il server.</span><span class="sxs-lookup"><span data-stu-id="4aabe-105">The Lync Server Deployment Wizard is used to install the needed components for each Lync server role and to activate the server.</span></span> <span data-ttu-id="4aabe-106">In questo articolo vengono illustrati i passaggi per la distribuzione di un server Standard Edition o di un front end server nell'infrastruttura di Lync.</span><span class="sxs-lookup"><span data-stu-id="4aabe-106">This article walks you through the steps of deploying a Standard Edition server or a Front End Server in your Lync infrastructure.</span></span>

<div>

## <a name="to-install-lync-server-components"></a><span data-ttu-id="4aabe-107">Per installare i componenti di Lync Server</span><span class="sxs-lookup"><span data-stu-id="4aabe-107">To install Lync Server components</span></span>

1.  <span data-ttu-id="4aabe-108">Se la distribuzione guidata di Lync Server non è in esecuzione, avviarla nel server in cui si desidera installare Lync.</span><span class="sxs-lookup"><span data-stu-id="4aabe-108">If the Lync Server Deployment Wizard isn’t running, start it on the server you want to install Lync onto.</span></span>

2.  <span data-ttu-id="4aabe-109">Fare clic su **Installa o aggiorna il sistema Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4aabe-109">Click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="4aabe-110">Nella distribuzione guidata, verificare che il **passaggio 1: installazione dell'archivio di configurazione locale** disponga di un segno di spunta verde, il che significa che questo server dispone di una copia locale dell'archivio installato correttamente.</span><span class="sxs-lookup"><span data-stu-id="4aabe-110">In the Deployment Wizard, confirm that **Step 1: Install Local Configuration Store** has a green check mark, which means that this server has a local copy of the store installed successfully.</span></span> <span data-ttu-id="4aabe-111">Se non è selezionata, è necessario installare l'archivio di configurazione locale sul server.</span><span class="sxs-lookup"><span data-stu-id="4aabe-111">If it’s not checked, you need to install the Local Configuration store on the server.</span></span> <span data-ttu-id="4aabe-112">Eseguire la procedura seguente per [installare l'archivio di configurazione locale in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) e quindi tornare qui.</span><span class="sxs-lookup"><span data-stu-id="4aabe-112">Follow the steps at [Install the Local Configuration store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) and then come back here.</span></span>

4.  <span data-ttu-id="4aabe-113">Quando si è pronti per installare i componenti di Lync Server 2013 nel server, fare clic su **Esegui** accanto a **passaggio 2: installazione o rimozione componenti di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4aabe-113">When you’re ready to install the Lync Server 2013 components on your server, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

5.  <span data-ttu-id="4aabe-114">Nella pagina **Configura componenti di Lync Server** fare clic su **Avanti** per configurare i componenti come definito nella topologia pubblicata.</span><span class="sxs-lookup"><span data-stu-id="4aabe-114">On the **Set Up Lync Server Components** page, click **Next** to set up components as defined in your published topology.</span></span>

6.  <span data-ttu-id="4aabe-115">Nella pagina **esecuzione comandi** in corso viene visualizzato un riepilogo dei comandi e delle informazioni di installazione come avviene il set up.</span><span class="sxs-lookup"><span data-stu-id="4aabe-115">The **Executing Commands** page will display a summary of commands and installation information as the set up takes place.</span></span> <span data-ttu-id="4aabe-116">Al termine, è possibile utilizzare l'elenco per selezionare un registro da visualizzare e quindi fare clic su **Visualizza registro**.</span><span class="sxs-lookup"><span data-stu-id="4aabe-116">When it’s done, you can use the list to select a log to view, and then click **View Log**.</span></span>

7.  <span data-ttu-id="4aabe-117">Quando viene eseguito il programma di installazione dei componenti di Lync Server 2013 e i registri sono stati esaminati in base alle esigenze, fare clic su **fine** per completare questo passaggio nell'installazione.</span><span class="sxs-lookup"><span data-stu-id="4aabe-117">When Lync Server 2013 components setup is done, and you’ve reviewed the logs as needed, click **Finish** to complete this step in the installation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4aabe-118">Se viene richiesto di riavviare il server (operazione che potrebbe verificarsi se è necessario installare Windows Desktop Experience), farlo definitivamente.</span><span class="sxs-lookup"><span data-stu-id="4aabe-118">If you’re prompted to restart the server (which might happen if Windows Desktop Experience needed to be installed), definitely do that.</span></span> <span data-ttu-id="4aabe-119">Quando si esegue il backup e l'esecuzione del computer, è necessario eseguire di nuovo questi passaggi, a partire dal passaggio tre elencato sopra (in pratica eseguire il passaggio 2 nella distribuzione guidata un'altra volta).</span><span class="sxs-lookup"><span data-stu-id="4aabe-119">When the computer is back up and running, you need to do these steps over again, starting from step three listed above (basically run Step 2 in the Deployment Wizard one more time).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

