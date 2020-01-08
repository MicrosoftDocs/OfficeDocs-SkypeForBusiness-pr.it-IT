---
title: 'Lync Server 2013: Strumenti di amministrazione di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6756aee8d7c65b179fb5c1c15ca008b3bd205778
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979881"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a>Strumenti di amministrazione di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

In questo argomento vengono descritti gli strumenti di amministrazione per Lync Server 2013.

Gli strumenti di amministrazione vengono installati per impostazione predefinita in ogni server Lync Server. È inoltre possibile installare gli strumenti di amministrazione in altri computer, ad esempio le console amministrative dedicate. Per le procedure per l'installazione degli strumenti di amministrazione, vedere [installare gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md). Per le procedure per l'apertura degli strumenti per l'esecuzione di attività di gestione, vedere [aprire gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

Verificare che i requisiti per l'infrastruttura, il sistema operativo, il software e i diritti di amministratore vengano riesaminati prima di installare o utilizzare gli strumenti di amministrazione di Lync Server. Per informazioni dettagliate sui requisiti dell'infrastruttura, vedere [requisiti dell'infrastruttura per gli strumenti amministrativi in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Per informazioni dettagliate sui requisiti del sistema operativo e del software per installare gli strumenti di amministrazione di Lync Server, vedere [supporto dei sistemi operativi per server e strumenti in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [requisiti software aggiuntivi per Lync Server 2013](lync-server-2013-additional-software-requirements.md)e [supporto e requisiti aggiuntivi del server in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). I diritti utente e le autorizzazioni necessarie per installare e usare gli strumenti sono descritti in [diritti di amministratore e autorizzazioni necessarie per l'installazione e l'amministrazione di Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

Gli strumenti di amministrazione sono i seguenti:

  - **La distribuzione guidata**   di Lync Server consente di distribuire Lync Server e di installare tutti gli strumenti di amministrazione.

  - **Il generatore**   di topologia di Lync Server usa per definire i componenti nella distribuzione.

  - **Il pannello**   di controllo di Lync Server usa una interfaccia basata sul Web per la gestione continua della distribuzione.

  - **Lync Server Management Shell**   usa la riga di comando per la gestione continua della distribuzione.

  - **Lo strumento**   di registrazione di Lync Server consente di risolvere i problemi della distribuzione.

  - **Il servizio**   di registrazione centralizzato raccoglie i registri e i file di traccia da un computer, un pool, un sito o un globale. Selezionare e definire scenari che contengono provider, flag e livelli di traccia. La registrazione viene raccolta, aggregata e visualizzata con strumenti come qualsiasi strumento basato su testo o Snooper. exe.

È possibile gestire la distribuzione usando principalmente il generatore di topologia e il pannello di controllo di Lync Server.

<div>

## <a name="deployment-wizard"></a>Distribuzione guidata

È necessario usare la distribuzione guidata di Lync Server inclusa nel supporto di installazione per installare tutti gli strumenti amministrativi in un computer in cui non è già stato installato Lync Server. Durante il processo di installazione degli strumenti di amministrazione, la distribuzione guidata di Lync Server viene installata localmente insieme agli altri strumenti in modo da poterla usare in seguito per installare i file per altri componenti o rimuovere i file per i componenti che non si desidera computer.

Per informazioni dettagliate su come eseguire la distribuzione guidata di Lync Server per la prima volta dal supporto di installazione di Lync Server, vedere [installare gli strumenti di amministrazione di Lync server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

</div>

<div>

## <a name="topology-builder"></a>Generatore di topologie

Per informazioni dettagliate sulle attività di distribuzione che è possibile eseguire tramite Generatore di topologie, vedere la documentazione relativa alla distribuzione per ogni ruolo del server.

</div>

<div>

## <a name="lync-server-control-panel"></a>Pannello di controllo di Lync Server

È possibile usare il pannello di controllo di Lync Server 2013 per eseguire la maggior parte delle attività amministrative necessarie per gestire e mantenere Lync Server 2013. Il pannello di controllo di Lync Server offre un'interfaccia utente grafica (GUI) per gestire la configurazione dei server in cui è in uso Lync Server, oltre a utenti, client e dispositivi dell'organizzazione. Lync Server Management Shell usa il pannello di controllo di Lync Server come meccanismo sottostante per eseguire la configurazione del server Lync.

Il pannello di controllo di Lync Server viene installato automaticamente in tutti i server front end server o Standard Edition di Lync. In questa versione gli Edge Server vengono amministrati in remoto. È anche possibile installare il pannello di controllo di Lync Server in un altro computer, ad esempio una console di gestione da cui si vuole gestire centralmente Lync Server. Per informazioni dettagliate, vedere [installare gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Per configurare le impostazioni tramite il pannello di controllo di Lync Server, è necessario avere effettuato l'accesso con un account assegnato al ruolo CsAdministrator. Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Lync Server 2013, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione per il controllo dell'accesso basato sui ruoli in Lync server 2013</A>.</P>
> <LI>
> <P>Per configurare le impostazioni tramite il pannello di controllo di Lync Server, è necessario usare anche un computer con una risoluzione minima dello schermo di 1024 x 768.</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Lync Server Management Shell

In Lync Server, Lync Server Management Shell offre un nuovo metodo per l'amministrazione e la gestione. Lync Server Management Shell è una potente interfaccia di gestione, basata sull'interfaccia della riga di comando di Windows PowerShell, che include un set completo di cmdlet specifici di Lync Server. Con Lync Server Management Shell si ottiene un set completo di controlli di configurazione e automazione. Il generatore di topologia e il pannello di controllo di Lync Server implementano entrambi i sottoinsiemi di questi cmdlet per supportare la gestione di Lync Server. Lync Server Management Shell include cmdlet per tutte le attività di amministrazione di Lync Server ed è possibile usare i cmdlet singolarmente per gestire la distribuzione. Per informazioni dettagliate, vedere la documentazione di [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) o la guida della riga di comando per ogni cmdlet.

</div>

<div>

## <a name="logging-tool"></a>Strumento di registrazione

Lo strumento di registrazione di Lync Server semplifica la risoluzione dei problemi acquisendo le informazioni di registrazione e traccia dal prodotto durante l'esecuzione del prodotto. È possibile usare lo strumento per eseguire sessioni di debug in qualsiasi ruolo di Lync Server Server. Per informazioni dettagliate sullo strumento di registrazione, vedere la documentazione dello strumento di registrazione di Lync Server 2010 nella [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)Raccolta TechNet all'indirizzo.

<div>


> [!IMPORTANT]  
> Il servizio di registrazione centralizzato è consigliato per tutte le raccolte di registrazione nello strumento di registrazione di Lync Server in tutte le circostanze. Lo strumento di registrazione di Lync Server continuerà a funzionare, ma interferirà o verrà reso prevalentemente inefficace se il servizio di registrazione centralizzato è già in corso. È consigliabile usare solo il servizio di registrazione centralizzato o lo strumento di registrazione di Lync Server, ma mai simultaneamente. Per altre informazioni sul servizio di registrazione centralizzato e sul motivo per cui è consigliabile usarlo in esclusiva, vedere <A href="lync-server-2013-using-the-centralized-logging-service.md">uso del servizio di registrazione centralizzato in Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Requisiti di infrastruttura per gli strumenti di amministrazione in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Supporto del sistema operativo per server e strumenti in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Requisiti software degli strumenti di amministrazione in Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

  - [Autorizzazioni e diritti di amministratore necessari per l'installazione e l'amministrazione di Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Requisiti per la pubblicazione di una topologia Lync Server 2013](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Installare gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Aprire gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Risoluzione dei problemi relativi al pannello di controllo di Lync Server 2013](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Uso del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

