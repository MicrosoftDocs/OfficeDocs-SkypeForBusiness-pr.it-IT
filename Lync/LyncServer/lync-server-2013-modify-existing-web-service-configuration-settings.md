---
title: 'Lync Server 2013: modificare le impostazioni di configurazione del servizio Web esistenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a6d29868c6f4b18bd4bb02dac651a671684ecc0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a>Modificare le impostazioni di configurazione del servizio Web esistenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

È possibile utilizzare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati di Lync Server 2013.

Eseguire la procedura seguente per modificare i criteri per un servizio Web esistente.

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a>Per modificare le impostazioni di configurazione del servizio Web esistenti

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Servizio Web**.

4.  Nella pagina **Servizio Web** fare clic su una configurazione, fare clic su **Modifica** e quindi su **Mostra dettagli**.

5.  In **Modifica impostazione servizio Web**, in **Autenticazione integrata di Windows**, selezionare **Negoziazione**, **Autenticazione integrata di Windows** o **Nessuno**.

6.  Selezionare una o più delle opzioni seguenti in base alle capacità dei client e al supporto nell'ambiente:
    
      - **Abilita autenticazione PIN** per consentire l'autenticazione dei client tramite numeri PIN.
    
      - **Abilita autenticazione certificato** per fare in modo che i server nel pool emettano i certificati per i client.
    
      - **Abilita download catena di certificati** per fare in modo che i server a cui viene presentato un certificato di autenticazione eseguano il download della catena di certificati per tale certificato.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione dell'autenticazione nel pannello di controllo di Lync Server 2013](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

