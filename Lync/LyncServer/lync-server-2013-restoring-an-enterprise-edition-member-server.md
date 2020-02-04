---
title: 'Lync Server 2013: ripristino di un server membro di Enterprise Edition'
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
ms.openlocfilehash: e870b68d1252ea5a203b3c334299fb65b6a56512
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>Ripristino di un server membro di Enterprise Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-18_

Se un server che esegue uno dei ruoli del server seguenti non riesce, seguire la procedura descritta in questo argomento per ripristinare il server. Se più server non riescono in modo indipendente, seguire la procedura per ogni server.

  - Server front-end

  - Mediation Server

  - Director

  - Server Chat persistente

  - Edge Server

<div>


> [!TIP]  
> Prima di iniziare il ripristino, è consigliabile prendere una copia dell'immagine del sistema. È possibile usare questa immagine come punto di rollback, in caso di problemi durante il ripristino. Potrebbe essere necessario prendere la copia dell'immagine dopo l'installazione del sistema operativo e di SQL Server e ripristinare o registrare di nuovo i certificati.



</div>

<div>

## <a name="to-restore-a-member-server"></a>Per ripristinare un server membro

1.  Iniziare con un nuovo server pulito o con lo stesso nome di dominio completo (FQDN) del server non riuscito, installare il sistema operativo e quindi ripristinare o registrare nuovamente i certificati.
    
    <div>
    

    > [!NOTE]  
    > Per eseguire questo passaggio, seguire le procedure di distribuzione del server dell'organizzazione.

    
    </div>

2.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins, accedere al server che si sta ripristinando.

3.  Passare alla cartella di installazione o al supporto di Lync Server e avviare la distribuzione guidata di Lync Server \\in\\Setup\\amd64 Setup. exe.

4.  Seguire la distribuzione guidata per eseguire le operazioni seguenti:
    
    1.  Eseguire il **passaggio 1: installare l'archivio configurazione locale** per installare i file di configurazione locali.
    
    2.  Eseguire il **passaggio 2: configurare o rimuovere i componenti di Lync Server** per installare il ruolo del server Lync Server.
    
    3.  Eseguire il **passaggio 3: richiedere, installare o assegnare certificati** per assegnare i certificati.
    
    4.  Eseguire il **passaggio 4: avviare i servizi** per avviare i servizi nel server.
    
    Per informazioni dettagliate sull'eseguire la distribuzione guidata, vedere la documentazione relativa alla distribuzione per il ruolo del server che si sta ripristinando.

</div>

</div>

<span> </span>

</div>

</div>

</div>

