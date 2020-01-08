---
title: 'Lync Server 2013: uso delle opzioni della riga di comando del programma di installazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5087c8ac777e5e2fd3259f925a4217a4d47dd800
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="7e0da-102">Uso delle opzioni della riga di comando di configurazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e0da-102">Using Setup command-line options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e0da-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="7e0da-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="7e0da-104">La riga di comando Setup. exe viene usata per pochissime operazioni in configurazione di Office.</span><span class="sxs-lookup"><span data-stu-id="7e0da-104">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="7e0da-105">Invece di usare le opzioni della riga di comando per la configurazione, in genere si usa lo strumento di personalizzazione di Office e il file config. XML per la configurazione del prodotto e la personalizzazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7e0da-105">Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="7e0da-106">La riga di comando di Office Setup. exe riconosce le opzioni della riga di comando descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7e0da-106">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="7e0da-107">Opzioni della riga di comando per l'installazione di Office</span><span class="sxs-lookup"><span data-stu-id="7e0da-107">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e0da-108">Opzione della riga di comando Setup</span><span class="sxs-lookup"><span data-stu-id="7e0da-108">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="7e0da-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7e0da-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e0da-110">/admin</span><span class="sxs-lookup"><span data-stu-id="7e0da-110">/admin</span></span></p></td>
<td><p><span data-ttu-id="7e0da-111">Esegue lo strumento di personalizzazione di Office per creare un file di personalizzazione della configurazione (file msp).</span><span class="sxs-lookup"><span data-stu-id="7e0da-111">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e0da-112">/adminfile [percorso]</span><span class="sxs-lookup"><span data-stu-id="7e0da-112">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="7e0da-113">Applica il file di personalizzazione della configurazione specificato all'installazione.</span><span class="sxs-lookup"><span data-stu-id="7e0da-113">Applies the specified Setup customization file to the installation.</span></span> <span data-ttu-id="7e0da-114">È possibile specificare un percorso di un file di personalizzazione specifico (file msp) o nella cartella in cui vengono archiviati i file di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="7e0da-114">You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e0da-115">/config [percorso]</span><span class="sxs-lookup"><span data-stu-id="7e0da-115">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="7e0da-116">Specifica il file config. XML usato dalla configurazione durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="7e0da-116">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="7e0da-117">Usare l'opzione/config per specificare il file config. XML personalizzato per le installazioni di Lync 2013, ad esempio:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="7e0da-117">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e0da-118">/Modify Lync</span><span class="sxs-lookup"><span data-stu-id="7e0da-118">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="7e0da-119">Usato con un file config. xml modificato per eseguire la configurazione in modalità manutenzione e apportare modifiche a un'installazione di Office esistente.</span><span class="sxs-lookup"><span data-stu-id="7e0da-119">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="7e0da-120">Ad esempio, puoi usare l'opzione/MODIFY per aggiungere o rimuovere le caratteristiche di Lync.</span><span class="sxs-lookup"><span data-stu-id="7e0da-120">For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e0da-121">/Repair Lync</span><span class="sxs-lookup"><span data-stu-id="7e0da-121">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="7e0da-122">Esegue la configurazione dal computer dell'utente per ripristinare Lync.</span><span class="sxs-lookup"><span data-stu-id="7e0da-122">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e0da-123">/Uninstall Lync</span><span class="sxs-lookup"><span data-stu-id="7e0da-123">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="7e0da-124">Esegue il programma di installazione per rimuovere Lync dal computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7e0da-124">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7e0da-125">Per informazioni dettagliate sull'uso delle opzioni della riga di comando per <http://go.microsoft.com/fwlink/p/?linkid=267515>la configurazione, vedere.</span><span class="sxs-lookup"><span data-stu-id="7e0da-125">For details about using the setup command-line options, see <http://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

