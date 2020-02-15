---
title: 'Lync Server 2013: esportazione di dati archiviati'
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
ms.openlocfilehash: 4bb0bcb30c49a44fe92920d4db77d6bf9697cd9e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a>Esportazione di dati archiviati da Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

I dati archiviati nei database di archiviazione non possono essere ricercati o in un formato leggibile, ma è possibile utilizzare il cmdlet Export-CsArchivingData per estrarre i record dal database e salvarli come file di posta elettronica di Outlook (EML). Per informazioni dettagliate sull'esportazione di dati archiviati, vedere [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) nella documentazione relativa alle operazioni.

Se si Abilita l'integrazione di Microsoft Exchange, i dati vengono archiviati negli archivi di Exchange 2013. I dati archiviati in Exchange 2013 sono reperibili e individuabili. Per informazioni dettagliate sul supporto per le comunicazioni integrate per Exchange 2013 e Lync Server 2013, vedere [Exchange Server and SharePoint Integration Support in Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) nella documentazione relativa alla supportabilità. Per informazioni dettagliate sull'accesso ai dati archiviati in Exchange, vedere la documentazione di Exchange 2013.

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Esportazione dei dati di archiviazione mediante i cmdlet di Windows PowerShell

I dati di archiviazione possono essere esportati utilizzando il cmdlet Export-CSArchivingData. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

**Per esportare i dati di archiviazione**

  - Questo comando Esporta tutti i dati di archiviazione scritti nel database di archiviazione atl-sql-001.litwareinc.com dal 1 ° giugno 2012. Il file di output risultante verrà archiviato nella cartella C:\\ArchivingExports.
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**Per esportare i dati di archiviazione per un singolo utente**

  - Con il comando seguente vengono esportati i dati di archiviazione per un singolo utente: kenmyer@litwareinc.com. Per eseguire questa operazione, è necessario includere il parametro UserUri seguito dall'indirizzo SIP dell'utente. Ad esempio:
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Supporto per l'integrazione di Exchange Server e SharePoint in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[Gestione dell'archiviazione in Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

