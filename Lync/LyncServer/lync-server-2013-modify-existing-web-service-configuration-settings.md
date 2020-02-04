---
title: 'Lync Server 2013: modificare le impostazioni di configurazione del servizio Web esistente'
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
ms.openlocfilehash: 11bd7f4629d4a3cf0f356a47760810e380af7deb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a>Modificare le impostazioni di configurazione del servizio Web esistenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

È possibile usare la pagina del **servizio Web** per configurare i metodi di autenticazione per l'accesso ai server Web e ai servizi Web correlati a Lync Server 2013.

Seguire questa procedura per modificare un criterio di servizio Web esistente.

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a>Per modificare le impostazioni di configurazione del servizio Web esistente

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **servizio Web**.

4.  Nella pagina **servizio Web** fare clic su una configurazione, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  In **Modifica impostazione servizio Web**, in **autenticazione di Windows integrata**, selezionare **negozia**, **autenticazione di Windows integrata**o **nessuno**.

6.  Selezionare una o più delle opzioni seguenti in base alle funzionalità dei client e al supporto nell'ambiente:
    
      - **Abilitare l'autenticazione PIN** per consentire ai client di essere autenticati usando i numeri di pin.
    
      - **Abilitare l'autenticazione del certificato** affinché i server del pool rilasciano certificati ai client.
    
      - **Abilitare il download della catena di certificati per consentire** ai server presentati con un certificato di autenticazione di scaricare la catena di certificati per tale certificato.

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

