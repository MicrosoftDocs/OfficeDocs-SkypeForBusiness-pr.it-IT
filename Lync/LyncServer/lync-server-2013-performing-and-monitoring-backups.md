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
# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Esecuzione e monitoraggio dei backup in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-15_

Le priorità aziendali devono guidare la specifica dei requisiti di backup e ripristino per l'organizzazione. L'esecuzione di backup dei server e dei dati è la prima linea di difesa nella pianificazione di un evento di emergenza.

I computer che eseguono i servizi o i ruoli del server Lync Server 2013 devono disporre di una copia della topologia corrente, delle impostazioni di configurazione correnti e dei criteri correnti prima che possano funzionare nel ruolo nominato. Lync Server è responsabile di garantire che tali informazioni vengano passate a ogni computer che ne ha bisogno.

I cmdlet **Export-CsConfiguration** e **Import-CsConfiguration** vengono utilizzati per eseguire il backup e il ripristino della topologia, delle impostazioni di configurazione e dei criteri di Lync Server durante un aggiornamento dell'archivio di gestione centrale. I cmdlet **Export-CsConfiguration** consentono di esportare i dati in un. File ZIP. È quindi possibile utilizzare il cmdlet **Import-CsConfiguration** per leggerlo. File ZIP e ripristino della topologia, delle impostazioni di configurazione e dei criteri nell'archivio di gestione centrale. Successivamente, i servizi di replica di Lync Server riplicheranno le informazioni ripristinate ad altri computer che eseguono i servizi di Lync Server.

La possibilità di esportare e importare i dati di configurazione viene utilizzata anche durante la configurazione iniziale dei computer che si trovano nella rete perimetrale (ad esempio, server perimetrali). Quando si configura un computer nella rete perimetrale, è innanzitutto necessario eseguire una replica manuale utilizzando i cmdlet di CsConfiguration: è necessario esportare i dati di configurazione utilizzando **Export-CsConfiguration** e quindi copiare il. File ZIP nel computer della rete perimetrale. Poi sarà possibile utilizzare **Import-CsConfiguration** ed il parametro LocalStore per importare i dati. È sufficiente eseguire questa operazione una sola volta. Successivamente, la replica verrà eseguita automaticamente.

Utenti autorizzati a utilizzare questo cmdlet: per impostazione predefinita, il cmdlet **Export-CsConfiguration** può essere utilizzato localmente dai membri dei seguenti gruppi: RTCUniversalServerAdmins. Per restituire un elenco di tutti i ruoli RBAC, questo cmdlet è assegnato a (compresi eventuali ruoli RBAC personalizzati creati personalmente), eseguire il comando seguente dal prompt di Windows PowerShell:

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

È consigliabile eseguire il backup di tutti i database di SQL 2012 back-end secondo le [procedure consigliate di SQL](https://go.microsoft.com/fwlink/p/?linkid=290716).

I test regolari del piano di ripristino di emergenza per l'infrastruttura di Lync Server 2013 devono essere eseguiti in un ambiente lab che simula l'ambiente di produzione il più fedelmente possibile. Fare riferimento alle attività mensili per ulteriori informazioni sui test di ripristino di emergenza.

Si noti che la frequenza di backup può essere regolata, in base agli obiettivi del punto di ripristino e del punto di ripristino. Come procedura consigliata, prendere periodicamente istantanee periodiche durante la giornata. In generale, è consigliabile eseguire backup completi ogni 24 ore.

<div>

## <a name="see-also"></a>Vedere anche


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[Procedure consigliate per SQL](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

