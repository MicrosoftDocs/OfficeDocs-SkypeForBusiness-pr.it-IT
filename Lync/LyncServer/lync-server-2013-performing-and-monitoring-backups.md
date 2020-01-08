---
title: 'Lync Server 2013: esecuzione e monitoraggio di backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fffc6a8355305e11d87513ffc37626f3e386c749
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a><span data-ttu-id="d4a03-102">Esecuzione e monitoraggio di backup in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4a03-102">Performing and monitoring backups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4a03-103">_**Argomento Ultima modifica:** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="d4a03-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="d4a03-104">Le priorità aziendali dovrebbero guidare la specifica dei requisiti di backup e ripristino per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d4a03-104">Your business priorities should drive the specification of backup and restoration requirements for your organization.</span></span> <span data-ttu-id="d4a03-105">L'esecuzione di backup dei server e dei dati è la prima linea di difesa nella pianificazione di un disastro.</span><span class="sxs-lookup"><span data-stu-id="d4a03-105">Performing backups of the servers and data is the first line of defense in planning for a disaster.</span></span>

<span data-ttu-id="d4a03-106">I computer che eseguono i servizi o i ruoli del server Lync Server 2013 devono avere una copia della topologia corrente, le impostazioni di configurazione correnti e i criteri correnti prima di poter funzionare nel loro ruolo nominato.</span><span class="sxs-lookup"><span data-stu-id="d4a03-106">Computers that run Lync Server 2013 services or server roles must have a copy of the current topology, current configuration settings, and current policies before they can function in their appointed role.</span></span> <span data-ttu-id="d4a03-107">Lync Server è responsabile per verificare che queste informazioni vengano passate a ogni computer che ne ha bisogno.</span><span class="sxs-lookup"><span data-stu-id="d4a03-107">Lync Server is responsible for making sure that this information is passed along to each computer that needs it.</span></span>

<span data-ttu-id="d4a03-108">I cmdlet **Export-CsConfiguration** e **Import-CsConfiguration** vengono usati per eseguire il backup e il ripristino della topologia, delle impostazioni di configurazione e dei criteri di Lync Server durante un aggiornamento di Central Management store.</span><span class="sxs-lookup"><span data-stu-id="d4a03-108">The **Export-CsConfiguration** and **Import-CsConfiguration** cmdlets are used to back up and restore your Lync Server topology, configuration settings, and policies during a Central Management store upgrade.</span></span> <span data-ttu-id="d4a03-109">I cmdlet **Export-CsConfiguration** consentono di esportare i dati in un. File ZIP.</span><span class="sxs-lookup"><span data-stu-id="d4a03-109">The **Export-CsConfiguration** cmdlets enable you to export data to a .ZIP file.</span></span> <span data-ttu-id="d4a03-110">Puoi quindi usare il cmdlet **Import-CsConfiguration** per leggerlo. File ZIP e ripristinare la topologia, le impostazioni di configurazione e i criteri per l'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="d4a03-110">You can then use the **Import-CsConfiguration** cmdlet to read that .ZIP file and restore the topology, configuration settings, and policies to the Central Management store.</span></span> <span data-ttu-id="d4a03-111">In seguito, i servizi di replica di Lync Server riplicheranno le informazioni ripristinate in altri computer che eseguono i servizi Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d4a03-111">After that, the replication services of Lync Server will replicate the restored information to other computers that are running Lync Server services.</span></span>

