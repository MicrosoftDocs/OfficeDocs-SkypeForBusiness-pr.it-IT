---
title: 'Lync Server 2013: utilizzo di Config.xml per eseguire le attività di installazione'
description: 'Lync Server 2013: utilizzo di Config.xml per eseguire le attività di installazione.'
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
ms.openlocfilehash: 22fff14e21a120c3a0ee2cd6432fd1eba2bbee5f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580402"
---
# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a><span data-ttu-id="82fca-103">Utilizzo di Config.xml per eseguire le attività di installazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82fca-103">Using Config.xml to perform installation tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82fca-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="82fca-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="82fca-105">Anche se lo strumento di personalizzazione di Office è lo strumento principale per l'installazione della personalizzazione, gli amministratori possono utilizzare il file Config.xml per specificare ulteriori istruzioni di installazione che non sono disponibili nel set di strumenti.</span><span class="sxs-lookup"><span data-stu-id="82fca-105">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT.</span></span> <span data-ttu-id="82fca-106">È possibile eseguire le personalizzazioni seguenti solo mediante il file Config.xml:</span><span class="sxs-lookup"><span data-stu-id="82fca-106">The following customizations can only be made by using the Config.xml file:</span></span>

  - <span data-ttu-id="82fca-107">Specificare il percorso del punto di installazione di rete.</span><span class="sxs-lookup"><span data-stu-id="82fca-107">Specify the path of the network installation point.</span></span>

  - <span data-ttu-id="82fca-108">Selezionare i prodotti da installare.</span><span class="sxs-lookup"><span data-stu-id="82fca-108">Select the products to install.</span></span>

  - <span data-ttu-id="82fca-109">Configurare la registrazione e il percorso del file di personalizzazione dell'installazione e degli aggiornamenti software.</span><span class="sxs-lookup"><span data-stu-id="82fca-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

  - <span data-ttu-id="82fca-110">Specificare le opzioni di installazione, ad esempio il nome utente.</span><span class="sxs-lookup"><span data-stu-id="82fca-110">Specify installation options, such as user name.</span></span>

  - <span data-ttu-id="82fca-111">Copiare l'origine di installazione locale nel computer dell'utente senza installare Office.</span><span class="sxs-lookup"><span data-stu-id="82fca-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

  - <span data-ttu-id="82fca-112">Aggiungere o rimuovere lingue dall'installazione.</span><span class="sxs-lookup"><span data-stu-id="82fca-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="82fca-113">È consigliabile utilizzare il file Config.xml per configurare l'installazione invisibile all'utente di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="82fca-113">We recommend that you use the Config.xml file to configure Lync 2013 silent installation.</span></span>

<span data-ttu-id="82fca-114">Per impostazione predefinita, il file di Config.xml memorizzato nella cartella di base del prodotto, ad esempio \\ Product. WW) indirizza il programma di installazione per l'installazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="82fca-114">By default, the Config.xml file that is stored in the core product folder (for example, \\product.WW) directs Setup to install that product.</span></span> <span data-ttu-id="82fca-115">Ad esempio, il file di Config.xml nella cartella seguente consente di installare Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="82fca-115">For example, the Config.xml file in the following folder installs Lync 2013:</span></span>

  - <span data-ttu-id="82fca-116">\\\\condivisione del server \\ \\ Lync15 \\ Lync. WW \\Config.xml</span><span class="sxs-lookup"><span data-stu-id="82fca-116">\\\\server\\share\\Lync15\\Lync.WW \\Config.xml</span></span>

<span data-ttu-id="82fca-117">Nella tabella seguente sono elencati gli elementi di Config.xml più comunemente utilizzati per l'installazione di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="82fca-117">The Config.xml elements most commonly used for Lync 2013 installation are listed in the following table.</span></span>

