---
title: 'Lync Server 2013: esecuzione e monitoraggio dei backup'
description: 'Lync Server 2013: esecuzione e monitoraggio dei backup.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb8ce99e850f0918974be08eb10796ef1397225
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557232"
---
# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="44e49-103">Esecuzione e monitoraggio dei backup in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44e49-103">Performing and monitoring backups in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44e49-104">_**Ultimo argomento modificato:** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="44e49-104">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="44e49-105">Le priorità aziendali devono guidare la specifica dei requisiti di backup e ripristino per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="44e49-105">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="44e49-106">L'esecuzione di backup dei server e dei dati è la prima linea di difesa nella pianificazione di un evento di emergenza.</span><span class="sxs-lookup"><span data-stu-id="44e49-106">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="44e49-107">I computer che eseguono i servizi o i ruoli del server Lync Server 2013 devono disporre di una copia della topologia corrente, delle impostazioni di configurazione correnti e dei criteri correnti prima che possano funzionare nel ruolo nominato.</span><span class="sxs-lookup"><span data-stu-id="44e49-107">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="44e49-108">Lync Server è responsabile di garantire che tali informazioni vengano passate a ogni computer che ne ha bisogno.</span><span class="sxs-lookup"><span data-stu-id="44e49-108">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="44e49-109">I cmdlet **Export-CsConfiguration** e **Import-CsConfiguration** vengono utilizzati per eseguire il backup e il ripristino della topologia, delle impostazioni di configurazione e dei criteri di Lync Server durante un aggiornamento dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="44e49-109">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="44e49-110">I cmdlet **Export-CsConfiguration** consentono di esportare i dati in un. File ZIP.</span><span class="sxs-lookup"><span data-stu-id="44e49-110">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="44e49-111">È quindi possibile utilizzare il cmdlet **Import-CsConfiguration** per leggerlo. File ZIP e ripristino della topologia, delle impostazioni di configurazione e dei criteri nell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="44e49-111">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="44e49-112">Successivamente, i servizi di replica di Lync Server riplicheranno le informazioni ripristinate ad altri computer che eseguono i servizi di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44e49-112">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="44e49-113">La possibilità di esportare e importare i dati di configurazione viene utilizzata anche durante la configurazione iniziale dei computer che si trovano nella rete perimetrale (ad esempio, server perimetrali).</span><span class="sxs-lookup"><span data-stu-id="44e49-113">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="44e49-114">Quando si configura un computer nella rete perimetrale, è innanzitutto necessario eseguire una replica manuale utilizzando i cmdlet di CsConfiguration: è necessario esportare i dati di configurazione utilizzando **Export-CsConfiguration** e quindi copiare il. File ZIP nel computer della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="44e49-114">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="44e49-115">Poi sarà possibile utilizzare **Import-CsConfiguration** ed il parametro LocalStore per importare i dati.</span><span class="sxs-lookup"><span data-stu-id="44e49-115">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="44e49-116">È sufficiente eseguire questa operazione una sola volta.</span><span class="sxs-lookup"><span data-stu-id="44e49-116">You only have to do this one time.</span></span> <span data-ttu-id="44e49-117">Successivamente, la replica verrà eseguita automaticamente.</span><span class="sxs-lookup"><span data-stu-id="44e49-117">After that, replication will occur automatically.</span></span>

<span data-ttu-id="44e49-118">Utenti autorizzati a utilizzare questo cmdlet: per impostazione predefinita, il cmdlet **Export-CsConfiguration** può essere utilizzato localmente dai membri dei seguenti gruppi: RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="44e49-118">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="44e49-119">Per restituire un elenco di tutti i ruoli RBAC, questo cmdlet è assegnato a (compresi eventuali ruoli RBAC personalizzati creati personalmente), eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="44e49-119">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="44e49-120">È consigliabile eseguire il backup di tutti i database di SQL 2012 back-end secondo le [procedure consigliate di SQL](https://go.microsoft.com/fwlink/p/?linkid=290716).</span><span class="sxs-lookup"><span data-stu-id="44e49-120">All SQL 2012 Back End databases should be backed up as per [SQL best practices](https://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="44e49-121">I test regolari del piano di ripristino di emergenza per l'infrastruttura di Lync Server 2013 devono essere eseguiti in un ambiente lab che simula l'ambiente di produzione il più fedelmente possibile.</span><span class="sxs-lookup"><span data-stu-id="44e49-121">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="44e49-122">Fare riferimento alle attività mensili per ulteriori informazioni sui test di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="44e49-122">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="44e49-123">Si noti che la frequenza di backup può essere regolata, in base agli obiettivi del punto di ripristino e del punto di ripristino.</span><span class="sxs-lookup"><span data-stu-id="44e49-123">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="44e49-124">Come procedura consigliata, prendere periodicamente istantanee periodiche durante la giornata.</span><span class="sxs-lookup"><span data-stu-id="44e49-124">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="44e49-125">In generale, è consigliabile eseguire backup completi ogni 24 ore.</span><span class="sxs-lookup"><span data-stu-id="44e49-125">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="44e49-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44e49-126">See Also</span></span>


[<span data-ttu-id="44e49-127">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="44e49-127">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="44e49-128">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="44e49-128">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="44e49-129">Procedure consigliate per SQL</span><span class="sxs-lookup"><span data-stu-id="44e49-129">SQL best practices</span></span>](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

