---
title: "Lync Server 2013: Preparazione dell'infrastruttura e dei sistemi"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc49f5e246e69f600506d990ace7362d9666f1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Preparazione dell'infrastruttura e dei sistemi per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

La distribuzione di Lync Server 2013 richiede l'uso di generatore di topologia per definire e pubblicare la struttura della topologia. Per identificare i componenti necessari per la topologia, è possibile usare generatore di topologia per creare e salvare una struttura di topologia. Prima di pubblicare la topologia in Generatore di topologie, eseguire le operazioni seguenti:

  - Acquisire e installare l'hardware per ogni componente nella progettazione della topologia creata e salvata con generatore di topologia, inclusi tutti i computer necessari (server che eseguono Lync Server 2013, server di database, server che eseguono Internet Information Services ( IIS) e invertire i server proxy, come appropriato), le schede di rete, i dispositivi di bilanciamento del carico hardware e gli strumenti di archiviazione, ad esempio i file server. Per informazioni dettagliate su come definire una topologia che specifichi i componenti necessari per la distribuzione, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Per informazioni dettagliate sui requisiti hardware per i server, vedere [hardware supportato per Lync server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa alla supportabilità.

  - Verificare che l'infrastruttura di rete soddisfi i requisiti. Per informazioni dettagliate, vedere [requisiti per l'infrastruttura di rete per Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.

  - Configurare servizi di dominio Active Directory. Per pubblicare e abilitare la topologia, è necessario che i server interni siano rappresentati da account di computer in servizi di dominio Active Directory. Questa operazione viene eseguita unendo i computer a servizi di dominio Active Directory. Per informazioni dettagliate sulla preparazione di servizi di [dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Creare una condivisione file. I server Standard Edition possono ospitare la condivisione file per il file richiesto, mentre in una distribuzione aziendale la condivisione file non può essere ospitata nel server front-end. Le autorizzazioni e le appartenenze ai gruppi necessarie per la distribuzione e l'impostazione dell'elenco di controllo di accesso (ACL) nella cartella e della condivisione devono essere impostate correttamente per il completamento corretto di generatore di topologie. Devi verificare che la persona che ha eseguito Generatore di topologia disponga delle autorizzazioni e delle appartenenze ai gruppi seguenti:
    
      - Membro degli amministratori locali
    
      - Membro degli utenti del dominio
    
      - Controllo completo sulla condivisione e la cartella di file Store

  - Per Enterprise Edition, installare e configurare SQL Server. Per il completamento dell'installazione di SQL Server, il server basato su SQL Server deve essere online e la persona che pubblica la topologia è un amministratore locale di SQL Server e deve essere un membro del gruppo sysadmin di SQL Server nell'istanza di SQL Server.

Dopo aver completato tutte le attività di preparazione descritte in questo argomento, ma prima di pubblicare la topologia è necessario eseguire anche le altre attività di preparazione, tra cui l'installazione dei sistemi operativi Windows e altro software prerequisito, la configurazione IIS e configurazione di DNS. Per informazioni dettagliate su queste attività, vedere [requisiti di sistema per i server che utilizzano Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [configurare IIS per Lync Server 2013](lync-server-2013-configure-iis.md)e [preparare l'infrastruttura e i sistemi per Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). È inoltre necessario acquisire familiarità con i client e i requisiti client. Per informazioni dettagliate, vedere [distribuzione di client e dispositivi in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurazione hardware per Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Installazione del software per Lync Server 2013](lync-server-2013-software-setup.md)

  - [Preparazione di Servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Configurare SQL Server per Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurare record DNS in Lync Server 2013 per un pool Front End o un server Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Installare gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