<span data-ttu-id="d4a03-112">La possibilità di esportare e importare dati di configurazione viene usata anche durante la configurazione iniziale dei computer che si trovano nella rete perimetrale (ad esempio, Edge Server).</span><span class="sxs-lookup"><span data-stu-id="d4a03-112">The ability to export and import configuration data is also used during the initial configuration of computers that are located in your perimeter network (for example, Edge Servers).</span></span> <span data-ttu-id="d4a03-113">Quando si configura un computer nella rete perimetrale, è necessario eseguire prima di tutto una replica manuale usando i cmdlet CsConfiguration: è necessario esportare i dati di configurazione tramite **Export-CsConfiguration** e quindi copiare il. File ZIP nel computer della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d4a03-113">When configuring a computer in the perimeter network, you must first perform a manual replication using the CsConfiguration cmdlets: you must export the configuration data by using **Export-CsConfiguration** and then copy the .ZIP file to the computer in the perimeter network.</span></span> <span data-ttu-id="d4a03-114">In seguito, puoi usare **Import-CsConfiguration** e il parametro LocalStore per importare i dati.</span><span class="sxs-lookup"><span data-stu-id="d4a03-114">After that, you can use **Import-CsConfiguration** and the LocalStore parameter to import the data.</span></span> <span data-ttu-id="d4a03-115">Devi solo eseguire questa operazione una sola volta.</span><span class="sxs-lookup"><span data-stu-id="d4a03-115">You only have to do this one time.</span></span> <span data-ttu-id="d4a03-116">In seguito, la replica si verificherà automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d4a03-116">After that, replication will occur automatically.</span></span>

<span data-ttu-id="d4a03-117">Utenti che possono eseguire questo cmdlet: per impostazione predefinita, i membri dei gruppi seguenti sono autorizzati a eseguire localmente il cmdlet **Export-CsConfiguration** : RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d4a03-117">Who can run this cmdlet: By default, members of the following groups are authorized to run the **Export-CsConfiguration** cmdlet locally: RTCUniversalServerAdmins.</span></span> <span data-ttu-id="d4a03-118">Per restituire un elenco di tutti i ruoli RBAC, questo cmdlet viene assegnato (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d4a03-118">To return a list of all RBAC roles, this cmdlet is assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

<span data-ttu-id="d4a03-119">È necessario eseguire il backup di tutti i database di SQL 2012 back-end in base alle [procedure consigliate SQL](http://go.microsoft.com/fwlink/p/?linkid=290716).</span><span class="sxs-lookup"><span data-stu-id="d4a03-119">All SQL 2012 Back End databases should be backed up as per [SQL best practices](http://go.microsoft.com/fwlink/p/?linkid=290716).</span></span>

<span data-ttu-id="d4a03-120">Il normale test del piano di ripristino di emergenza per l'infrastruttura di Lync Server 2013 deve essere eseguito in un ambiente lab che simula l'ambiente di produzione il più vicino possibile.</span><span class="sxs-lookup"><span data-stu-id="d4a03-120">Regular testing of the Disaster Recovery Plan for your Lync Server 2013 infrastructure should be performed in a lab environment that mimics the production environment as closely as possible.</span></span> <span data-ttu-id="d4a03-121">Per altre informazioni sui test di ripristino di emergenza, vedere le attività mensili.</span><span class="sxs-lookup"><span data-stu-id="d4a03-121">Refer to the Monthly Tasks for more information about Disaster Recovery Testing.</span></span>

<span data-ttu-id="d4a03-122">Tieni presente che la frequenza di backup può essere regolata in base agli obiettivi del punto di ripristino e del punto di ripristino.</span><span class="sxs-lookup"><span data-stu-id="d4a03-122">Note that the backup frequency can be adjusted, based on your Restore Point and Recovery Point objectives.</span></span> <span data-ttu-id="d4a03-123">Come procedura consigliata, eseguire istantanee periodiche regolari durante tutta la giornata.</span><span class="sxs-lookup"><span data-stu-id="d4a03-123">As a best practice, take regular, periodic snapshots throughout the day.</span></span> <span data-ttu-id="d4a03-124">In genere, è consigliabile eseguire backup completi ogni 24 ore.</span><span class="sxs-lookup"><span data-stu-id="d4a03-124">Generally, you should perform full backups every 24 hours.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d4a03-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4a03-125">See Also</span></span>


[<span data-ttu-id="d4a03-126">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d4a03-126">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="d4a03-127">Export-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="d4a03-127">Export-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[<span data-ttu-id="d4a03-128">Procedure consigliate per SQL</span><span class="sxs-lookup"><span data-stu-id="d4a03-128">SQL best practices</span></span>](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

