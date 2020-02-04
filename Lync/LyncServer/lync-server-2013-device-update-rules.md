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
ms.openlocfilehash: 4912497f1c8481d44b02a0213e01a0e8908ebfa2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="3deeb-102">Regole di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3deeb-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3deeb-103">_**Argomento Ultima modifica:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="3deeb-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="3deeb-104">Periodicamente, Microsoft rilascia un nuovo set di aggiornamenti del firmware per il dispositivo per Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="3deeb-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="3deeb-105">*Le regole di aggiornamento* dei dispositivi associano gli aggiornamenti del firmware a dispositivi hardware, telefoni e altri dispositivi che utilizzano Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="3deeb-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="3deeb-106">Per ottenere l'ultima serie di regole di aggiornamento dei dispositivi, accedere alla pagina della guida e del supporto nel sito Web Microsoft e cercare "edizione telefono".</span><span class="sxs-lookup"><span data-stu-id="3deeb-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="3deeb-107">Scaricare il pacchetto di aggiornamento ed estrarre i file in una cartella nel computer in cui devono essere caricati gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="3deeb-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="3deeb-108">Dopo l'estrazione dei file, importare le regole di aggiornamento dei dispositivi presenti nell'estratto. File CAB (con il nome UCUpdates. cab).</span><span class="sxs-lookup"><span data-stu-id="3deeb-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="3deeb-109">USA quindi il pannello di controllo di Lync Server o i cmdlet di Windows PowerShell per visualizzare e gestire queste regole per i dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3deeb-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="3deeb-110">Gli argomenti seguenti spiegano come importare, visualizzare e gestire le regole di aggiornamento dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3deeb-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3deeb-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3deeb-111">In This Section</span></span>

  - [<span data-ttu-id="3deeb-112">Visualizzare informazioni sulle regole di aggiornamento dei dispositivi in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3deeb-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="3deeb-113">Importare le regole di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3deeb-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="3deeb-114">Approvare una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3deeb-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="3deeb-115">Rimuovere una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3deeb-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="3deeb-116">Reimpostare una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3deeb-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="3deeb-117">Ripristinare una regola di aggiornamento del dispositivo in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3deeb-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

