---
title: 'Lync Server 2013: gestione delle chiamate ai numeri non assegnati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b09be36c372473fc6700669f069646ca3f6054d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505893"
---
# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="743a5-102">Gestione delle chiamate a numeri non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="743a5-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="743a5-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="743a5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="743a5-104">Lync Server consente di configurare la gestione delle chiamate in arrivo quando il numero composto è valido per l'organizzazione, ma non è assegnato a un utente o a un telefono.</span><span class="sxs-lookup"><span data-stu-id="743a5-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="743a5-105">È possibile utilizzare l'applicazione annuncio per trasferire le chiamate a una destinazione predeterminata (numero di telefono, URI SIP o segreteria telefonica) oppure riprodurre un annuncio audio o entrambi.</span><span class="sxs-lookup"><span data-stu-id="743a5-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="743a5-106">È inoltre possibile trasferire tali chiamate a un numero di telefono operatore automatico della messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="743a5-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="743a5-107">La gestione delle chiamate a numeri non assegnati in uno di questi modi consente di evitare le situazioni in cui un chiamante compone un numero errato e sente un segnale di linea occupata oppure in cui il client SIP riceve un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="743a5-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="743a5-p102">In questa sezione viene illustrato come gestire gli intervalli di numeri non assegnati per gestire le chiamate a numeri di telefono non assegnati. Nella sezione viene inoltre illustrato come gestire gli annunci durante un ripristino di emergenza se si desidera tale funzionalità durante un'interruzione del servizio.</span><span class="sxs-lookup"><span data-stu-id="743a5-p102">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers. The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="743a5-110">L'utilizzo della gestione dei numeri non assegnati durante un'interruzione del servizio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="743a5-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="743a5-111">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="743a5-111">In This Section</span></span>

  - [<span data-ttu-id="743a5-112">Creare un annuncio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="743a5-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="743a5-113">Configurare i numeri di telefono non assegnati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="743a5-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="743a5-114">Gestire gli annunci durante il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="743a5-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

