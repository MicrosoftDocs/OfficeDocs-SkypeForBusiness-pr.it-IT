---
title: 'Lync Server 2013: convalida della configurazione di Office Web Apps Server'
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
ms.openlocfilehash: 541929233eff5e401b3998aa84e463e2640378c0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Convalida della configurazione di Office Web Apps Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-04-22_

Dopo che Office Web Apps Server è stato aggiunto alla topologia e dopo la pubblicazione di tale topologia, dovrebbero essere visualizzati due nuovi eventi del log eventi nel log eventi di Lync Server. Prima di tutto, è necessario aggiungere un evento MCU dati LS (ID evento 41034); Questo evento riporterà che il server Office Web Apps è stato individuato:

**Web Conferencing Server Office Web Apps Server viene individuato, il contenuto di PowerPoint è abilitato.**

Oltre a questo, dovrebbe essere visualizzato un altro evento di MCU dati LS (ID evento 41032) che riporta gli URL del server di Office Web Apps. Ad esempio, dovresti vedere qualcosa di simile a questo:

**L'individuazione del server Web Conferencing Server Office Web Apps è riuscita.**

**Pagina del relatore interno del server Office Web Apps:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Pagina partecipanti interni a Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Pagina del relatore esterno di Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Pagina partecipanti interni a Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Se viene visualizzato un evento di MCU dati LS con l'ID evento di 41033, significa che l'individuazione di Office Web Apps Server non è riuscita. In questo caso, Microsoft Lync Server 2013 tenterà tutte le volte necessarie per individuare il server Office Web Apps appena configurato. Se il processo di individuazione non riesce più volte, è necessario rimuovere Office Web Apps Server dal documento della topologia, pubblicare la topologia aggiornata e quindi provare a aggiungere Office Web Apps Server alla topologia dopo la risoluzione dei problemi di connettività.

Se il server Office Web Apps sembra configurato correttamente ed è stato riconosciuto dal processo di individuazione, è possibile verificare che Office Web Apps Server funzioni come previsto condividendo una presentazione di PowerPoint tra una coppia di client di Microsoft Lync 2013. Se l'utente A può caricare e visualizzare la presentazione di PowerPoint e se l'utente B può quindi partecipare alla riunione e vedere la presentazione, il server Office Web Apps funziona.

Anche se il server Office Web Apps sembra configurato correttamente, è possibile che venga visualizzato il messaggio di errore "alcune funzionalità di condivisione non sono disponibili a causa di problemi di connettività del server" quando si prova a condividere una presentazione di PowerPoint. Se viene visualizzato il messaggio di errore, è necessario riavviare il server front-end (o i server) associato al nuovo server Office Web Apps.

</div>

<span> </span>

</div>

</div>

</div>

