---
title: 'Lync Server 2013: strumenti di amministrazione di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27a7567fa467f8e152f4b6a61b06600a127607d7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a>Strumenti di amministrazione di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

In questo argomento vengono descritti gli strumenti di amministrazione di Lync Server 2013.

Gli strumenti di amministrazione vengono installati per impostazione predefinita in ogni server Lync Server. Inoltre, è possibile installare gli strumenti di amministrazione in altri computer, ad esempio le console amministrative dedicate. Per le procedure per l'installazione degli strumenti di amministrazione, vedere [Install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md). Per le procedure per l'apertura degli strumenti per l'esecuzione di attività di gestione, vedere [Open Lync Server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

Assicurarsi di esaminare l'infrastruttura, il sistema operativo, il software e i requisiti di diritti di amministratore prima di installare o utilizzare gli strumenti di amministrazione di Lync Server. Per informazioni dettagliate sui requisiti dell'infrastruttura, vedere [Administrative Tools Infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md). Per informazioni dettagliate sui requisiti software e del sistema operativo per l'installazione degli strumenti di amministrazione di Lync Server, vedere [Server and Tools Operating System Support in Lync server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional Software Requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md). I diritti e le autorizzazioni degli utenti necessari per installare e utilizzare gli strumenti sono descritti in [autorizzazioni e diritti di amministratore necessari per l'installazione e l'amministrazione di Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).

Gli strumenti di amministrazione sono costituiti dai seguenti:

  - **La distribuzione guidata**   di Lync Server consente di distribuire Lync Server e di installare tutti gli strumenti di amministrazione.

  - **Il generatore**   di topologie di Lync Server utilizza per definire i componenti della distribuzione.

  - **Il pannello**   di controllo di Lync Server utilizza un'interfaccia basata sul Web per la gestione continua della distribuzione.

  - **Lync Server Management Shell**   utilizza la riga di comando per la gestione continua della distribuzione.

  - **Strumento di registrazione di Lync Server**   utilizzato per la risoluzione dei problemi della distribuzione.

  - **Servizio di registrazione centralizzato**   raccogliere i registri e i file di traccia da un computer, un pool, un sito o un globale. Selezionare e definire gli scenari che contengono provider, flag e livelli di traccia. La registrazione viene raccolta, aggregata e visualizzata con strumenti quali qualsiasi strumento basato su testo o Snooper. exe.

È possibile gestire la distribuzione principalmente utilizzando il generatore di topologie e il pannello di controllo di Lync Server.

<div>

## <a name="deployment-wizard"></a>Distribuzione guidata

È necessario utilizzare la distribuzione guidata di Lync Server inclusa nel supporto di installazione per installare tutti gli strumenti di amministrazione su un computer in cui non è stato ancora installato Lync Server. Durante il processo di installazione degli strumenti di amministrazione, la distribuzione guidata di Lync Server viene installata localmente insieme agli altri strumenti, in modo che sia possibile utilizzarla in un secondo momento per installare i file per i componenti aggiuntivi o rimuovere i file per i componenti che non si desidera utilizzare nel computer.

Per informazioni dettagliate sull'esecuzione della distribuzione guidata di Lync Server per la prima volta dal supporto di installazione di Lync Server, vedere [Install Lync server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).

</div>

<div>

## <a name="topology-builder"></a>Strumento di generazione topologia

Per informazioni dettagliate sulle attività di distribuzione che è possibile eseguire utilizzando Generatore di topologie, vedere la documentazione relativa alla distribuzione per ogni ruolo del server.

</div>

<div>

## <a name="lync-server-control-panel"></a>Pannello di controllo di Lync Server

È possibile utilizzare il pannello di controllo di Lync Server 2013 per eseguire la maggior parte delle attività amministrative necessarie per la gestione e la manutenzione di Lync Server 2013. Nel pannello di controllo di Lync Server è disponibile un'interfaccia utente grafica (GUI) per gestire la configurazione dei server che eseguono Lync Server, oltre a utenti, client e dispositivi nell'organizzazione. Lync Server Management Shell utilizza il pannello di controllo di Lync Server come meccanismo sottostante per eseguire la configurazione di Lync Server.

