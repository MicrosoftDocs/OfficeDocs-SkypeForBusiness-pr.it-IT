---
title: "Lync Server 2013: preparazione dell'infrastruttura e dei sistemi"
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
ms.openlocfilehash: 95156c862c2c6fbee1b3a4625d8b9db234012a91
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139107"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Preparazione dell'infrastruttura e dei sistemi per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

La distribuzione di Lync Server 2013 richiede l'utilizzo di generatore di topologie per definire e pubblicare la progettazione della topologia. Per identificare i componenti necessari per la topologia, è possibile utilizzare Generatore di topologie per creare e salvare una progettazione della topologia. Prima di pubblicare la topologia nel Generatore di topologie, eseguire le operazioni seguenti:

  - Acquisire e installare l'hardware per ogni componente nella progettazione della topologia creata e salvata tramite Generatore di topologie, inclusi tutti i computer necessari (server che eseguono Lync Server 2013, server di database, server che eseguono Internet Information Services ( IIS) e server proxy inversi, in base alle esigenze), schede di rete, dispositivi di bilanciamento del carico hardware e periferiche di archiviazione, ad esempio file server. Per informazioni dettagliate su come definire una topologia che specifichi i componenti necessari per la distribuzione, vedere [define and Configuring the topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md). Per informazioni dettagliate sui requisiti hardware per i server, vedere [hardware supportato per Lync Server 2013](lync-server-2013-supported-hardware.md) nella documentazione relativa alla supportabilità.

  - Verificare che l'infrastruttura di rete soddisfi i requisiti. Per informazioni dettagliate, vedere [Network Infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.

  - Configurare servizi di dominio Active Directory. Per pubblicare e abilitare la topologia, è necessario che i server interni siano rappresentati da account computer in Servizi di dominio Active Directory. A tale scopo, i computer vengono aggiunti a Servizi di dominio Active Directory. Per informazioni dettagliate sulla preparazione di servizi di [dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).

  - Creare una condivisione file. I server Standard Edition possono ospitare la condivisione file per il file richiesto, mentre in una distribuzione Enterprise la condivisione file non può essere ospitata sul server Front End. Le autorizzazioni e le appartenenze ai gruppi necessarie per la distribuzione e l'impostazione dell'elenco di controllo di accesso nella cartella e nella condivisione devono essere impostate in modo adeguato per l'esecuzione corretta del Generatore di topologie. È necessario assicurarsi che la persona che esegue Generatore di topologie disponga delle autorizzazioni e delle appartenenze ai gruppi seguenti:
    
      - Membro del gruppo Administrators locale
    
      - Membro del gruppo Domain Users
    
      - Controllo completo sulla condivisione e sulla cartella dell'archivio file

  - Per Enterprise Edition, installare e configurare SQL Server. Per la corretta installazione di SQL Server è necessario che il server basato su SQL Server sia online e che la persona che pubblica la topologia sia un amministratore locale sul server SQL e membro del gruppo sysadmin di SQL Server sull'istanza di SQL Server.

Dopo aver completato tutte le attività di preparazione descritte in questo argomento, ma prima di pubblicare la topologia, è necessario eseguire anche le altre attività di preparazione, tra cui l'installazione dei sistemi operativi Windows e degli altri prerequisiti software, l'installazione di IIS e la configurazione di DNS. Per informazioni dettagliate su queste attività, vedere [requisiti di sistema per i server che eseguono Lync server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md)e [preparazione dell'infrastruttura e dei sistemi per Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md). È inoltre opportuno acquisire familiarità con i client e i relativi requisiti. Per informazioni dettagliate, vedere [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Installazione hardware per Lync Server 2013](lync-server-2013-hardware-setup.md)

  - [Configurazione del software per Lync Server 2013](lync-server-2013-software-setup.md)

  - [Preparazione di Servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Configurare SQL Server per Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Configurare i record DNS in Lync Server 2013 per un pool Front end o un server Standard Edition](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Installare gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

