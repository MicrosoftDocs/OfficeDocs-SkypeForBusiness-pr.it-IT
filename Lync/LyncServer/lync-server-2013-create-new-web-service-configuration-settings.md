---
title: 'Lync Server 2013: creare nuove impostazioni di configurazione del servizio Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79508e99c8bc70e7781e77cd7727be30ebdda58f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a>Creare nuove impostazioni di configurazione del servizio Web in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

È possibile utilizzare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati di Lync Server 2013.

Eseguire la procedura seguente per creare un nuovo criterio di servizio Web.

<div>

## <a name="to-create-new-web-service-configuration-settings"></a>Per creare nuove impostazioni di configurazione del servizio Web

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Servizio Web**.

4.  Nella pagina **servizio Web** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:
    
      - Per configurare il servizio Web per un sito, fare clic su **configurazione sito**. In **Seleziona un sito**fare clic sul sito a cui verranno applicati i criteri del servizio Web e quindi fare clic su **OK**.
    
      - Per configurare il servizio Web per un pool, fare clic su **Configurazione pool**. In **Seleziona un servizio**fare clic sul servizio a cui verranno applicati i criteri del servizio Web e quindi fare clic su **OK**.

5.  In **nuova impostazione del servizio Web**, in **autenticazione integrata di Windows**, selezionare **negozia**, **autenticazione integrata di Windows**o **nessuno**.

6.  Selezionare una o più delle opzioni seguenti in base alle capacità dei client e al supporto nell'ambiente:
    
      - **Abilita autenticazione PIN** per consentire l'autenticazione dei client tramite numeri PIN.
    
      - **Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.
    
      - **Abilita download catena di certificati** per fare in modo che i server a cui viene presentato un certificato di autenticazione eseguano il download della catena di certificati per tale certificato.

7.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

