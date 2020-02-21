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
ms.openlocfilehash: 5fb1d4a51179326f15999f05f2f80649d7b9dec8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="68f85-102">Definizione dell'esperienza utente per l'acquisizione manuale di una posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68f85-102">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68f85-103">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="68f85-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="68f85-p101">Se un client si trova all'esterno della rete o in una subnet non definita, l'utente può immettere manualmente una posizione. La chiamata di emergenza però verrà innanzitutto instradata a un dispatcher ECRC (Emergency Call Response Center) del servizio E9-1-1 nazionale/regionale prima di essere instradata a un centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point). Il dispatcher ECRC richiederà verbalmente al chiamante la posizione e inoltrerà quindi la chiamata al centro PSAP appropriato in base alle informazioni fornite.</span><span class="sxs-lookup"><span data-stu-id="68f85-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span>

  - <span data-ttu-id="68f85-107">**È necessario che agli utenti venga richiesto di immettere un percorso quando uno non viene fornito automaticamente dal servizio informazioni percorso?**</span><span class="sxs-lookup"><span data-stu-id="68f85-107">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>  
    <span data-ttu-id="68f85-108">Se, ad esempio, un client si trova in una subnet non definita, a casa, in un albergo o in qualsiasi altro luogo esterno alla rete, è necessario richiedere all'utente la specifica di una posizione?</span><span class="sxs-lookup"><span data-stu-id="68f85-108">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
    <span data-ttu-id="68f85-p102">È possibile configurare l'impostazione **Posizione obbligatoria** nei criteri percorso per definire il comportamento del client. L'impostazione di questo valore su No indica che all'utente non verrà richiesta una posizione. Se invece si imposta il valore su Sì, all'utente verrà richiesta la specifica della posizione ma potrà ignorare il messaggio. Il valore Dichiarazione di non responsabilità indica invece che all'utente verrà richiesta una posizione e visualizzata una dichiarazione di non responsabilità se tenta di ignorare il messaggio. In tutti i casi, l'utente potrà continuare a utilizzare il client come sempre.</span><span class="sxs-lookup"><span data-stu-id="68f85-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>

<span data-ttu-id="68f85-p103">Quando un utente immette manualmente una posizione, tale posizione viene mappata all'indirizzo MAC del gateway predefinito della rete del client e archiviata in una tabella specifica dell'utente disponibile sul client. Quando l'utente ritorna a una posizione archiviata in precedenza, il client Lync viene automaticamente impostato su tale posizione.</span><span class="sxs-lookup"><span data-stu-id="68f85-p103">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client’s network, and is stored in a per-user table located on the client. When the user returns to any previously stored location, the Lync client automatically sets itself to that location.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="68f85-116">È possibile modificare solo la posizione corrente del client, nonché eliminare le posizioni archiviate nella tabella degli utenti locali.</span><span class="sxs-lookup"><span data-stu-id="68f85-116">You can modify only the current location of your client, but you can also delete any location stored in the local user’s table.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

