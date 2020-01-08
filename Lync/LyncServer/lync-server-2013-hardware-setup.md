---
title: 'Lync Server 2013: Configurazione hardware'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e2d05db28ffa61ea25dbb237c388c37a87ac5a0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a>Configurazione hardware per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

La configurazione dell'hardware e di altri componenti necessari nell'infrastruttura necessaria per implementare la topologia richiede che, prima di pubblicare la topologia in Generatore di topologie, sia necessario eseguire le operazioni seguenti:

  - Installare l'hardware per ogni componente nella progettazione della topologia creata e salvata con generatore di topologia, inclusi tutti i computer necessari (server che eseguono Lync Server 2013, server di database, server che eseguono Internet Information Services (IIS) e invertire i server proxy, a seconda delle esigenze), schede di rete, dispositivi di bilanciamento del carico hardware e periferiche di archiviazione, ad esempio file server. Verificare di aver seguito le indicazioni relative al numero e alla velocità per le schede di rete. Se si utilizzeranno i dispositivi di bilanciamento del carico hardware, verificare di avere le informazioni appropriate del fornitore per configurarle per l'uso con Lync Server 2013. Se si vuole usare un file server o un altro server per ospitare la condivisione di file richiesta da Lync Server, verificare che il server sia disponibile e pronto per la configurazione della condivisione file. Per informazioni dettagliate su come definire una topologia che specifichi i componenti necessari per la distribuzione, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Per informazioni dettagliate sui requisiti hardware per i server, vedere [hardware supportato per Lync server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa alla supportabilità.

  - Verificare che l'infrastruttura di rete soddisfi i requisiti. Per informazioni dettagliate, vedere [requisiti per l'infrastruttura di rete per Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.

  - Configurare servizi di dominio Active Directory. La configurazione di servizi di dominio Active Directory include la preparazione di servizi di dominio Active Directory e la definizione di tutti i componenti da distribuire in Active Directory. Per informazioni dettagliate sulla preparazione di servizi di [dominio Active Directory, vedere Preparazione della documentazione per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) nella pagina relativa alla distribuzione.

  - Configurare le autorizzazioni necessarie per la creazione della condivisione file. Le autorizzazioni per l'uso delle condivisioni file di Lync Server 2013 vengono configurate automaticamente da generatore di topologie quando si pubblica la topologia. Tuttavia, l'account utente usato per pubblicare la topologia deve avere il controllo completo (lettura/scrittura/modifica) nella condivisione file in modo che generatore di topologie configuri le autorizzazioni necessarie. Per assicurarsi che la condivisione di file possa essere gestita correttamente durante il processo di pubblicazione del generatore di topologia, l'utente o il gruppo di domini di cui l'utente è membro deve essere membro del gruppo Administrators locale nel computer in cui si trova la condivisione file. In uno scenario con più domini, il dominio di un utente o di un gruppo deve essere un membro del gruppo Administrators locale nel computer nel dominio B in cui si troverà la condivisione file.
    
    Per informazioni dettagliate sull'aggiornamento con le condivisioni file in un file System distribuito (DFS), vedere [configurare l'archiviazione dei file per Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).
    
    <div>
    

    > [!WARNING]  
    > La condivisione file per Lync Server 2013, Enterprise Edition non può essere posizionata nel server front-end.

    
    </div>

  - Installare e configurare il servizio di bilanciamento del carico hardware per i servizi Web. Con il bilanciamento del carico DNS (Domain Name System) distribuito, è comunque necessario usare anche i dispositivi di bilanciamento del carico hardware per questi pool, ma solo per il traffico HTTP/HTTPS. Il bilanciamento del carico hardware viene usato per il traffico HTTPS dai client sulle porte 443 e 80. Anche se hai ancora bisogno di bilanciamento del carico hardware per questi pool, la configurazione e l'amministrazione saranno principalmente per il traffico HTTP/HTTPS, a cui sono abituati gli amministratori dei dispositivi di bilanciamento del carico hardware.

Dopo aver completato tutte le attività di preparazione descritte in questo argomento, ma prima di pubblicare la topologia è anche necessario:

  - [Installare i sistemi operativi e il software prerequisito nei server per Lync Server 2013](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Configurare IIS per Lync Server 2013](lync-server-2013-configure-iis.md)

  - [Configurare SQL Server per Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurare record DNS in Lync Server 2013 per un pool Front End o un server Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

