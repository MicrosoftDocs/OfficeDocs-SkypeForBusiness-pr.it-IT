---
title: Eliminare le impostazioni dei PIN per i servizi di conferenza telefonica con accesso esterno per un sito o un gruppo di utenti
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
ms.openlocfilehash: ae81fd45c2679c8b4d2ab0bf6813fbb405905224
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users-in-lync-server-2013"></a><span data-ttu-id="d5cb0-102">Eliminare le impostazioni dei PIN per i servizi di conferenza telefonica con accesso esterno per un sito o un gruppo di utenti in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5cb0-102">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5cb0-103">_**Argomento Ultima modifica:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="d5cb0-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="d5cb0-104">Seguire questa procedura per eliminare un criterio PIN a livello di utente o a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="d5cb0-104">Follow these steps to delete a user-level or a site-level PIN policy.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d5cb0-105">Non è possibile eliminare il criterio PIN globale.</span><span class="sxs-lookup"><span data-stu-id="d5cb0-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-pin-policy"></a><span data-ttu-id="d5cb0-106">Per eliminare un criterio PIN per un utente o un sito</span><span class="sxs-lookup"><span data-stu-id="d5cb0-106">To delete a user or site PIN policy</span></span>

1.  <span data-ttu-id="d5cb0-107">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5cb0-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="d5cb0-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d5cb0-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d5cb0-109">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d5cb0-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d5cb0-110">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri PIN**.</span><span class="sxs-lookup"><span data-stu-id="d5cb0-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="d5cb0-111">Nel campo di ricerca della pagina **criteri PIN** digitare tutto o parte del nome del criterio che si vuole eliminare.</span><span class="sxs-lookup"><span data-stu-id="d5cb0-111">On the **PIN Policy** page, in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="d5cb0-112">Nell'elenco dei criteri fare clic sui criteri desiderati, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="d5cb0-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="d5cb0-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5cb0-113">Click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

