---
title: 'Lync Server 2013: eliminare una regola di criteri di versione client esistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy rule
ms:assetid: 2fe351c4-d78b-47d5-af49-d47ee5e0fe42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923066(v=OCS.15)
ms:contentKeyID: 50675352
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fce0da6ece0d34c7cf41eac43d472e85c117817
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501573"
---
# <a name="delete-an-existing-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="8d1b5-102">Eliminare una regola di criteri di versione client esistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d1b5-102">Delete an existing client version policy rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d1b5-103">_**Ultimo argomento modificato:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="8d1b5-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="8d1b5-104">Un criterio di versione client è costituito da un insieme di regole dei criteri di versione client.</span><span class="sxs-lookup"><span data-stu-id="8d1b5-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="8d1b5-105">Queste regole definiscono le azioni da eseguire quando gli utenti tentano di accedere con client e versioni client specifici.</span><span class="sxs-lookup"><span data-stu-id="8d1b5-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="8d1b5-106">È possibile eliminare singole regole da un criterio di versione client dal pannello di controllo di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8d1b5-106">You can delete individual rules from a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-delete-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="8d1b5-107">Per eliminare le regole dei criteri di versione client con il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8d1b5-107">To delete client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8d1b5-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8d1b5-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8d1b5-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8d1b5-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8d1b5-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8d1b5-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8d1b5-111">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento **criteri versione client** .</span><span class="sxs-lookup"><span data-stu-id="8d1b5-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="8d1b5-112">Nella pagina **criteri versione client** fare doppio clic sul criterio versione client per la regola che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="8d1b5-112">On the **Client Version Policy** page, double-click the client version policy for the rule you want to delete.</span></span>

5.  <span data-ttu-id="8d1b5-113">Le regole vengono visualizzate nella pagina **modifica criteri versione client** .</span><span class="sxs-lookup"><span data-stu-id="8d1b5-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="8d1b5-114">Per eliminare una regola, selezionare la regola, quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="8d1b5-114">To delete a rule, select the rule, and then click **Remove**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

