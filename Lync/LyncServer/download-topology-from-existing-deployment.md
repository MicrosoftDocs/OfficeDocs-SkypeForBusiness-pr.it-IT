---
title: Scarica topologia dalla distribuzione esistente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19cf24e1ef287b50ffece7407913a7d2c45e7062
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="020d1-102">Scarica topologia dalla distribuzione esistente</span><span class="sxs-lookup"><span data-stu-id="020d1-102">Download topology from existing deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="020d1-103">_**Ultimo argomento modificato:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="020d1-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="020d1-104">Quando si crea un pool di Lync Server 2013, si utilizzerà l'archivio di gestione centrale associato a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="020d1-104">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="020d1-105">All'avvio di Generatore di topologie per il primo utilizzo e le sessioni di modifica successive viene richiesto di specificare la posizione in cui deve essere caricato il documento della configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="020d1-105">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="020d1-106">Poiché la topologia di Lync Server 2010 è già stata definita e è stata stabilita l'archivio di gestione centrale, è necessario scegliere di scaricare una topologia da una distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="020d1-106">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="020d1-107">Generatore di topologie leggerà il database e recupererà la definizione corrente.</span><span class="sxs-lookup"><span data-stu-id="020d1-107">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="020d1-108">**Per scaricare una topologia da una distribuzione esistente**</span><span class="sxs-lookup"><span data-stu-id="020d1-108">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="020d1-109">Aprire la **Distribuzione guidata di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="020d1-109">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="020d1-110">Nella pagina **Lync Server 2013 – Distribuzione guidata** fare clic su **Installa Strumenti di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="020d1-110">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="020d1-111">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="020d1-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="020d1-112">Selezionare **Scarica topologia dalla distribuzione esistente**.</span><span class="sxs-lookup"><span data-stu-id="020d1-112">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="020d1-113">![Impostazioni del generatore di topologie della distribuzione guidata](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Impostazioni del generatore di topologie della distribuzione guidata")</span><span class="sxs-lookup"><span data-stu-id="020d1-113">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="020d1-114">Scegliere un nome di file e salvare la topologia con il tipo di file predefinito con estensione tbxml.</span><span class="sxs-lookup"><span data-stu-id="020d1-114">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="020d1-115">Espandere il nodo Lync Server, come illustrato, per visualizzare i vari ruoli server nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="020d1-115">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="020d1-116">![Proprietà generali del ruolo del server generatore di topologie](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Proprietà generali del ruolo del server generatore di topologie")</span><span class="sxs-lookup"><span data-stu-id="020d1-116">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

