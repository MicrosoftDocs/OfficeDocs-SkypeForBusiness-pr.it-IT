---
title: 'Lync Server 2013: uso di config. XML per eseguire attività di installazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b6e037f2c69e963e8ca5963a71dabe80f9c75fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a><span data-ttu-id="7c988-102">Uso di config. XML per eseguire attività di installazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7c988-102">Using Config.xml to perform installation tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c988-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7c988-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7c988-104">Anche se lo strumento di personalizzazione di Office (OCT) è lo strumento principale per l'installazione di personalizzazione, gli amministratori possono usare il file config. XML per specificare altre istruzioni per l'installazione che non sono disponibili in ottobre.</span><span class="sxs-lookup"><span data-stu-id="7c988-104">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT.</span></span> <span data-ttu-id="7c988-105">Le personalizzazioni seguenti possono essere eseguite solo usando il file config. XML:</span><span class="sxs-lookup"><span data-stu-id="7c988-105">The following customizations can only be made by using the Config.xml file:</span></span>

  - <span data-ttu-id="7c988-106">Specificare il percorso del punto di installazione della rete.</span><span class="sxs-lookup"><span data-stu-id="7c988-106">Specify the path of the network installation point.</span></span>

  - <span data-ttu-id="7c988-107">Selezionare i prodotti da installare.</span><span class="sxs-lookup"><span data-stu-id="7c988-107">Select the products to install.</span></span>

  - <span data-ttu-id="7c988-108">Configurare la registrazione e la posizione del file di personalizzazione della configurazione e degli aggiornamenti software.</span><span class="sxs-lookup"><span data-stu-id="7c988-108">Configure logging and the location of the Setup customization file and software updates.</span></span>

  - <span data-ttu-id="7c988-109">Specificare le opzioni di installazione, ad esempio nome utente.</span><span class="sxs-lookup"><span data-stu-id="7c988-109">Specify installation options, such as user name.</span></span>

  - <span data-ttu-id="7c988-110">Copiare l'origine di installazione locale (LIS) nel computer dell'utente senza installare Office.</span><span class="sxs-lookup"><span data-stu-id="7c988-110">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

  - <span data-ttu-id="7c988-111">Aggiungere o rimuovere lingue dall'installazione.</span><span class="sxs-lookup"><span data-stu-id="7c988-111">Add or remove languages from the installation.</span></span>

<span data-ttu-id="7c988-112">È consigliabile usare il file config. XML per configurare l'installazione invisibile di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="7c988-112">We recommend that you use the Config.xml file to configure Lync 2013 silent installation.</span></span>

<span data-ttu-id="7c988-113">Per impostazione predefinita, il file config. xml archiviato nella cartella principale del prodotto, ad esempio \\Product. WW) indirizza la configurazione per l'installazione di tale prodotto.</span><span class="sxs-lookup"><span data-stu-id="7c988-113">By default, the Config.xml file that is stored in the core product folder (for example, \\product.WW) directs Setup to install that product.</span></span> <span data-ttu-id="7c988-114">Ad esempio, il file config. XML nella cartella seguente installa Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="7c988-114">For example, the Config.xml file in the following folder installs Lync 2013:</span></span>

  - <span data-ttu-id="7c988-115">\\\\condivisione\\\\del server\\Lync15 Lync. \\WW config. XML</span><span class="sxs-lookup"><span data-stu-id="7c988-115">\\\\server\\share\\Lync15\\Lync.WW \\Config.xml</span></span>

<span data-ttu-id="7c988-116">Gli elementi config. XML usati più comunemente per l'installazione di Lync 2013 sono elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="7c988-116">The Config.xml elements most commonly used for Lync 2013 installation are listed in the following table.</span></span>

