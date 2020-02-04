---
title: Definizione dell'esperienza utente per l'acquisizione manuale di una posizione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b5913547ab7d5030ca40070de36b4deb1f6a89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="5d5fa-102">Definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d5fa-102">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d5fa-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="5d5fa-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="5d5fa-104">Se un client si trova all'esterno della rete o in una subnet non definita, l'utente può immettere manualmente una posizione.</span><span class="sxs-lookup"><span data-stu-id="5d5fa-104">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location.</span></span> <span data-ttu-id="5d5fa-105">Durante una chiamata di emergenza, però, la chiamata verrà prima instradata a un dispatcher di Emergency Call Centre (ECRC) National/Regional E9-1-1, prima di essere indirizzato a un punto di risposta di sicurezza pubblica (PSAP).</span><span class="sxs-lookup"><span data-stu-id="5d5fa-105">But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="5d5fa-106">ECRC eseguirà una query verbale sul chiamante per una posizione e quindi inoltra la chiamata al PSAP appropriato, in base alle informazioni fornite.</span><span class="sxs-lookup"><span data-stu-id="5d5fa-106">The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span>

  - <span data-ttu-id="5d5fa-107">**Gli utenti devono essere invitati a immettere una posizione quando non vengono forniti automaticamente dal servizio informazioni sulla posizione?**</span><span class="sxs-lookup"><span data-stu-id="5d5fa-107">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>  
    <span data-ttu-id="5d5fa-108">Ad esempio, se un client si trova in una subnet non definita, a casa, in un hotel o in qualsiasi altro punto all'esterno della rete, l'utente deve essere tenuto a immettere una posizione?</span><span class="sxs-lookup"><span data-stu-id="5d5fa-108">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
    <span data-ttu-id="5d5fa-109">Per definire il comportamento del client, è possibile configurare l'impostazione della **posizione necessaria** nel criterio della posizione.</span><span class="sxs-lookup"><span data-stu-id="5d5fa-109">You can configure the **Location Required** setting in the location policy to define the client behavior.</span></span> <span data-ttu-id="5d5fa-110">L'impostazione di questo valore non significa che l'utente non verrà richiesto per una posizione.</span><span class="sxs-lookup"><span data-stu-id="5d5fa-110">Setting this value to No means that the user will not be prompted for a location.</span></span> <span data-ttu-id="5d5fa-111">L'impostazione di questo valore su Sì significa che l'utente verrà richiesto per una posizione, ma può chiudere la richiesta.</span><span class="sxs-lookup"><span data-stu-id="5d5fa-111">Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="5d5fa-112">L'impostazione di questo valore su Disclaimer indica che all'utente verrà richiesto di trovare una posizione e verrà visualizzata una dichiarazione di non responsabilità se tenta di chiudere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="5d5fa-112">Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="5d5fa-113">In tutti i casi, l'utente può continuare a usare il client come di consueto.</span><span class="sxs-lookup"><span data-stu-id="5d5fa-113">In all cases, the user can continue to use the client as usual.</span></span>

<span data-ttu-id="5d5fa-114">Quando un utente immette manualmente una posizione, la posizione viene mappata all'indirizzo MAC del gateway predefinito della rete del client e viene archiviata in una tabella per utente che si trova nel client.</span><span class="sxs-lookup"><span data-stu-id="5d5fa-114">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client’s network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="5d5fa-115">Quando l'utente torna in una posizione archiviata in precedenza, il client Lync si imposta automaticamente in tale posizione.</span><span class="sxs-lookup"><span data-stu-id="5d5fa-115">When the user returns to any previously stored location, the Lync client automatically sets itself to that location.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5d5fa-116">È possibile modificare solo la posizione corrente del client, ma è anche possibile eliminare qualsiasi posizione archiviata nella tabella dell'utente locale.</span><span class="sxs-lookup"><span data-stu-id="5d5fa-116">You can modify only the current location of your client, but you can also delete any location stored in the local user’s table.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

