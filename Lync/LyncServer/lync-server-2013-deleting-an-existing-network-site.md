---
title: 'Lync Server 2013: eliminazione di un sito di rete esistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c8e3828bccb84fcddb4404dd7228173c63ab8a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a><span data-ttu-id="aa3b5-102">Eliminazione di un sito di rete esistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa3b5-102">Deleting an existing network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa3b5-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="aa3b5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="aa3b5-104">I siti di rete sono gli uffici o i percorsi configurati in ogni area geografica di un controllo di ammissione alle chiamate (CAC) o una distribuzione avanzata di 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="aa3b5-105">È possibile usare il pannello di controllo di Lync Server 2013 per configurare i siti e associarli alle aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-105">You can use the Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="aa3b5-106">Ad esempio, un'area di rete per il Nord America potrebbe essere associata a siti di reti come Chicago, Redmond e Vancouver.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="aa3b5-107">È necessario creare un sito di rete CAC per ogni sito all'interno di un'organizzazione, anche se il sito non ha limitazioni di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="aa3b5-108">Dal pannello di controllo di Lync Server è possibile creare, modificare ed eliminare siti di rete.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="aa3b5-109">Usare la procedura seguente per eliminare un sito di rete esistente.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-109">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="aa3b5-110">Per informazioni dettagliate sulla creazione o la modifica di siti di rete, vedere [creazione o modifica di siti di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span><span class="sxs-lookup"><span data-stu-id="aa3b5-110">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)</span></span>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="aa3b5-111">Per eliminare un sito di rete</span><span class="sxs-lookup"><span data-stu-id="aa3b5-111">To delete a network site</span></span>

1.  <span data-ttu-id="aa3b5-112">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aa3b5-113">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aa3b5-114">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aa3b5-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aa3b5-115">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **sito**.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="aa3b5-116">Nella pagina del **sito** fare clic sul sito che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-116">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa3b5-117">È possibile eliminare più di un sito alla volta.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-117">You can delete more than one site at a time.</span></span> <span data-ttu-id="aa3b5-118">Per eseguire questa operazione, premere CTRL e selezionare più siti tenendo premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-118">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="aa3b5-119">In alternativa, per selezionare tutti i siti, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="aa3b5-119">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="aa3b5-120">Scegliere **Elimina**dal menu **modifica** .</span><span class="sxs-lookup"><span data-stu-id="aa3b5-120">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="aa3b5-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-121">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="aa3b5-122">Non è possibile rimuovere un sito di rete se associato a una subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-122">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="aa3b5-123">Se si tenta di rimuovere un sito associato a una subnet, viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="aa3b5-123">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="aa3b5-124">Per verificare se un sito è associato a qualsiasi subnet, fare clic sul sito e quindi su <STRONG>Mostra dettagli</STRONG> dal menu <STRONG>modifica</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="aa3b5-124">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

