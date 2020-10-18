---
title: Eseguire la migrazione di riunioni e di contenuto di riunioni esistenti
description: Eseguire la migrazione di riunioni esistenti e del contenuto delle riunioni.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d94dd35063a121a057a218c27fdb36e42a155b77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579312"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="de37a-103">Eseguire la migrazione di riunioni e di contenuto di riunioni esistenti</span><span class="sxs-lookup"><span data-stu-id="de37a-103">Migrate existing meetings and meeting content</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de37a-104">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="de37a-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="de37a-105">Quando un account utente viene spostato da Lync Server 2010 a un server Lync Server 2013, le informazioni seguenti vengono spostate con l'account utente seguente:</span><span class="sxs-lookup"><span data-stu-id="de37a-105">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="de37a-p101">**Le riunioni già pianificate dall'utente**. Vengono spostate anche le directory e i dati delle conferenze.</span><span class="sxs-lookup"><span data-stu-id="de37a-p101">**Meetings already scheduled by the user**. This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="de37a-p102">**Il PIN dell'utente**. Il PIN corrente dell'utente continua a funzionare fino alla scadenza o alla richiesta di un nuovo PIN da parte dell'utente stesso.</span><span class="sxs-lookup"><span data-stu-id="de37a-p102">**User’s personal identification number (PIN)**. The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="de37a-110">Le seguenti informazioni sull'account utente non vengono spostate nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="de37a-110">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="de37a-p103">**Contenuto delle riunioni**. Per spostare il contenuto condiviso durante una riunione, ad esempio PowerPoint, Lavagna, allegati o dati dei sondaggi, usare il parametro **-MoveConferenceData** come parte del cmdlet **Move-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="de37a-p103">**Meeting content**. In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

