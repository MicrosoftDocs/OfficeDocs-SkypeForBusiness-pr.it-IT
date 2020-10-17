---
title: "Lync Server 2013: eseguire la migrazione degli utenti nell'archivio contatti unificato"
description: "Lync Server 2013: eseguire la migrazione degli utenti nell'archivio contatti unificato."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e9ee9850cc723ae132f15d7c0c6b3769e1240ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568592"
---
# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="f886b-103">Eseguire la migrazione degli utenti nell'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f886b-103">Migrate users to unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f886b-104">_**Ultimo argomento modificato:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="f886b-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="f886b-105">I contatti di un utente vengono migrati automaticamente al server Exchange 2013 quando l'utente:</span><span class="sxs-lookup"><span data-stu-id="f886b-105">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="f886b-106">All'utente sono stati assegnati servizi utente per cui UcsAllowed è impostato su True.</span><span class="sxs-lookup"><span data-stu-id="f886b-106">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="f886b-107">È stato effettuato il provisioning con una cassetta postale di Exchange 2013 e ha eseguito l'accesso almeno una volta alla cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="f886b-107">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="f886b-108">Esegue l'accesso utilizzando un rich client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="f886b-108">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="f886b-109">Se l'utente esegue l'accesso con un client Lync 2010 o versioni precedenti o se l'utente non è connesso a un server Exchange 2013, i criteri di servizi utente vengono ignorati e i contatti dell'utente restano in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f886b-109">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="f886b-110">È possibile stabilire se i contatti di un utente sono stati migrati usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f886b-110">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="f886b-111">Verificare la chiave del Registro di sistema seguente nel computer client:</span><span class="sxs-lookup"><span data-stu-id="f886b-111">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="f886b-112">\_Software utente corrente di HKEY \_ \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ \<SIP URL\> \\ UCS</span><span class="sxs-lookup"><span data-stu-id="f886b-112">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="f886b-113">Se i contatti dell'utente sono archiviati in Exchange 2013, questa chiave contiene un valore di InUCSMode con un valore pari a 2165.</span><span class="sxs-lookup"><span data-stu-id="f886b-113">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="f886b-114">Eseguire il cmdlet **Test-CsUnifiedContactStore**.</span><span class="sxs-lookup"><span data-stu-id="f886b-114">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="f886b-115">Nella riga di comando di Lync Server Management Shell digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f886b-115">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="f886b-116">Se **Test-CsUnifiedContactStore** ha esito positivo, i contatti dell'utente sono stati migrati nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="f886b-116">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

