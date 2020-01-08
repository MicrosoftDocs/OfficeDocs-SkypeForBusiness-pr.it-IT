---
title: 'Lync Server 2013: creare nuove impostazioni di configurazione del servizio Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86105e4dbf6b624f87844a68ebe5fca6bba02247
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a>Creare nuove impostazioni di configurazione del servizio Web in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

È possibile usare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati a Lync Server 2013.

Seguire questa procedura per creare un nuovo criterio di servizio Web.

<div>

## <a name="to-create-new-web-service-configuration-settings"></a>Per creare nuove impostazioni di configurazione del servizio Web

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **servizio Web**.

4.  Nella pagina **servizio Web** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:
    
      - Per configurare il servizio Web per un sito, fare clic su **configurazione sito**. In **Seleziona un sito**fare clic sul sito a cui verranno applicati i criteri di servizio Web e fare clic su **OK**.
    
      - Per configurare il servizio Web per un pool, fare clic su **Configurazione pool**. In **Seleziona un servizio**fare clic sul servizio a cui verranno applicati i criteri di servizio Web e fare clic su **OK**.

5.  Nell' **impostazione di un nuovo servizio Web**, nell' **autenticazione integrata di Windows**, selezionare **negozia**, **autenticazione di Windows integrata**o **nessuno**.

6.  Selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:
    
      - **Abilitare l'autenticazione PIN** per consentire ai client di essere autenticati usando i numeri di pin.
    
      - **Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.
    
      - **Abilitare il download della catena di certificati per consentire** ai server presentati con un certificato di autenticazione di scaricare la catena di certificati per tale certificato.

7.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

