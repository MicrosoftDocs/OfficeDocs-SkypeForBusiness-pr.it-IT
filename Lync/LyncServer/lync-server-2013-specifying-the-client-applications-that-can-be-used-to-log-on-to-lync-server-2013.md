---
title: 'Lync Server 2013: specificare le applicazioni client che è possibile usare per accedere a Lync Server 2013'
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
ms.openlocfilehash: 788a0638dee6b9d52a5d954eafb7b4e33bdfd294
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013"></a><span data-ttu-id="4449b-102">Specifica delle applicazioni client che possono essere usate per accedere a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4449b-102">Specifying the client applications that can be used to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4449b-103">_**Argomento Ultima modifica:** 2012-12-11_</span><span class="sxs-lookup"><span data-stu-id="4449b-103">_**Topic Last Modified:** 2012-12-11_</span></span>

<span data-ttu-id="4449b-104">Lync Server 2013 consente di specificare la versione dei client supportati nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4449b-104">Lync Server 2013 enables you to specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="4449b-105">L'uso dei criteri di versione client consente di ridurre i costi associati al supporto di più versioni client.</span><span class="sxs-lookup"><span data-stu-id="4449b-105">Using client version policies can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="4449b-106">Può anche migliorare l'esperienza utente complessiva, perché quando le versioni precedenti e successive dei client interagiscono, le funzionalità disponibili possono essere limitate dalla versione precedente del client.</span><span class="sxs-lookup"><span data-stu-id="4449b-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span>

<span data-ttu-id="4449b-107">Sono disponibili tre componenti del controllo della versione client:</span><span class="sxs-lookup"><span data-stu-id="4449b-107">There are three components of client version control:</span></span>

  - <span data-ttu-id="4449b-108">Le impostazioni di configurazione della versione client vengono usate per attivare o disattivare il controllo della versione client, sia a livello globale che per siti particolari.</span><span class="sxs-lookup"><span data-stu-id="4449b-108">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span>

  - <span data-ttu-id="4449b-109">I criteri di versione client vengono usati per assegnare un set di regole a livello globale o a un sito, un pool o un gruppo di utenti specifico.</span><span class="sxs-lookup"><span data-stu-id="4449b-109">Client version policies are used to assign a set of rules globally, or to a particular site, pool, or group of users.</span></span>

  - <span data-ttu-id="4449b-110">Le regole dei criteri di versione client costituiscono un criterio di versione client e vengono usate per definire le azioni da intraprendere quando gli utenti tentano di accedere con client e versioni client specifici.</span><span class="sxs-lookup"><span data-stu-id="4449b-110">Client version policy rules make up a client version policy, and are used to define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4449b-111">Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.</span><span class="sxs-lookup"><span data-stu-id="4449b-111">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4449b-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4449b-112">In This Section</span></span>

  - [<span data-ttu-id="4449b-113">Impostazioni di configurazione della versione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4449b-113">Client version configuration settings in Lync Server 2013</span></span>](lync-server-2013-client-version-configuration-settings.md)

  - [<span data-ttu-id="4449b-114">Criteri di versione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4449b-114">Client version policies in Lync Server 2013</span></span>](lync-server-2013-client-version-policies.md)

  - [<span data-ttu-id="4449b-115">Regole della versione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4449b-115">Client version rules in Lync Server 2013</span></span>](lync-server-2013-client-version-rules.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4449b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4449b-116">See Also</span></span>


[<span data-ttu-id="4449b-117">Gestione di dispositivi, telefoni e applicazioni client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4449b-117">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

