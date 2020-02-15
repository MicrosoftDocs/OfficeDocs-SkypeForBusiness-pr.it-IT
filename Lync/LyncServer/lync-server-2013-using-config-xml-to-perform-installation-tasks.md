---
title: 'Lync Server 2013: utilizzo del file config. XML per eseguire le attività di installazione'
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
ms.openlocfilehash: 2adadafcbb5338f47aa13d25b3dfd39386935b30
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a><span data-ttu-id="5b9ca-102">Utilizzo di config. XML per eseguire le attività di installazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b9ca-102">Using Config.xml to perform installation tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b9ca-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5b9ca-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5b9ca-104">Anche se lo strumento di personalizzazione di Office è lo strumento principale per l'installazione della personalizzazione, gli amministratori possono utilizzare il file config. XML per specificare ulteriori istruzioni di installazione che non sono disponibili nel set di strumenti.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-104">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT.</span></span> <span data-ttu-id="5b9ca-105">È possibile eseguire le personalizzazioni seguenti solo mediante il file Config.xml:</span><span class="sxs-lookup"><span data-stu-id="5b9ca-105">The following customizations can only be made by using the Config.xml file:</span></span>

  - <span data-ttu-id="5b9ca-106">Specificare il percorso del punto di installazione di rete.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-106">Specify the path of the network installation point.</span></span>

  - <span data-ttu-id="5b9ca-107">Selezionare i prodotti da installare.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-107">Select the products to install.</span></span>

  - <span data-ttu-id="5b9ca-108">Configurare la registrazione e il percorso del file di personalizzazione dell'installazione e degli aggiornamenti software.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-108">Configure logging and the location of the Setup customization file and software updates.</span></span>

  - <span data-ttu-id="5b9ca-109">Specificare le opzioni di installazione, ad esempio il nome utente.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-109">Specify installation options, such as user name.</span></span>

  - <span data-ttu-id="5b9ca-110">Copiare l'origine di installazione locale nel computer dell'utente senza installare Office.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-110">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

  - <span data-ttu-id="5b9ca-111">Aggiungere o rimuovere lingue dall'installazione.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-111">Add or remove languages from the installation.</span></span>

<span data-ttu-id="5b9ca-112">È consigliabile utilizzare il file config. XML per configurare l'installazione invisibile all'utente di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-112">We recommend that you use the Config.xml file to configure Lync 2013 silent installation.</span></span>

<span data-ttu-id="5b9ca-113">Per impostazione predefinita, il file config. XML memorizzato nella cartella di base del prodotto, \\ad esempio Product. WW) indirizza il programma di installazione per l'installazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-113">By default, the Config.xml file that is stored in the core product folder (for example, \\product.WW) directs Setup to install that product.</span></span> <span data-ttu-id="5b9ca-114">Ad esempio, il file config. XML nella cartella seguente consente di installare Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="5b9ca-114">For example, the Config.xml file in the following folder installs Lync 2013:</span></span>

  - <span data-ttu-id="5b9ca-115">\\\\condivisione\\\\server Lync15\\Lync. WW \\config. XML</span><span class="sxs-lookup"><span data-stu-id="5b9ca-115">\\\\server\\share\\Lync15\\Lync.WW \\Config.xml</span></span>

<span data-ttu-id="5b9ca-116">Nella tabella seguente sono elencati gli elementi config. XML più comunemente utilizzati per l'installazione di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-116">The Config.xml elements most commonly used for Lync 2013 installation are listed in the following table.</span></span>

