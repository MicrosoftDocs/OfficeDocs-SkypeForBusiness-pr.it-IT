---
title: 'Lync Server 2013: installazione del portale Web amministrativo di Lync room System'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c69231c6f07d2e57c0fe8be31d18ed6da109fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Installazione del portale Web amministrativo di Lync room System in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-04-09_

È possibile scaricare il portale Web amministrativo di Microsoft Lync room System dall'area download Microsoft [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).

Per installare il portale Web amministrativo di Lync room System, eseguire la procedura seguente.

1.  Configurare la porta dell'applicazione attendibile eseguendo il cmdlet seguente in Lync Server Management Shell:
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  Per installare il portale della sala riunioni, scaricare **LyncRoomAdminPortal. exe** e quindi eseguirlo come amministratore.

3.  Aprire il file Web. config dalla posizione seguente:
    
    % Programmi% file\\di Microsoft Lync Server\\2013 Web\\Components meeting\\room\\Portal int handler\\

4.  Nel file Web. config modificare il PortalUserName con il nome utente creato nel passaggio 2 nella sezione "configurazione dei prerequisiti per il portale di amministrazione di Lync room System" (il nome consigliato nel passaggio è LRSApp):
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  Poiché il portale di amministrazione di LRS è un'applicazione attendibile, non è necessario specificare la password nella configurazione del portale. Se l'utente usa un registrar diverso da quello locale, è necessario specificarne il registrar aggiungendo la riga seguente nel file Web. config:
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  Se la porta utilizzata è diversa da 5061, aggiungere la riga seguente nel file Web. config:
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a>Verifica dell'installazione del portale Web amministrativo di Lync room System

Per verificare l'installazione del portale Web amministrativo di Lync room System, eseguire le operazioni seguenti:


1.  In un server front-end passare all'URL seguente:
    
    https://\<Fe-server\>/LRS
    
    Non è necessario visualizzare gli errori, come illustrato nell'immagine seguente:
    
    Schermata ![di accesso al portale di amministrazione di Lync room System](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "")

2.  Se non vengono visualizzati errori, provare ad accedere all'URL seguente da qualsiasi altro computer della topologia:
    
    https://\<Fe-server\>/LRS
    
    Per accedere alla pagina, è necessario aggiungere i record DNS come descritto in "record DNS necessari per l'accesso automatico al [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)client".

</div>

</div>

<span> </span>

</div>

</div>

</div>

