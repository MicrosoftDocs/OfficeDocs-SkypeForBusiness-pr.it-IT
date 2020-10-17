---
title: 'Lync Server 2013: specificare le applicazioni client che è possibile utilizzare per accedere a Lync Server 2013'
description: 'Lync Server 2013: specificare le applicazioni client che è possibile utilizzare per accedere a Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying the client applications that can be used to log on to Lync Server 2013
ms:assetid: d256a581-9a48-4d1a-82cc-2e1f520d7d2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182591(v=OCS.15)
ms:contentKeyID: 48185450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 907f4b99f1aa87ccee62ad39fdaccad1aa9d256d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558372"
---
# <a name="specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013"></a><span data-ttu-id="b36aa-103">Specificare le applicazioni client che possono essere utilizzate per accedere a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b36aa-103">Specifying the client applications that can be used to log on to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b36aa-104">_**Ultimo argomento modificato:** 2012-12-11_</span><span class="sxs-lookup"><span data-stu-id="b36aa-104">_**Topic Last Modified:** 2012-12-11_</span></span>

<span data-ttu-id="b36aa-105">Lync Server 2013 consente di specificare la versione dei client supportati nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="b36aa-105">Lync Server 2013 enables you to specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="b36aa-106">L'utilizzo dei criteri di versione client può contribuire a ridurre i costi associati al supporto di più versioni client.</span><span class="sxs-lookup"><span data-stu-id="b36aa-106">Using client version policies can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="b36aa-107">È inoltre possibile migliorare l'esperienza complessiva degli utenti, perché quando le versioni precedenti e successive dei client interagiscono, le funzionalità disponibili possono essere limitate dalla versione precedente del client.</span><span class="sxs-lookup"><span data-stu-id="b36aa-107">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span>

<span data-ttu-id="b36aa-108">Sono disponibili tre componenti del controllo della versione client:</span><span class="sxs-lookup"><span data-stu-id="b36aa-108">There are three components of client version control:</span></span>

  - <span data-ttu-id="b36aa-109">Le impostazioni di configurazione della versione client vengono utilizzate per abilitare o disabilitare il controllo della versione client, a livello globale o per siti particolari.</span><span class="sxs-lookup"><span data-stu-id="b36aa-109">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span>

  - <span data-ttu-id="b36aa-110">I criteri di versione client vengono utilizzati per assegnare un set di regole a livello globale o a un sito, a un pool o a un gruppo di utenti specifico.</span><span class="sxs-lookup"><span data-stu-id="b36aa-110">Client version policies are used to assign a set of rules globally, or to a particular site, pool, or group of users.</span></span>

  - <span data-ttu-id="b36aa-111">Le regole dei criteri di versione client costituiscono un criterio di versione client e vengono utilizzate per definire le azioni da eseguire quando gli utenti tentano di accedere con client e versioni client specifici.</span><span class="sxs-lookup"><span data-stu-id="b36aa-111">Client version policy rules make up a client version policy, and are used to define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b36aa-112">Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.</span><span class="sxs-lookup"><span data-stu-id="b36aa-112">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b36aa-113">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="b36aa-113">In This Section</span></span>

  - [<span data-ttu-id="b36aa-114">Impostazioni di configurazione della versione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b36aa-114">Client version configuration settings in Lync Server 2013</span></span>](lync-server-2013-client-version-configuration-settings.md)

  - [<span data-ttu-id="b36aa-115">Criteri versione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b36aa-115">Client version policies in Lync Server 2013</span></span>](lync-server-2013-client-version-policies.md)

  - [<span data-ttu-id="b36aa-116">Regole sulla versione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b36aa-116">Client version rules in Lync Server 2013</span></span>](lync-server-2013-client-version-rules.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b36aa-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b36aa-117">See Also</span></span>


[<span data-ttu-id="b36aa-118">Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b36aa-118">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

