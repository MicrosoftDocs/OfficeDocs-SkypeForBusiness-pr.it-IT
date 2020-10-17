---
title: Supporto dell'infrastruttura di certificazione per Lync Server 2013
description: Supporto dell'infrastruttura di certificazione per Lync Server 2013.
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
ms.openlocfilehash: cc08719e5b1c58a4dc3c1cab07db5e9842d46d5c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544232"
---
# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Supporto dell'infrastruttura di certificazione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-07_

Lync Server 2013 richiede un'infrastruttura a chiave pubblica (PKI) per supportare le connessioni TLS (Transport Layer Security) e Mutual TLS (MTLS). Per impostazione predefinita, Lync Server 2013 è configurato per l'utilizzo di TLS per le connessioni tra client e server. MTLS viene utilizzato per le connessioni tra server.

I certificati di MTLS devono essere emessi dalle autorità di certificazione (CAs) attendibili per Lync Server 2013. Lync Server supporta i certificati emessi dalle seguenti autorità di certificazione:

  - Certificati emessi da un'autorità di certificazione interna:
    
      - CA del sistema operativo Windows Server 2003
    
      - CA del sistema operativo Windows Server 2008
    
      - CA del sistema operativo Windows Server 2008 R2
    
      - CA del sistema operativo Windows Server 2012
    
      - CA del sistema operativo Windows Server 2012 R2

  - Certificati emessi da un'autorità di certificazione pubblica

La comunicazione con altre applicazioni e server, ad esempio Exchange 2013, richiede un certificato supportato da altre applicazioni e prodotti. Per la versione 2013, Lync Server 2013 e altri prodotti server Microsoft, tra cui Exchange 2013 e SharePoint Server, supportano il protocollo di autorizzazione aperta (OAuth) per l'autenticazione e l'autorizzazione da server a server. Per informazioni dettagliate, vedere [Managing server-to-Server Authentication (OAuth) e le applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) nella documentazione relativa alla distribuzione o nella documentazione relativa alle operazioni.

Per le connessioni dai client che eseguono il sistema operativo Windows 7, il sistema operativo Windows Server 2008 R2 e Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 include il supporto per (ma non richiede) i certificati firmati utilizzando la funzione hash di crittografia SHA-256. Per supportare l'accesso esterno mediante SHA-256, il certificato esterno viene rilasciato da una CA pubblica mediante SHA-256.

Per informazioni dettagliate sui requisiti dei certificati, vedere [Certificate Infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'utilizzo di caratteri jolly con i certificati, vedere Supporto dei certificati con [caratteri jolly in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) nella documentazione relativa alla supportabilità.

</div>

<span> </span>

</div>

</div>

</div>