### <a name="configxml-elements"></a><span data-ttu-id="7c988-117">Elementi config. XML</span><span class="sxs-lookup"><span data-stu-id="7c988-117">Config.xml elements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c988-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="7c988-118">Element</span></span></th>
<th><span data-ttu-id="7c988-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c988-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c988-120">Configurazione</span><span class="sxs-lookup"><span data-stu-id="7c988-120">Configuration</span></span></p></td>
<td><p><span data-ttu-id="7c988-121">Elemento di primo livello (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="7c988-121">Top-level element (required).</span></span> <span data-ttu-id="7c988-122">Contiene l'attributo Product, ad esempio: Product = Lync</span><span class="sxs-lookup"><span data-stu-id="7c988-122">Contains the Product attribute, for example: Product=Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c988-123">OptionState</span><span class="sxs-lookup"><span data-stu-id="7c988-123">OptionState</span></span></p></td>
<td><p><span data-ttu-id="7c988-124">Specifica il modo in cui vengono gestite le caratteristiche specifiche del prodotto durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="7c988-124">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="7c988-125">Usare gli attributi seguenti per impedire l'installazione di servizi di integrazione applicativa, che includono componenti condivisi che interferiscono con Outlook 2010:</span><span class="sxs-lookup"><span data-stu-id="7c988-125">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2010:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c988-126">ID =&quot;LOBiMain&quot;</span><span class="sxs-lookup"><span data-stu-id="7c988-126">Id=&quot;LOBiMain&quot;</span></span></p></li>
<li><p><span data-ttu-id="7c988-127">Stato =&quot;assente&quot;</span><span class="sxs-lookup"><span data-stu-id="7c988-127">State=&quot;Absent&quot;</span></span></p></li>
<li><p><span data-ttu-id="7c988-128">Children =&quot;Force&quot;</span><span class="sxs-lookup"><span data-stu-id="7c988-128">Children=&quot;Force&quot;</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c988-129">Visualizzare</span><span class="sxs-lookup"><span data-stu-id="7c988-129">Display</span></span></p></td>
<td><p><span data-ttu-id="7c988-130">Il livello di interfaccia utente visualizzato per l'installazione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="7c988-130">The level of UI that Setup displays to the user.</span></span> <span data-ttu-id="7c988-131">Gli attributi tipici includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c988-131">Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c988-132">CompletionNotice =&quot;Sì&quot; | &quot;No&quot;(impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="7c988-132">CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
<li><p><span data-ttu-id="7c988-133">AcceptEula =&quot;Sì&quot; | &quot;No&quot;(impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="7c988-133">AcceptEula=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c988-134">Registrazione</span><span class="sxs-lookup"><span data-stu-id="7c988-134">Logging</span></span></p></td>
<td><p><span data-ttu-id="7c988-135">Opzioni per il tipo di registrazione eseguito dall'installazione.</span><span class="sxs-lookup"><span data-stu-id="7c988-135">Options for the kind of logging that Setup performs.</span></span> <span data-ttu-id="7c988-136">Gli attributi tipici includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c988-136">Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c988-137">Digitare =&quot;off&quot; | &quot;standard&quot;(impostazione predefinita) | &quot;Verbose&quot;</span><span class="sxs-lookup"><span data-stu-id="7c988-137">Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</span></span></p></li>
<li><p><span data-ttu-id="7c988-138">Template = "nomefile. txt" (il nome del file di log)</span><span class="sxs-lookup"><span data-stu-id="7c988-138">Template=”filename.txt” (the name of the log file)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c988-139">Impostazione</span><span class="sxs-lookup"><span data-stu-id="7c988-139">Setting</span></span></p></td>
<td><p><span data-ttu-id="7c988-140">Specifica i valori per le proprietà di Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="7c988-140">Specifies values for Windows Installer properties.</span></span> <span data-ttu-id="7c988-141">Gli attributi tipici includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c988-141">Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c988-142">Impostazione di ID&quot;=&quot; Name (nome della proprietà di Windows Installer)</span><span class="sxs-lookup"><span data-stu-id="7c988-142">Setting Id=&quot;name&quot; (the name of the Windows Installer property)</span></span></p></li>
<li><p><span data-ttu-id="7c988-143">Valore =&quot;valore&quot; (il valore da assegnare alla proprietà)</span><span class="sxs-lookup"><span data-stu-id="7c988-143">Value=&quot;value&quot; (the value to assign to the property)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c988-144">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="7c988-144">DistributionPoint</span></span></p></td>
<td><p><span data-ttu-id="7c988-145">Percorso completo del punto di installazione di rete da cui eseguire l'installazione.</span><span class="sxs-lookup"><span data-stu-id="7c988-145">The fully qualified path of the network installation point from which the installation is to run.</span></span> <span data-ttu-id="7c988-146">Include l'attributo location:</span><span class="sxs-lookup"><span data-stu-id="7c988-146">Includes the Location attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="7c988-147">Location = "Path"</span><span class="sxs-lookup"><span data-stu-id="7c988-147">Location=”path”</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7c988-148">L'esempio seguente mostra un file config. XML per una tipica installazione silenziosa di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="7c988-148">The following example shows a Config.xml file for a typical silent installation of Lync 2013.</span></span>

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

<span data-ttu-id="7c988-149">Informazioni dettagliate sull'uso del file config. XML per eseguire attività di installazione e manutenzione di Office sono <http://go.microsoft.com/fwlink/p/?linkid=267514>disponibili all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="7c988-149">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at <http://go.microsoft.com/fwlink/p/?linkid=267514>.</span></span>

<div>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="7c988-150">Per personalizzare il file config. XML</span><span class="sxs-lookup"><span data-stu-id="7c988-150">To customize the Config.xml file</span></span>

1.  <span data-ttu-id="7c988-151">Aprire il file config. XML usando uno strumento di editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="7c988-151">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2.  <span data-ttu-id="7c988-152">Individuare le righe che contengono gli elementi che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="7c988-152">Locate the lines that contain the elements you want to change.</span></span>

3.  <span data-ttu-id="7c988-153">Modificare la voce dell'elemento con le opzioni Silent che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="7c988-153">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="7c988-154">Assicurati di rimuovere i delimitatori di commento, "\<\!--" e "--\>".</span><span class="sxs-lookup"><span data-stu-id="7c988-154">Make sure that you remove the comment delimiters, "\<\!--" and "--\>".</span></span> <span data-ttu-id="7c988-155">Ad esempio, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="7c988-155">For example, use the following syntax:</span></span>
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  <span data-ttu-id="7c988-156">Salvare il file config. XML.</span><span class="sxs-lookup"><span data-stu-id="7c988-156">Save the Config.xml file.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

