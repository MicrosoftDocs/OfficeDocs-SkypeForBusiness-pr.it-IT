---
title: Eseguire la migrazione di riunioni e di contenuto di riunioni esistenti
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38b4f374aef66fa95d49b2330a07f9def4135328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="34a56-102">Eseguire la migrazione di riunioni e di contenuto di riunioni esistenti</span><span class="sxs-lookup"><span data-stu-id="34a56-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34a56-103">_**Argomento Ultima modifica:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="34a56-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="34a56-104">Quando un account utente viene spostato da Lync Server 2010 a un server Lync Server 2013, le informazioni seguenti vengono spostate con l'account utente seguente:</span><span class="sxs-lookup"><span data-stu-id="34a56-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="34a56-105">**Riunioni già programmate dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="34a56-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="34a56-106">Questo include lo spostamento delle directory di conferenza e dei dati di conferenza.</span><span class="sxs-lookup"><span data-stu-id="34a56-106">This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="34a56-107">**Pin (Personal Identification Number) dell'utente**.</span><span class="sxs-lookup"><span data-stu-id="34a56-107">**User’s personal identification number (PIN)**.</span></span> <span data-ttu-id="34a56-108">Il PIN corrente dell'utente continuerà a funzionare finché non scade o l'utente richiede un nuovo PIN.</span><span class="sxs-lookup"><span data-stu-id="34a56-108">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="34a56-109">Le informazioni dell'account utente seguenti non vengono spostati nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="34a56-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="34a56-110">**Contenuto della riunione**.</span><span class="sxs-lookup"><span data-stu-id="34a56-110">**Meeting content**.</span></span> <span data-ttu-id="34a56-111">Per poter trasferire il contenuto condiviso durante una riunione, ad esempio PowerPoint, lavagna, allegati o dati di sondaggio, usa il parametro **-MoveConferenceData** come parte del cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="34a56-111">In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

