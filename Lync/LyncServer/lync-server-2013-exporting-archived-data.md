---
title: 'Lync Server 2013: esportazione di dati archiviati'
description: 'Lync Server 2013: esportazione di dati archiviati.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656751f1a2d03b50f0c938a8501ba3e95e304cff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564752"
---
# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="581f0-103">Esportazione di dati archiviati da Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="581f0-103">Exporting archived data from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="581f0-104">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="581f0-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="581f0-105">I dati archiviati nei database di archiviazione non possono essere ricercati o in un formato leggibile, ma è possibile utilizzare il cmdlet Export-CsArchivingData per estrarre i record dal database e salvarli come file di posta elettronica di Outlook (EML).</span><span class="sxs-lookup"><span data-stu-id="581f0-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="581f0-106">Per informazioni dettagliate sull'esportazione di dati archiviati, vedere [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="581f0-106">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="581f0-107">Se si Abilita l'integrazione di Microsoft Exchange, i dati vengono archiviati negli archivi di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="581f0-107">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="581f0-108">I dati archiviati in Exchange 2013 sono reperibili e individuabili.</span><span class="sxs-lookup"><span data-stu-id="581f0-108">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="581f0-109">Per informazioni dettagliate sul supporto per le comunicazioni integrate per Exchange 2013 e Lync Server 2013, vedere [Exchange Server and SharePoint Integration Support in Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="581f0-109">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="581f0-110">Per informazioni dettagliate sull'accesso ai dati archiviati in Exchange, vedere la documentazione di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="581f0-110">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="581f0-111">Esportazione dei dati di archiviazione mediante i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="581f0-111">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="581f0-112">I dati di archiviazione possono essere esportati utilizzando il cmdlet Export-CSArchivingData.</span><span class="sxs-lookup"><span data-stu-id="581f0-112">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="581f0-113">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="581f0-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="581f0-114">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="581f0-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="581f0-115">**Per esportare i dati di archiviazione**</span><span class="sxs-lookup"><span data-stu-id="581f0-115">**To export archiving data**</span></span>

  - <span data-ttu-id="581f0-116">Questo comando Esporta tutti i dati di archiviazione scritti nel database di archiviazione atl-sql-001.litwareinc.com dal 1 ° giugno 2012.</span><span class="sxs-lookup"><span data-stu-id="581f0-116">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="581f0-117">Il file di output risultante verrà archiviato nella cartella C: \\ ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="581f0-117">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="581f0-118">**Per esportare i dati di archiviazione per un singolo utente**</span><span class="sxs-lookup"><span data-stu-id="581f0-118">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="581f0-119">Con il comando seguente vengono esportati i dati di archiviazione per un singolo utente: kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="581f0-119">The following command exports archiving data for a single user: kenmyer@litwareinc.com.</span></span> <span data-ttu-id="581f0-120">Per eseguire questa operazione, è necessario includere il parametro UserUri seguito dall'indirizzo SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="581f0-120">This is done by including the UserUri parameter followed by the user’s SIP address.</span></span> <span data-ttu-id="581f0-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="581f0-121">For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="581f0-122">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .</span><span class="sxs-lookup"><span data-stu-id="581f0-122">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="581f0-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="581f0-123">See Also</span></span>


[<span data-ttu-id="581f0-124">Supporto per l'integrazione di Exchange Server e SharePoint in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="581f0-124">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="581f0-125">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="581f0-125">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="581f0-126">Gestione dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="581f0-126">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

