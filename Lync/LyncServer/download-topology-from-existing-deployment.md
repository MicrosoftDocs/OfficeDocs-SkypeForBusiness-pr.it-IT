---
title: Scarica topologia dalla distribuzione esistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29a8bd95af99b6b79b91f84231120c6981eeedb7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="ea20b-102">Scarica topologia dalla distribuzione esistente</span><span class="sxs-lookup"><span data-stu-id="ea20b-102">Download topology from existing deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea20b-103">_**Argomento Ultima modifica:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="ea20b-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="ea20b-104">Quando si crea un pool di Lync Server 2013, si utilizzerà l'Central Management Store associato a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ea20b-104">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="ea20b-105">Quando si avvia il generatore di topologia al primo utilizzo e alle successive sessioni di modifica, viene richiesto il percorso in cui si vuole che il generatore di topologia carichi il documento di configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="ea20b-105">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="ea20b-106">Dato che la topologia di Lync Server 2010 è già stata definita e che è stata stabilita l'Central Management store, è consigliabile scegliere di scaricare una topologia da una distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="ea20b-106">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="ea20b-107">Generatore di topologia leggerà il database e recupererà la definizione corrente.</span><span class="sxs-lookup"><span data-stu-id="ea20b-107">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="ea20b-108">**Per scaricare una topologia da una distribuzione esistente**</span><span class="sxs-lookup"><span data-stu-id="ea20b-108">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="ea20b-109">Aprire la **distribuzione guidata di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ea20b-109">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="ea20b-110">Nella pagina **Lync Server 2013-Deployment Wizard** fare clic su **installa strumenti di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="ea20b-110">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="ea20b-111">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013** e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ea20b-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="ea20b-112">Selezionare **Scarica topologia dalla distribuzione esistente**.</span><span class="sxs-lookup"><span data-stu-id="ea20b-112">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="ea20b-113">![Impostazioni del Generatore di topologie per la Distribuzione guidata](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Impostazioni del Generatore di topologie per la Distribuzione guidata")</span><span class="sxs-lookup"><span data-stu-id="ea20b-113">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="ea20b-114">Scegliere un nome file e salvare la topologia con il tipo di file default. tbxml.</span><span class="sxs-lookup"><span data-stu-id="ea20b-114">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="ea20b-115">Espandere il nodo Lync Server, come illustrato, per rivelare i vari ruoli del server nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ea20b-115">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="ea20b-116">![Proprietà generali del ruolo server del Generatore di topologie](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Proprietà generali del ruolo server del Generatore di topologie")</span><span class="sxs-lookup"><span data-stu-id="ea20b-116">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

