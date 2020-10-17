---
title: 'Lync Server 2013: registrazione dettagli chiamata (CDR)'
description: 'Lync Server 2013: registrazione dettagli chiamata (CDR).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call detail recording (CDR)
ms:assetid: 67726075-c77c-4191-a64f-a1cf5c7bcbb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688079(v=OCS.15)
ms:contentKeyID: 49733675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590f99fd0b8649ffb3c4df039488dc54a8f3b7b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561792"
---
# <a name="call-detail-recording-cdr-in-lync-server-2013"></a><span data-ttu-id="cd7c4-103">Registrazione dettagli chiamata (CDR) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd7c4-103">Call detail recording (CDR) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd7c4-104">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="cd7c4-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="cd7c4-105">La funzionalità di registrazione dettagli chiamata (CDR) registra le informazioni di utilizzo e di diagnostica per le attività peer-to-peer, tra cui la messaggistica istantanea, le chiamate VoIP (Voice over Internet Protocol), la condivisione di applicazioni, il trasferimento file e le riunioni.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-105">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities, including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="cd7c4-106">I dati di utilizzo possono essere utilizzati per calcolare il rendimento dell'investimento, mentre i dati di diagnostica possono essere utilizzati per la risoluzione dei problemi relativi alle attività peer-to-peer e alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-106">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span> <span data-ttu-id="cd7c4-107">Quando si installa Lync Server 2013, verrà installata anche una raccolta predefinita di impostazioni di configurazione globali per CDR.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-107">When you install Lync Server 2013, you will also install a predefined collection of global configuration settings for CDR.</span></span> <span data-ttu-id="cd7c4-108">Utilizzare le informazioni negli argomenti di questa sezione per configurare la registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="cd7c4-108">Use the topics in this section to configure CDR.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cd7c4-109">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="cd7c4-109">In This Section</span></span>

  - [<span data-ttu-id="cd7c4-110">Visualizzare le informazioni di configurazione di registrazione dettagli chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd7c4-110">View CDR configuration information in Lync Server 2013</span></span>](lync-server-2013-view-cdr-configuration-information.md)

  - [<span data-ttu-id="cd7c4-111">Abilitare la registrazione dettagli chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd7c4-111">Enable call detail recording in Lync Server 2013</span></span>](lync-server-2013-enable-call-detail-recording.md)

  - [<span data-ttu-id="cd7c4-112">Creare o modificare una raccolta di impostazioni di configurazione di registrazione dettagli chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd7c4-112">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="cd7c4-113">Eliminare una raccolta esistente di impostazioni di configurazione di registrazione dettagli chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd7c4-113">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="cd7c4-114">Eliminazione manuale dei database di registrazione dettagli chiamata e qualità dei dati di utilizzo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd7c4-114">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>](lync-server-2013-manually-purging-the-call-detail-recording-and-quality-of-experience-databases.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cd7c4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd7c4-115">See Also</span></span>


[<span data-ttu-id="cd7c4-116">Configurazione delle impostazioni di registrazione dettagli chiamata e qualità delle esperienze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd7c4-116">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