### <a name="configxml-elements"></a><span data-ttu-id="5b9ca-117">Elementi config. XML</span><span class="sxs-lookup"><span data-stu-id="5b9ca-117">Config.xml elements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b9ca-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b9ca-118">Element</span></span></th>
<th><span data-ttu-id="5b9ca-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b9ca-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b9ca-120">Configurazione</span><span class="sxs-lookup"><span data-stu-id="5b9ca-120">Configuration</span></span></p></td>
<td><p><span data-ttu-id="5b9ca-121">Elemento di primo livello (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="5b9ca-121">Top-level element (required).</span></span> <span data-ttu-id="5b9ca-122">Contiene l'attributo Product, ad esempio: Product = Lync</span><span class="sxs-lookup"><span data-stu-id="5b9ca-122">Contains the Product attribute, for example: Product=Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b9ca-123">OptionState</span><span class="sxs-lookup"><span data-stu-id="5b9ca-123">OptionState</span></span></p></td>
<td><p><span data-ttu-id="5b9ca-124">Specifica come vengono gestite caratteristiche specifiche del prodotto durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-124">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="5b9ca-125">Utilizzare gli attributi seguenti per impedire l'installazione di servizi di integrazione applicativa, che include componenti condivisi che interferiscono con Outlook 2010:</span><span class="sxs-lookup"><span data-stu-id="5b9ca-125">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2010:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b9ca-126">ID =&quot;LOBiMain&quot;</span><span class="sxs-lookup"><span data-stu-id="5b9ca-126">Id=&quot;LOBiMain&quot;</span></span></p></li>
<li><p><span data-ttu-id="5b9ca-127">Stato =&quot;assente&quot;</span><span class="sxs-lookup"><span data-stu-id="5b9ca-127">State=&quot;Absent&quot;</span></span></p></li>
<li><p><span data-ttu-id="5b9ca-128">Children =&quot;Force&quot;</span><span class="sxs-lookup"><span data-stu-id="5b9ca-128">Children=&quot;Force&quot;</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b9ca-129">Schermo</span><span class="sxs-lookup"><span data-stu-id="5b9ca-129">Display</span></span></p></td>
<td><p><span data-ttu-id="5b9ca-130">Livello di interfaccia utente visualizzato all'utente dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-130">The level of UI that Setup displays to the user.</span></span> <span data-ttu-id="5b9ca-131">Tra gli attributi tipici sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b9ca-131">Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b9ca-132">CompletionNotice =&quot;Yes&quot; | &quot;No&quot;(impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="5b9ca-132">CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
<li><p><span data-ttu-id="5b9ca-133">AcceptEula =&quot;Yes&quot; | &quot;No&quot;(impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="5b9ca-133">AcceptEula=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b9ca-134">Registrazione</span><span class="sxs-lookup"><span data-stu-id="5b9ca-134">Logging</span></span></p></td>
<td><p><span data-ttu-id="5b9ca-135">Opzioni per il tipo di registrazione eseguita dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-135">Options for the kind of logging that Setup performs.</span></span> <span data-ttu-id="5b9ca-136">Tra gli attributi tipici sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b9ca-136">Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b9ca-137">Type =&quot;off&quot; | &quot;standard&quot;(impostazione predefinita) | &quot;Verbose&quot;</span><span class="sxs-lookup"><span data-stu-id="5b9ca-137">Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</span></span></p></li>
<li><p><span data-ttu-id="5b9ca-138">Template = "nomefile. txt" (il nome del file di registro)</span><span class="sxs-lookup"><span data-stu-id="5b9ca-138">Template=”filename.txt” (the name of the log file)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b9ca-139">Impostazione</span><span class="sxs-lookup"><span data-stu-id="5b9ca-139">Setting</span></span></p></td>
<td><p><span data-ttu-id="5b9ca-140">Specifica i valori per le proprietà di Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-140">Specifies values for Windows Installer properties.</span></span> <span data-ttu-id="5b9ca-141">Tra gli attributi tipici sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b9ca-141">Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b9ca-142">Impostazione ID =&quot;Name&quot; (il nome della proprietà di Windows Installer)</span><span class="sxs-lookup"><span data-stu-id="5b9ca-142">Setting Id=&quot;name&quot; (the name of the Windows Installer property)</span></span></p></li>
<li><p><span data-ttu-id="5b9ca-143">Valore =&quot;valore&quot; (valore da assegnare alla proprietà)</span><span class="sxs-lookup"><span data-stu-id="5b9ca-143">Value=&quot;value&quot; (the value to assign to the property)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b9ca-144">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="5b9ca-144">DistributionPoint</span></span></p></td>
<td><p><span data-ttu-id="5b9ca-145">Percorso completo del punto di installazione di rete da cui deve essere eseguita l'installazione</span><span class="sxs-lookup"><span data-stu-id="5b9ca-145">The fully qualified path of the network installation point from which the installation is to run.</span></span> <span data-ttu-id="5b9ca-146">Include l'attributo location:</span><span class="sxs-lookup"><span data-stu-id="5b9ca-146">Includes the Location attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b9ca-147">Location = "percorso"</span><span class="sxs-lookup"><span data-stu-id="5b9ca-147">Location=”path”</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5b9ca-148">Nell'esempio seguente viene illustrato un file config. XML per una tipica installazione invisibile all'utente di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-148">The following example shows a Config.xml file for a typical silent installation of Lync 2013.</span></span>

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

<span data-ttu-id="5b9ca-149">Informazioni dettagliate sull'utilizzo del file config. XML per eseguire le attività di installazione e manutenzione di Office <http://go.microsoft.com/fwlink/p/?linkid=267514>sono disponibili all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-149">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at <http://go.microsoft.com/fwlink/p/?linkid=267514>.</span></span>

<div>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="5b9ca-150">Per personalizzare il file config. XML</span><span class="sxs-lookup"><span data-stu-id="5b9ca-150">To customize the Config.xml file</span></span>

1.  <span data-ttu-id="5b9ca-151">Aprire il file config. XML utilizzando uno strumento di editor di testo, ad esempio il blocco note.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-151">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2.  <span data-ttu-id="5b9ca-152">Individuare le righe che contengono gli elementi che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-152">Locate the lines that contain the elements you want to change.</span></span>

3.  <span data-ttu-id="5b9ca-153">Modificare la voce dell'elemento con le opzioni Silent che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-153">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="5b9ca-154">Assicurarsi di rimuovere i delimitatori dei commenti, "\<\!--" e "--\>".</span><span class="sxs-lookup"><span data-stu-id="5b9ca-154">Make sure that you remove the comment delimiters, "\<\!--" and "--\>".</span></span> <span data-ttu-id="5b9ca-155">Utilizzare ad esempio la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5b9ca-155">For example, use the following syntax:</span></span>
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  <span data-ttu-id="5b9ca-156">Salvare il file Config.xml.</span><span class="sxs-lookup"><span data-stu-id="5b9ca-156">Save the Config.xml file.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

