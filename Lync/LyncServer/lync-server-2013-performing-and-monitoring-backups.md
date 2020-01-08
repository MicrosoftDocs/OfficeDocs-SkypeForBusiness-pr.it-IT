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

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Esecuzione e monitoraggio di backup in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-15_

Le priorità aziendali dovrebbero guidare la specifica dei requisiti di backup e ripristino per l'organizzazione. L'esecuzione di backup dei server e dei dati è la prima linea di difesa nella pianificazione di un disastro.

I computer che eseguono i servizi o i ruoli del server Lync Server 2013 devono avere una copia della topologia corrente, le impostazioni di configurazione correnti e i criteri correnti prima di poter funzionare nel loro ruolo nominato. Lync Server è responsabile per verificare che queste informazioni vengano passate a ogni computer che ne ha bisogno.

I cmdlet **Export-CsConfiguration** e **Import-CsConfiguration** vengono usati per eseguire il backup e il ripristino della topologia, delle impostazioni di configurazione e dei criteri di Lync Server durante un aggiornamento di Central Management store. I cmdlet **Export-CsConfiguration** consentono di esportare i dati in un. File ZIP. Puoi quindi usare il cmdlet **Import-CsConfiguration** per leggerlo. File ZIP e ripristinare la topologia, le impostazioni di configurazione e i criteri per l'Central Management store. In seguito, i servizi di replica di Lync Server riplicheranno le informazioni ripristinate in altri computer che eseguono i servizi Lync Server.

La possibilità di esportare e importare dati di configurazione viene usata anche durante la configurazione iniziale dei computer che si trovano nella rete perimetrale (ad esempio, Edge Server). Quando si configura un computer nella rete perimetrale, è necessario eseguire prima di tutto una replica manuale usando i cmdlet CsConfiguration: è necessario esportare i dati di configurazione tramite **Export-CsConfiguration** e quindi copiare il. File ZIP nel computer della rete perimetrale. In seguito, puoi usare **Import-CsConfiguration** e il parametro LocalStore per importare i dati. Devi solo eseguire questa operazione una sola volta. In seguito, la replica si verificherà automaticamente.

Utenti che possono eseguire questo cmdlet: per impostazione predefinita, i membri dei gruppi seguenti sono autorizzati a eseguire localmente il cmdlet **Export-CsConfiguration** : RTCUniversalServerAdmins. Per restituire un elenco di tutti i ruoli RBAC, questo cmdlet viene assegnato (inclusi eventuali ruoli RBAC personalizzati creati manualmente), eseguire il comando seguente dal prompt di Windows PowerShell:

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

È necessario eseguire il backup di tutti i database di SQL 2012 back-end in base alle [procedure consigliate SQL](http://go.microsoft.com/fwlink/p/?linkid=290716).

Il normale test del piano di ripristino di emergenza per l'infrastruttura di Lync Server 2013 deve essere eseguito in un ambiente lab che simula l'ambiente di produzione il più vicino possibile. Per altre informazioni sui test di ripristino di emergenza, vedere le attività mensili.

Tieni presente che la frequenza di backup può essere regolata in base agli obiettivi del punto di ripristino e del punto di ripristino. Come procedura consigliata, eseguire istantanee periodiche regolari durante tutta la giornata. In genere, è consigliabile eseguire backup completi ogni 24 ore.

<div>

## <a name="see-also"></a>Vedere anche


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[Procedure consigliate per SQL](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

