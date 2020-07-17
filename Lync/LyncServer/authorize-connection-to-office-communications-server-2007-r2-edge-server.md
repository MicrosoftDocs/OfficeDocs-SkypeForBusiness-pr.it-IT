---
title: Autorizzare la connessione al server perimetrale di Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: f66f53b5c1aa25324dbd316ad2d72e7d04c42e0f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="c186c-102">Autorizzare la connessione al server perimetrale di Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c186c-102">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c186c-103">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c186c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c186c-104">Per ogni server Lync Server 2013 front end server o Standard Edition nel pool pilota, è necessario aggiornare l'elenco dei server interni autorizzati per la connessione al server perimetrale di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c186c-104">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="c186c-105">In caso contrario, la conferenza audio/visiva (A/V) con accesso esterno per utenti che partecipano utilizzando il server perimetrale legacy non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="c186c-105">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="c186c-106">Per autorizzare la connessione al server perimetrale di Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c186c-106">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="c186c-107">Dal server perimetrale di Office Communications Server 2007 R2, dal gruppo **strumenti di amministrazione** , aprire lo snap-in **Gestione computer** .</span><span class="sxs-lookup"><span data-stu-id="c186c-107">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="c186c-108">Nell'albero della console espandere **Servizi e applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="c186c-108">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="c186c-109">Fare clic con il pulsante destro del mouse su **Office Communications Server 2007 R2** e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c186c-109">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="c186c-110">Fare clic sulla scheda **Interno**.</span><span class="sxs-lookup"><span data-stu-id="c186c-110">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="c186c-111">In **Aggiungi server** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c186c-111">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="c186c-112">Nella finestra di dialogo **Aggiungi Office Communications Server** immettere le informazioni appropriate:</span><span class="sxs-lookup"><span data-stu-id="c186c-112">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="c186c-113">Specificare il nome di dominio completo (FQDN) di ogni server Lync Server 2013 front end server o Standard Edition e il pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c186c-113">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="c186c-114">Specificare il nome di dominio completo di Lync Server 2013 Director se è stata configurata una route statica nel pool che specifica il computer dell'hop successivo in base al nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="c186c-114">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="c186c-115">Dopo aver aggiunto una voce per ogni Lync Server 2013, Front End Server, server Standard Edition, pool e Director, fare clic su **applica** e quindi fare clic su **OK** per chiudere la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="c186c-115">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

