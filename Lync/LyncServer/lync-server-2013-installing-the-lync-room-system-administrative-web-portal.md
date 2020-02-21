---
title: 'Lync Server 2013: installazione del portale Web amministrativo di Lync room System'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b475911da0e0508fecb53de533f75e9feb10155
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Installazione del portale Web amministrativo di Lync room System in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-04-09_

È possibile scaricare il portale Web amministrativo Microsoft Lync room System dall'area download Microsoft all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044).

Per installare il portale Web amministrativo di Lync room System, attenersi alla seguente procedura.

1.  Configurare la porta dell'applicazione attendibile eseguendo il cmdlet seguente in Lync Server Management Shell:
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  Per installare il portale della sala riunioni, scaricare **LyncRoomAdminPortal. exe** e quindi eseguirlo come amministratore.

3.  Aprire il file Web. config dal percorso seguente:
    
    % Program Files%\\Microsoft Lync Server 2013\\Web Components\\sala riunioni\\Portal\\int handler\\

4.  Nel file Web. config modificare PortalUserName con il nome utente creato nel passaggio 2 nella sezione "configurazione dei prerequisiti per il portale di amministrazione di Lync room System" (il nome consigliato nel passaggio è LRSApp):
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  Poiché il portale di amministrazione di LRS è un'applicazione attendibile, non è necessario fornire la password nella configurazione del portale. Se l'utente utilizza un registrar diverso da quello locale, è necessario specificare il registrar per il servizio di registrazione aggiungendo la riga seguente nel file Web. config:
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  Se la porta utilizzata è diversa da 5061, aggiungere la riga seguente nel file Web. config:
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>Verifica dell'installazione del portale Web amministrativo di Lync room System

Per verificare l'installazione del portale Web amministrativo di Lync room System, eseguire le operazioni seguenti:


1.  In un front end Server passare all'URL seguente:
    
    https://\<Fe-server\>/LRS
    
    Non è possibile visualizzare errori, come illustrato nell'immagine seguente:
    
    ![Schermata di accesso al portale di amministrazione di Lync room System](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Schermata di accesso al portale di amministrazione di Lync room System")

2.  Se non vengono visualizzati errori, provare a accedere all'URL seguente da qualsiasi altro computer della topologia:
    
    https://\<Fe-server\>/LRS
    
    Per accedere alla pagina, è necessario aggiungere i record DNS come descritto nella sezione "record DNS necessari per l'accesso automatico dei client" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056).

</div>

</div>

<span> </span>

</div>

</div>

</div>

