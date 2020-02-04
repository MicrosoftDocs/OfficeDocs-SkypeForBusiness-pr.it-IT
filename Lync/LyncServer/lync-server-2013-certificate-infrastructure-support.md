---
title: "Lync Server 2013: Supporto per l'infrastruttura di certificazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc8cb5bdad02de4fcb407d7eb27960258a46dd3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Supporto per l'infrastruttura di certificazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

Lync Server 2013 richiede un'infrastruttura a chiave pubblica (PKI) per supportare connessioni TLS (Transport Layer Security) e MTLS (Mutual TLS). Per impostazione predefinita, Lync Server 2013 è configurato per l'uso di TLS per le connessioni da client a server. MTLS viene usato per le connessioni tra server.

I certificati MTLS devono essere emessi da autorità di certificazione (CAs) attendibili per Lync Server 2013. Lync Server supporta i certificati emessi dalle seguenti autorità di certificazione:

  - Certificati emessi da una CA interna:
    
      - CA del sistema operativo Windows Server 2003
    
      - CA del sistema operativo Windows Server 2008
    
      - CA del sistema operativo Windows Server 2008 R2
    
      - CA del sistema operativo Windows Server 2012
    
      - CA del sistema operativo Windows Server 2012 R2

  - Certificati emessi da una CA pubblica

La comunicazione con altre applicazioni e server, ad esempio Exchange 2013, richiede un certificato supportato dalle altre applicazioni e prodotti. Per la versione di 2013, Lync Server 2013 e altri prodotti di Microsoft Server, inclusi Exchange 2013 e SharePoint Server, supportano il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server. Per informazioni dettagliate, vedere [gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) nella documentazione relativa alla distribuzione o nella documentazione operativa.

Per le connessioni da client che usano il sistema operativo Windows 7, il sistema operativo Windows Server 2008 R2 e Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 include il supporto per (ma non richiede) certificati firmati con l'SHA-256 funzione hash crittografico. Per supportare l'accesso esterno tramite SHA-256, il certificato esterno viene emesso da una CA pubblica tramite SHA-256.

Per informazioni dettagliate sui requisiti dei certificati, vedere [requisiti per l'infrastruttura dei certificati per Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso dei caratteri jolly con i certificati, vedere [supporto di certificati jolly in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) nella documentazione relativa alla supportabilità.

</div>

<span> </span>

</div>

</div>

</div>

