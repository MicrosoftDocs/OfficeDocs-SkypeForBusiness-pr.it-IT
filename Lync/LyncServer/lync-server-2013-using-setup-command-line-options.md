---
title: 'Lync Server 2013: utilizzo delle opzioni della riga di comando del programma di installazione'
description: 'Lync Server 2013: utilizzo delle opzioni della riga di comando del programma di installazione.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15c3490ead090766462ce83cb13ffe62355032cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580242"
---
# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="34749-103">Utilizzo delle opzioni della riga di comando del programma di installazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34749-103">Using Setup command-line options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34749-104">_**Ultimo argomento modificato:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="34749-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="34749-p101">La riga di comando di Setup.exe consente di eseguire un numero limitato di operazioni di configurazione di Office. Invece di usare le opzioni della riga di comando di Setup, in genere si usa lo Strumento di personalizzazione di Office e il file the Config.xml per la personalizzazione delle caratteristiche e della configurazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="34749-p101">The Setup.exe command line is used for very few operations in Office setup. Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="34749-107">La riga di comando di Setup.exe di Office riconosce le opzioni descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="34749-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="34749-108">Opzioni della riga di comando del programma di installazione di Office</span><span class="sxs-lookup"><span data-stu-id="34749-108">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34749-109">Opzione della riga di comando</span><span class="sxs-lookup"><span data-stu-id="34749-109">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="34749-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34749-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34749-111">/admin</span><span class="sxs-lookup"><span data-stu-id="34749-111">/admin</span></span></p></td>
<td><p><span data-ttu-id="34749-112">Esegue lo Strumento di personalizzazione di Office per creare un file di personalizzazione della configurazione (file con estensione msp).</span><span class="sxs-lookup"><span data-stu-id="34749-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34749-113">/adminfile [percorso]</span><span class="sxs-lookup"><span data-stu-id="34749-113">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="34749-p102">Applica all'installazione il file di personalizzazione dell'installazione specificato. È possibile specificare il percorso di un determinato file di personalizzazione dell'installazione (msp) o della cartella in cui sono archiviati i file di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="34749-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34749-116">/config [percorso]</span><span class="sxs-lookup"><span data-stu-id="34749-116">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="34749-117">Specifica il file Config.xml utilizzato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="34749-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="34749-118">Utilizzare l'opzione/config per specificare il file Config.xml personalizzato per le installazioni di Lync 2013, ad esempio: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="34749-118">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34749-119">/modify Lync</span><span class="sxs-lookup"><span data-stu-id="34749-119">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="34749-p104">Usato con un file Config.xml modificato per eseguire il programma di installazione in modalità manutenzione e apportare modifiche a un'installazione di Office esistente. È ad esempio possibile usare l'opzione /modify per aggiungere o rimuovere caratteristiche di Lync.</span><span class="sxs-lookup"><span data-stu-id="34749-p104">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation. For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34749-122">/repair Lync</span><span class="sxs-lookup"><span data-stu-id="34749-122">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="34749-123">Esegue il programma di installazione nel computer dell'utente per ripristinare Lync.</span><span class="sxs-lookup"><span data-stu-id="34749-123">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34749-124">/uninstall Lync</span><span class="sxs-lookup"><span data-stu-id="34749-124">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="34749-125">Esegue il programma di installazione per rimuovere Lync dal computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="34749-125">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="34749-126">Per informazioni dettagliate sull'utilizzo delle opzioni della riga di comando del programma di installazione, vedere <https://go.microsoft.com/fwlink/p/?linkid=267515> .</span><span class="sxs-lookup"><span data-stu-id="34749-126">For details about using the setup command-line options, see <https://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