Il pannello di controllo di Lync Server viene installato automaticamente in ogni server Lync Server front end server o Standard Edition. In questa versione è possibile amministrare i server perimetrali in remoto. È inoltre possibile installare il pannello di controllo di Lync Server in un altro computer, ad esempio una console di gestione da cui si desidera gestire in modo centralizzato Lync Server. Per informazioni dettagliate, vedere [Install Lync Server 2013 Administrative Tools](lync-server-2013-install-lync-server-administrative-tools.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Per configurare le impostazioni utilizzando il pannello di controllo di Lync Server, è necessario essere connessi utilizzando un account assegnato al ruolo CsAdministrator. Per informazioni dettagliate sui ruoli amministrativi predefiniti disponibili in Lync Server 2013, vedere <A href="lync-server-2013-planning-for-role-based-access-control.md">pianificazione del controllo di accesso basato sui ruoli in Lync server 2013</A>.</P>
> <LI>
> <P>Per configurare le impostazioni utilizzando il pannello di controllo di Lync Server, è necessario utilizzare anche un computer con una risoluzione minima dello schermo pari a 1024 x 768.</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Lync Server Management Shell

In Lync Server, Lync Server Management Shell fornisce un nuovo metodo per l'amministrazione e la gestione. Lync Server Management Shell è un'interfaccia di gestione potente, basata sull'interfaccia della riga di comando di Windows PowerShell, che include un set completo di cmdlet specifici di Lync Server. Con Lync Server Management Shell, è possibile ottenere un set completo di controlli di configurazione e automazione. Il generatore di topologie e il pannello di controllo di Lync Server implementano sottoinsiemi di questi cmdlet per supportare la gestione di Lync Server. Lync Server Management Shell include cmdlet per tutte le attività di amministrazione di Lync Server ed è possibile utilizzare i cmdlet singolarmente per gestire la distribuzione. Per informazioni dettagliate, vedere la documentazione relativa a [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) o la guida della riga di comando per ogni cmdlet.

</div>

<div>

## <a name="logging-tool"></a>Strumento di registrazione

Lo strumento di registrazione di Lync Server facilita la risoluzione dei problemi acquisendo le informazioni di registrazione e traccia dal prodotto durante l'esecuzione del prodotto. È possibile utilizzare lo strumento per eseguire le sessioni di debug su qualsiasi ruolo del server Lync Server. Per informazioni dettagliate sullo strumento di registrazione, vedere la documentazione dello strumento di registrazione di Lync Server 2010 nella [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265)libreria TechNet all'indirizzo.

<div>


> [!IMPORTANT]  
> Il servizio di registrazione centralizzato è consigliato per tutte le raccolte di registrazione tramite lo strumento di registrazione di Lync Server in tutte le circostanze. Lo strumento di registrazione di Lync Server continuerà a funzionare, ma interferirà o verrà reso prevalentemente inefficace se il servizio di registrazione centralizzato è già in esecuzione. È consigliabile utilizzare solo il servizio di registrazione centralizzato o lo strumento di registrazione di Lync Server, ma non contemporaneamente. Per ulteriori informazioni sul servizio di registrazione centralizzato e sul motivo per cui utilizzarlo in modo esclusivo, vedere <A href="lync-server-2013-using-the-centralized-logging-service.md">utilizzo del servizio di registrazione centralizzato in Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Requisiti dell'infrastruttura degli strumenti di amministrazione in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Supporto del sistema operativo per server e strumenti in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Requisiti software per gli strumenti di amministrazione in Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)

  - [Autorizzazioni e diritti di amministratore necessari per l'installazione e l'amministrazione di Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [Requisiti per la pubblicazione di una topologia in Lync Server 2013](lync-server-2013-requirements-to-publish-a-topology.md)

  - [Installare gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)

  - [Aprire gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Risoluzione dei problemi relativi al Pannello di controllo di Lync Server 2013](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [Utilizzo del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-using-the-centralized-logging-service.md)

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

