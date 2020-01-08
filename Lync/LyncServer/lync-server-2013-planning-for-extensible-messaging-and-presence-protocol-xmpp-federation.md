---
title: Pianificazione della Federazione XMPP (Extensible Messaging and Presence Protocol)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2f4e1d8f9b7f164dd9e83f556dcc57809619278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Pianificazione della Federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Le versioni precedenti di Lync Server e Office Communications Server fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che poteva essere distribuito come ruolo server distinto per consentire la Federazione con le distribuzioni XMPP. In Microsoft Lync Server 2013 la funzionalità XMPP può essere distribuita come caratteristica. La funzionalità XMPP viene installata in due parti: un proxy XMPP che viene eseguito nel server perimetrale e il gateway XMPP che viene eseguito nei server front-end.

La distribuzione e la configurazione di XMPP sono descritte in [distribuzione dell'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) si prevede di supportare XMPP nella propria organizzazione definendo le regole di porta e protocollo nel firewall, la configurazione dei certificati e l'aggiunta di record DNS. Gli argomenti seguenti in questa sezione riepilogano le informazioni che sarà necessario pianificare correttamente la Federazione XMPP per la distribuzione.

<div>


> [!IMPORTANT]
> La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la Federazione della messaggistica istantanea con Google Talk. Per qualsiasi altro sistema XMPP, contattare il fornitore di terze parti per verificare che supportino la Federazione con Lync Server 2013 e per eventuali suggerimenti per la distribuzione o la risoluzione dei problemi.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Riepilogo del certificato-federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Riepilogo della porta-Federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Riepilogo DNS-Federazione XMPP (Extensible Messaging and Presence Protocol) in Lync Server 2013](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione della federazione di XMPP in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Configurare criteri per controllare l'accesso utente federato XMPP in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[Gestire i partner federati XMPP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))  
[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))  
[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

