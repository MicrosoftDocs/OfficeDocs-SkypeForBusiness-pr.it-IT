---
title: 'Lync Server 2013: ripristino di un server membro Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0643cf250e00b447bfac8a1b32c2a3038cff139
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>Ripristino di un server membro Enterprise Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-18_

Se un server che esegue uno dei ruoli del server seguenti ha esito negativo, seguire la procedura descritta in questo argomento per ripristinare il server. Se si verificano errori indipendenti in più server, seguire la procedura per ogni server.

  - Front End Server

  - Mediation Server

  - Director

  - server Persistent Chat

  - Edge Server

<div>


> [!TIP]  
> Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema. È possibile utilizzare questa immagine come punto di rollback, in caso di problemi durante il ripristino. È possibile che si desideri prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare nuovamente i certificati.



</div>

<div>

## <a name="to-restore-a-member-server"></a>Per ripristinare un server membro

1.  Iniziare con un server pulito o nuovo con lo stesso nome di dominio completo (FQDN) del server in cui si è verificato l'errore, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.
    
    <div>
    

    > [!NOTE]  
    > Seguire le procedure di distribuzione dei server dell'organizzazione per eseguire questa operazione.

    
    </div>

2.  Da un account utente membro del gruppo RTCUniversalServerAdmins, eseguire l'accesso al server che si sta ripristinando.

3.  Passare alla cartella o al supporto di installazione di Lync Server e avviare la distribuzione guidata di Lync Server \\in\\Setup\\amd64 Setup. exe.

4.  Utilizzare la Distribuzione guidata per eseguire le operazioni seguenti:
    
    1.  Eseguire **Passaggio 1: Installazione dell'archivio di configurazione locale** per installare i file della configurazione locale.
    
    2.  Eseguire il **passaggio 2: installazione o rimozione componenti di Lync Server** per installare il ruolo del server Lync Server.
    
    3.  Eseguire **Passaggio 3: Richiesta, installazione o assegnazione dei certificati** per assegnare i certificati.
    
    4.  Eseguire **Passaggio 4: Avvio servizi** per avviare i servizi nel server.
    
    Per informazioni dettagliate sull'esecuzione della distribuzione guidata, vedere la documentazione relativa alla distribuzione per il ruolo del server che si sta ripristinando.

</div>

</div>

<span> </span>

</div>

</div>

</div>

