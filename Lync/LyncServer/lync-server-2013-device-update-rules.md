---
title: 'Lync Server 2013: regole di aggiornamento del dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update rules
ms:assetid: a2f7e293-3342-4566-9605-410cb95f3b3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994062(v=OCS.15)
ms:contentKeyID: 51803973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b52fa2f2aefae05f713972df5c3b15e6db7c0b57
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="f9704-102">Regole di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9704-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9704-103">_**Ultimo argomento modificato:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="f9704-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="f9704-104">Periodicamente, Microsoft rilascia una nuova serie di aggiornamenti del firmware del dispositivo per Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="f9704-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="f9704-105">*Le regole di aggiornamento* dei dispositivi associano gli aggiornamenti del firmware ai dispositivi hardware, ovvero telefoni e altri dispositivi che eseguono Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="f9704-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="f9704-106">Per ottenere l'ultimo set di regole di aggiornamento dei dispositivi, passare alla pagina Guida e supporto del sito Web Microsoft e cercare "edizione Phone".</span><span class="sxs-lookup"><span data-stu-id="f9704-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="f9704-107">Scaricare il pacchetto di aggiornamento ed estrarre i file in una cartella nel computer in cui devono essere caricati gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="f9704-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="f9704-108">Dopo l'estrazione dei file, importare le regole di aggiornamento dei dispositivi rilevate nell'estratto. File CAB (con il nome UCUpdates. cab).</span><span class="sxs-lookup"><span data-stu-id="f9704-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="f9704-109">Successivamente, utilizzare il pannello di controllo di Lync Server o i cmdlet di Windows PowerShell per visualizzare e gestire tali regole per i dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f9704-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="f9704-110">Negli argomenti seguenti viene illustrato come importare, visualizzare e gestire le regole di aggiornamento dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="f9704-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f9704-111">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="f9704-111">In This Section</span></span>

  - [<span data-ttu-id="f9704-112">Visualizzare informazioni sulle regole di aggiornamento dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9704-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="f9704-113">Importare le regole di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9704-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="f9704-114">Approvazione di una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9704-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="f9704-115">Rimuovere una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9704-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="f9704-116">Reimpostare una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9704-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="f9704-117">Ripristinare una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9704-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

