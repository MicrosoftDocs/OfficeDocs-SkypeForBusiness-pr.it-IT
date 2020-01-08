---
title: "Lync Server 2013: Eseguire la migrazione degli utenti nell'archivio contatti unificato"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0ec64192f1aa83eb9c076976c20a9e87ab9115
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980932"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="d9762-102">Eseguire la migrazione degli utenti nell'archivio contatti unificato in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9762-102">Migrate users to unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9762-103">_**Argomento Ultima modifica:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="d9762-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="d9762-104">I contatti di un utente vengono automaticamente migrati nel server di Exchange 2013 quando l'utente:</span><span class="sxs-lookup"><span data-stu-id="d9762-104">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="d9762-105">È stato assegnato un criterio servizi utente con UcsAllowed impostato su true.</span><span class="sxs-lookup"><span data-stu-id="d9762-105">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="d9762-106">È stato effettuato il provisioning con una cassetta postale di Exchange 2013 e ha eseguito l'accesso alla cassetta postale almeno una volta.</span><span class="sxs-lookup"><span data-stu-id="d9762-106">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="d9762-107">Accede utilizzando un client RTF di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="d9762-107">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="d9762-108">Se l'utente esegue l'accesso con un client Lync 2010 o versioni precedenti oppure se l'utente non è connesso a un server di Exchange 2013, il criterio servizi utente viene ignorato e i contatti dell'utente restano in Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d9762-108">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="d9762-109">Puoi determinare se i contatti di un utente sono stati migrati usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9762-109">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="d9762-110">Selezionare la chiave del registro di sistema seguente nel computer client:</span><span class="sxs-lookup"><span data-stu-id="d9762-110">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="d9762-111">HKEY\_software\_\\dell'\\utente corrente\\Microsoft\\Office\\15,0\\\<UCS SIP\>\\dell'URL di Lync</span><span class="sxs-lookup"><span data-stu-id="d9762-111">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="d9762-112">Se i contatti dell'utente sono archiviati in Exchange 2013, questa chiave contiene un valore di InUCSMode con il valore 2165.</span><span class="sxs-lookup"><span data-stu-id="d9762-112">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="d9762-113">Eseguire il cmdlet **Test-CsUnifiedContactStore** .</span><span class="sxs-lookup"><span data-stu-id="d9762-113">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="d9762-114">Nella riga di comando di Lync Server Management Shell digitare:</span><span class="sxs-lookup"><span data-stu-id="d9762-114">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="d9762-115">Se **Test-CsUnifiedContactStore** ha esito positivo, i contatti dell'utente sono stati migrati in archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="d9762-115">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