### <a name="configxml-elements"></a><span data-ttu-id="82fca-118">Elementi Config.xml</span><span class="sxs-lookup"><span data-stu-id="82fca-118">Config.xml elements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82fca-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="82fca-119">Element</span></span></th>
<th><span data-ttu-id="82fca-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82fca-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82fca-121">Configurazione</span><span class="sxs-lookup"><span data-stu-id="82fca-121">Configuration</span></span></p></td>
<td><p><span data-ttu-id="82fca-122">Elemento di primo livello (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="82fca-122">Top-level element (required).</span></span> <span data-ttu-id="82fca-123">Contiene l'attributo Product, ad esempio: Product = Lync</span><span class="sxs-lookup"><span data-stu-id="82fca-123">Contains the Product attribute, for example: Product=Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82fca-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="82fca-124">OptionState</span></span></p></td>
<td><p><span data-ttu-id="82fca-125">Specifica come vengono gestite caratteristiche specifiche del prodotto durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="82fca-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="82fca-126">Utilizzare gli attributi seguenti per impedire l'installazione di servizi di integrazione applicativa, che include componenti condivisi che interferiscono con Outlook 2010:</span><span class="sxs-lookup"><span data-stu-id="82fca-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2010:</span></span></p>
<ul>
<li><p><span data-ttu-id="82fca-127">ID = &quot; LOBiMain&quot;</span><span class="sxs-lookup"><span data-stu-id="82fca-127">Id=&quot;LOBiMain&quot;</span></span></p></li>
<li><p><span data-ttu-id="82fca-128">Stato = &quot; assente&quot;</span><span class="sxs-lookup"><span data-stu-id="82fca-128">State=&quot;Absent&quot;</span></span></p></li>
<li><p><span data-ttu-id="82fca-129">Children = &quot; Force&quot;</span><span class="sxs-lookup"><span data-stu-id="82fca-129">Children=&quot;Force&quot;</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82fca-130">Visualizza</span><span class="sxs-lookup"><span data-stu-id="82fca-130">Display</span></span></p></td>
<td><p><span data-ttu-id="82fca-131">Livello di interfaccia utente visualizzato all'utente dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="82fca-131">The level of UI that Setup displays to the user.</span></span> <span data-ttu-id="82fca-132">Tra gli attributi tipici sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="82fca-132">Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="82fca-133">CompletionNotice = &quot; Yes &quot;  |  &quot; No &quot; (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="82fca-133">CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
<li><p><span data-ttu-id="82fca-134">AcceptEula = &quot; Yes &quot;  |  &quot; No &quot; (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="82fca-134">AcceptEula=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82fca-135">Registrazione</span><span class="sxs-lookup"><span data-stu-id="82fca-135">Logging</span></span></p></td>
<td><p><span data-ttu-id="82fca-136">Opzioni per il tipo di registrazione eseguita dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="82fca-136">Options for the kind of logging that Setup performs.</span></span> <span data-ttu-id="82fca-137">Tra gli attributi tipici sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="82fca-137">Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="82fca-138">Type = &quot; off &quot;  |  &quot; standard &quot; (impostazione predefinita) | &quot; Verbose&quot;</span><span class="sxs-lookup"><span data-stu-id="82fca-138">Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</span></span></p></li>
<li><p><span data-ttu-id="82fca-139">Template = "filename.txt" (il nome del file di log)</span><span class="sxs-lookup"><span data-stu-id="82fca-139">Template=”filename.txt” (the name of the log file)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82fca-140">Impostazione</span><span class="sxs-lookup"><span data-stu-id="82fca-140">Setting</span></span></p></td>
<td><p><span data-ttu-id="82fca-141">Specifica i valori per le proprietà di Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="82fca-141">Specifies values for Windows Installer properties.</span></span> <span data-ttu-id="82fca-142">Tra gli attributi tipici sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="82fca-142">Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="82fca-143">Impostazione ID = &quot; Name &quot; (il nome della proprietà di Windows Installer)</span><span class="sxs-lookup"><span data-stu-id="82fca-143">Setting Id=&quot;name&quot; (the name of the Windows Installer property)</span></span></p></li>
<li><p><span data-ttu-id="82fca-144">Valore = &quot; valore &quot; (valore da assegnare alla proprietà)</span><span class="sxs-lookup"><span data-stu-id="82fca-144">Value=&quot;value&quot; (the value to assign to the property)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82fca-145">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="82fca-145">DistributionPoint</span></span></p></td>
<td><p><span data-ttu-id="82fca-146">Percorso completo del punto di installazione di rete da cui deve essere eseguita l'installazione</span><span class="sxs-lookup"><span data-stu-id="82fca-146">The fully qualified path of the network installation point from which the installation is to run.</span></span> <span data-ttu-id="82fca-147">Include l'attributo location:</span><span class="sxs-lookup"><span data-stu-id="82fca-147">Includes the Location attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="82fca-148">Location = "percorso"</span><span class="sxs-lookup"><span data-stu-id="82fca-148">Location=”path”</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="82fca-149">Nell'esempio seguente viene illustrato un file di Config.xml per una tipica installazione invisibile all'utente di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="82fca-149">The following example shows a Config.xml file for a typical silent installation of Lync 2013.</span></span>

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

<span data-ttu-id="82fca-150">Informazioni dettagliate sull'utilizzo del file di Config.xml per eseguire le attività di installazione e manutenzione di Office sono disponibili all'indirizzo <https://go.microsoft.com/fwlink/p/?linkid=267514> .</span><span class="sxs-lookup"><span data-stu-id="82fca-150">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at <https://go.microsoft.com/fwlink/p/?linkid=267514>.</span></span>

<div>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="82fca-151">Per personalizzare il file di Config.xml</span><span class="sxs-lookup"><span data-stu-id="82fca-151">To customize the Config.xml file</span></span>

1.  <span data-ttu-id="82fca-152">Aprire il file Config.xml utilizzando uno strumento di editor di testo, ad esempio il blocco note.</span><span class="sxs-lookup"><span data-stu-id="82fca-152">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2.  <span data-ttu-id="82fca-153">Individuare le righe che contengono gli elementi che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="82fca-153">Locate the lines that contain the elements you want to change.</span></span>

3.  <span data-ttu-id="82fca-154">Modificare la voce dell'elemento con le opzioni Silent che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="82fca-154">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="82fca-155">Assicurarsi di rimuovere i delimitatori dei commenti " \<\!--" and "--\> ".</span><span class="sxs-lookup"><span data-stu-id="82fca-155">Make sure that you remove the comment delimiters, "\<\!--" and "--\>".</span></span> <span data-ttu-id="82fca-156">Utilizzare ad esempio la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="82fca-156">For example, use the following syntax:</span></span>
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  <span data-ttu-id="82fca-157">Salvare il file Config.xml.</span><span class="sxs-lookup"><span data-stu-id="82fca-157">Save the Config.xml file.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

