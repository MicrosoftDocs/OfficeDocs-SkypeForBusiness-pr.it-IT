---
title: 'Lync Server 2013: installazione hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57b06362ad70bedd8edd0baafc3d512cbbf95714
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528343"
---
# <a name="hardware-setup-for-lync-server-2013"></a>Installazione hardware per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Se si configura l'hardware e gli altri componenti necessari nell'infrastruttura necessaria per implementare la topologia, prima di pubblicare la topologia in Generatore di topologie è necessario eseguire le operazioni seguenti:

  - Installare l'hardware per ogni componente nella progettazione della topologia creata e salvata utilizzando Generatore di topologie, inclusi tutti i computer necessari (server che eseguono Lync Server 2013, server di database, server che eseguono Internet Information Services (IIS) e server proxy inversi, a seconda dei casi), schede di rete, dispositivi di bilanciamento del carico hardware e periferiche di archiviazione, ad esempio file server. Assicurarsi di aver rispettato i consigli relativi al numero e alla velocità delle schede di rete. Se si utilizzano i dispositivi di bilanciamento del carico hardware, verificare di disporre delle informazioni appropriate del fornitore per configurarle per l'utilizzo con Lync Server 2013. Se si utilizzerà un file server o un altro server per ospitare la condivisione file richiesta da Lync Server, assicurarsi che il server sia disponibile e pronto per la configurazione della condivisione file. Per informazioni dettagliate su come definire una topologia che specifichi i componenti necessari per la distribuzione, vedere [define and Configuring the topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Per informazioni dettagliate sui requisiti hardware per i server, vedere [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa alla supportabilità.

  - Verificare che l'infrastruttura di rete soddisfi i requisiti. Per informazioni dettagliate, vedere [Network Infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.

  - Configurare servizi di dominio Active Directory. Tra le attività di configurazione sono incluse la preparazione di Servizi di dominio Active Directory e la definizione di tutti i componenti che si desidera distribuire in questo servizio. Per informazioni dettagliate sulla preparazione di servizi di [dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.

  - Impostare le autorizzazioni necessarie per creare la condivisione file. Le autorizzazioni per l'utilizzo di condivisioni di file da Lync Server 2013 vengono configurate automaticamente dal generatore di topologie quando si pubblica la topologia. Tuttavia, l'account utente utilizzato per pubblicare la topologia deve disporre del controllo completo (lettura/scrittura/modifica) sulla condivisione file affinché il generatore di topologie configuri le autorizzazioni necessarie. Per assicurarsi che la condivisione file possa essere gestita correttamente durante il processo di pubblicazione del generatore di topologie, è necessario che l'utente o il gruppo di dominio a cui appartiene l'utente sia membro del gruppo Administrators locale nel computer in cui si trova la condivisione file. In uno scenario multidominio l'utente o il gruppo del Dominio A deve essere membro del gruppo Administrators locale nel computer nel Dominio B in cui verrà posizionata la condivisione file.
    
    Per informazioni dettagliate sull'aggiornamento tramite condivisioni file in un file System distribuito (DFS), vedere [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).
    
    <div>
    

    > [!WARNING]  
    > La condivisione file per Lync Server 2013, Enterprise Edition non può essere posizionata nel server front-end.

    
    </div>

  - Installare e configurare il servizio di bilanciamento del carico hardware per i servizi Web. Dopo aver distribuito il servizio di bilanciamento del carico DNS (Domain Name System), è ancora necessario utilizzare anche i servizi di bilanciamento del carico hardware per questi pool, ma solo per il traffico HTTP/HTTPS. Il servizio di bilanciamento del carico hardware viene utilizzato per il traffico HTTPS dai client sulle porte 443 e 80. Sebbene sia comunque necessario disporre di dispositivi di bilanciamento del carico hardware per questi pool, le impostazioni e l'amministrazione di tale bilanciamento saranno destinate principalmente al traffico HTTP/HTTPS, a cui gli amministratori del bilanciamento del carico hardware sono abituati.

Dopo aver eseguito tutte le attività di preparazione descritte in questo argomento, ma prima di pubblicare la topologia, è inoltre necessario eseguire le operazioni seguenti:

  - [Installare i sistemi operativi e il software prerequisito sui server per Lync Server 2013](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Configurare IIS per Lync Server 2013](lync-server-2013-configure-iis.md)

  - [Configurare SQL Server per Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurare i record DNS in Lync Server 2013 per un pool Front end o un server Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

