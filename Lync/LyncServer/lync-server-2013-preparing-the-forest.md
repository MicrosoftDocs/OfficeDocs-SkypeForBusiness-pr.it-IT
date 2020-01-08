---
title: 'Lync Server 2013: Preparazione della foresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the forest
ms:assetid: 3d188fcb-c64e-46cf-a3a7-9e3ebefed7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425898(v=OCS.15)
ms:contentKeyID: 48183926
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c374252f94c3a872eacbb99a4f6b891204bb56cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-forest-for-lync-server-2013"></a><span data-ttu-id="fae71-102">Preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fae71-102">Preparing the forest for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fae71-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fae71-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fae71-104">La preparazione della foresta crea le impostazioni globali di Active Directory e gli oggetti e i gruppi universali di Active Directory per l'uso da Lync Server 2013 e concede le autorizzazioni di accesso appropriate per gli oggetti Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fae71-104">Forest preparation creates Active Directory global settings and objects and Active Directory universal groups for use by Lync Server 2013, and grants suitable access permissions on the Active Directory objects.</span></span> <span data-ttu-id="fae71-105">Per una descrizione dei gruppi universali e delle impostazioni globali e degli oggetti creati dalla preparazione della foresta, vedere [le modifiche apportate dalla preparazione della foresta in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span><span class="sxs-lookup"><span data-stu-id="fae71-105">For a description of the universal groups and the global settings and objects created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md).</span></span>

<span data-ttu-id="fae71-106">La preparazione della foresta crea inoltre oggetti che contengono set di proprietà e indicatori di visualizzazione usati da Lync Server 2013 e li archivia nel contenitore di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fae71-106">Forest preparation also creates objects that contain property sets and display specifiers that are used by Lync Server 2013, and stores them in the Configuration container.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fae71-107">Verificare che le modifiche apportate alla preparazione dello schema vengano replicate in tutti i controller di dominio prima di eseguire la procedura di preparazione della foresta.</span><span class="sxs-lookup"><span data-stu-id="fae71-107">Make sure that schema preparation changes have replicated to all domain controllers before performing the forest preparation procedure.</span></span> <span data-ttu-id="fae71-108">Se la replica non viene completata, si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="fae71-108">If replication is not completed, an error occurs.</span></span>



</div>

<span data-ttu-id="fae71-109">Se si esegue una nuova distribuzione di Lync Server, è necessario archiviare le impostazioni globali nel contenitore di configurazione.</span><span class="sxs-lookup"><span data-stu-id="fae71-109">If you are performing a new Lync Server deployment, you must store global settings in the Configuration container.</span></span> <span data-ttu-id="fae71-110">Se si esegue l'aggiornamento da una versione precedente e si memorizzano ancora le impostazioni globali nel contenitore di sistema, è possibile continuare a usare il contenitore di sistema.</span><span class="sxs-lookup"><span data-stu-id="fae71-110">If you are upgrading from an earlier version and you still store global settings in the System container, you can continue to use the System container.</span></span>

<span data-ttu-id="fae71-111">Per eseguire questa procedura, è necessario essere membri del gruppo amministratori dell'organizzazione o Domain Admins per il dominio radice della foresta.</span><span class="sxs-lookup"><span data-stu-id="fae71-111">You must be a member of the Enterprise Admins or Domain Admins group for the forest root domain to perform this procedure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fae71-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="fae71-112">In This Section</span></span>

  - [<span data-ttu-id="fae71-113">Esecuzione della preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fae71-113">Running forest preparation for Lync Server 2013</span></span>](lync-server-2013-running-forest-preparation.md)

  - [<span data-ttu-id="fae71-114">Utilizzo dei cmdlet per annullare la preparazione della foresta per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fae71-114">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

