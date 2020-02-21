---
title: 'Lync Server 2013: convalidare la configurazione del server Office Web Apps'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068c3fcfd33668918eb330b64d816ceca818de27
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Convalidare la configurazione del server Office Web Apps in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-04-22_

Dopo che il server Office Web Apps è stato aggiunto alla topologia e dopo la pubblicazione della topologia, dovrebbero essere visualizzati due nuovi eventi del registro eventi nel registro eventi di Lync Server. Per prima cosa, è necessario aggiungere un evento MCU dati LS (ID evento 41034). Questo evento riporterà che il server Office Web Apps è stato individuato:

**Server Web Conferencing Server Office Web Apps è stato rilevato, il contenuto di PowerPoint è abilitato.**

Inoltre, dovrebbe essere visualizzato un altro evento LS Data MCU (ID evento 41032) che restituisce gli URL di Office Web Apps Server. Ad esempio, dovrebbe essere visualizzato un evento simile al seguente:

**Individuazione del server Web Conferencing Server Office Web Apps ha avuto esito positivo.**

**Pagina del relatore interno del server Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Pagina partecipante interno al server Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Pagina del relatore esterno del server Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Pagina partecipante interno al server Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Se viene visualizzato un evento LS Data MCU con ID evento 41033, l'individuazione di Office Web Apps Server ha avuto esito negativo. In questo caso, Microsoft Lync Server 2013 tenterà tutte le volte necessarie per individuare il server Office Web Apps appena configurato. Se è impossibile eseguire il processo di individuazione, è necessario rimuovere Office Web Apps Server dal documento relativo alla topologia, pubblicare la topologia aggiornata e quindi tentare di aggiungere di nuovo Office Web Apps Server alla topologia dopo avere risolto i problemi di connettività.

Se il server Office Web Apps sembra configurato correttamente ed è stato riconosciuto dal processo di individuazione, è possibile verificare che il server Office Web Apps funzioni come previsto condividendo una presentazione di PowerPoint tra una coppia di client Microsoft Lync 2013. Se l'utente A può caricare e visualizzare la presentazione di PowerPoint e l'utente B può partecipare alla riunione e visualizzare la presentazione, Office Web Apps Server funziona correttamente.

Anche se Office Web Apps Server sembra configurato correttamente, si potrebbe ricevere il messaggio di errore "Alcune funzionalità di condivisione non sono disponibili a causa di problemi di connettività del server" quando si tenta di condividere una presentazione di PowerPoint. Se si riceve questo messaggio di errore, riavviare i Front End Server associati al nuovo Office Web Apps Server.

</div>

<span> </span>

</div>

</div>

</div>

