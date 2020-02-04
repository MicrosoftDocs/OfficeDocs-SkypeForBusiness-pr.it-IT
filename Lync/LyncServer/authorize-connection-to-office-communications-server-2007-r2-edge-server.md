---
title: Autorizzare la connessione a Office Communications Server 2007 R2 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dbce32a12f05dff768d23a2bdccfe1b84a567cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="bcfee-102">Autorizzare la connessione a Office Communications Server 2007 R2 Edge Server</span><span class="sxs-lookup"><span data-stu-id="bcfee-102">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcfee-103">_**Argomento Ultima modifica:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="bcfee-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="bcfee-104">Per ogni server front end server o standard di Lync Server 2013 nel pool pilota è necessario aggiornare l'elenco dei server interni autorizzati a connettersi a Office Communications Server 2007 R2 Edge Server.</span><span class="sxs-lookup"><span data-stu-id="bcfee-104">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="bcfee-105">Senza questi aggiornamenti, le conferenze audio/visive (A/V) esterne per gli utenti che partecipano tramite il server perimetrale legacy non funzioneranno.</span><span class="sxs-lookup"><span data-stu-id="bcfee-105">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="bcfee-106">Per autorizzare la connessione a Office Communications Server 2007 R2 Edge Server</span><span class="sxs-lookup"><span data-stu-id="bcfee-106">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="bcfee-107">Da Office Communications Server 2007 R2 Edge Server, dal gruppo **strumenti di amministrazione** , aprire lo snap-in **Gestione computer** .</span><span class="sxs-lookup"><span data-stu-id="bcfee-107">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="bcfee-108">Nell'albero della console espandere **Servizi e applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="bcfee-108">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="bcfee-109">Fare clic con il pulsante destro del mouse su **Office Communications Server 2007 R2**e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="bcfee-109">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="bcfee-110">Fare clic sulla scheda **interno** .</span><span class="sxs-lookup"><span data-stu-id="bcfee-110">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="bcfee-111">In **Aggiungi server**fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bcfee-111">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="bcfee-112">Nella finestra di dialogo **Aggiungi Office Communications Server** immettere le informazioni appropriate:</span><span class="sxs-lookup"><span data-stu-id="bcfee-112">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="bcfee-113">Specificare il nome di dominio completo (FQDN) di ogni server di Lync Server 2013 front-end o Standard Edition e Lync Server 2013 pool.</span><span class="sxs-lookup"><span data-stu-id="bcfee-113">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="bcfee-114">Specificare il nome di dominio completo di Lync Server 2013 Director se è stata configurata una route statica nel pool che specifica il computer hop successivo per il nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="bcfee-114">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="bcfee-115">Dopo aver aggiunto una voce per ogni Lync Server 2013, Front End Server, Standard Edition Server, pool e Director, fare clic su **applica** e quindi su **OK** per chiudere la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="bcfee-115">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

