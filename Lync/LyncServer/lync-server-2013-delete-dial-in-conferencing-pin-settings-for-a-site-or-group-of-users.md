---
title: Eliminare le impostazioni del PIN per le conferenze telefoniche con accesso esterno per un sito o un gruppo di utenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete dial-in conferencing PIN settings for a site or group of users
ms:assetid: 15a9faee-d024-4c0e-b2a0-fe7e7dc00589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520955(v=OCS.15)
ms:contentKeyID: 48183498
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a085da7207bcccbe6a1a1d8009fb3f054e20dfbb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users-in-lync-server-2013"></a><span data-ttu-id="e3a72-102">Eliminare le impostazioni del PIN per le conferenze telefoniche con accesso esterno per un sito o un gruppo di utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3a72-102">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3a72-103">_**Ultimo argomento modificato:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="e3a72-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="e3a72-104">Eseguire questa procedura per eliminare un criterio PIN a livello di utente o di sito.</span><span class="sxs-lookup"><span data-stu-id="e3a72-104">Follow these steps to delete a user-level or a site-level PIN policy.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="e3a72-105">Non è possibile eliminare il criterio PIN globale.</span><span class="sxs-lookup"><span data-stu-id="e3a72-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-pin-policy"></a><span data-ttu-id="e3a72-106">Per eliminare un criterio PIN utente o sito</span><span class="sxs-lookup"><span data-stu-id="e3a72-106">To delete a user or site PIN policy</span></span>

1.  <span data-ttu-id="e3a72-107">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3a72-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="e3a72-108">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e3a72-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e3a72-109">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e3a72-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e3a72-110">Nella barra di spostamento sinistra fare clic su **Servizio di conferenza**, quindi su **Criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="e3a72-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="e3a72-111">Nella pagina **Criteri PIN** digitare nel campo di ricerca tutto o parte del nome del criterio che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="e3a72-111">On the **PIN Policy** page, in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="e3a72-112">Nell'elenco dei criteri fare clic su quello desiderato, fare clic su **Modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="e3a72-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="e3a72-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3a72-113">Click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

