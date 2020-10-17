---
title: 'Lync Server 2013: Framework di sicurezza per Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f84b7eaf3476624479d1ecb7c7bb564a4eae8ad9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510443"
---
# <a name="security-framework-for-lync-server-2013"></a>Framework di sicurezza per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-08_

In questa sezione viene fornita una panoramica degli elementi fondamentali che formano il Framework di sicurezza per Microsoft Lync Server 2013. Comprendere il modo in cui questi elementi interagiscono è essenziale per prendere decisioni informate sulla protezione di una specifica distribuzione di Lync Server 2013.

Gli elementi sono i seguenti:

  - Servizi di dominio Active Directory (AD-DS) fornisce un singolo archivio back-end attendibile per gli account utente e le risorse di rete.

  - Role-Based controllo di accesso (RBAC) consente di delegare le attività amministrative mantenendo standard elevati per la sicurezza.

  - L'infrastruttura a chiave pubblica (PKI) utilizza i certificati emessi da autorità di certificazione (CAs) attendibili per autenticare i server e garantire l'integrità dei dati.

  - Transport Layer Security (TLS), HTTPS su SSL (HTTPS) e Mutual TLS (MTLS) consentono l'autenticazione degli endpoint e la crittografia della messaggistica istantanea. I flussi di condivisione di audio, video e applicazioni punto a punto sono crittografati mediante Secure Real-Time Transport Protocol (SRTP).

  - Protocolli standard di settore per l'autenticazione degli utenti, laddove possibile.

  - Windows PowerShell fornisce funzionalità di sicurezza abilitate per impostazione predefinita, in modo che gli utenti non possano eseguire facilmente o involontariamente script.

Questi elementi di sicurezza fondamentali interagiscono per definire utenti, server, connessioni e operazioni attendibili per garantire una base sicura per Lync Server 2013.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

Negli argomenti di questa sezione viene descritto il funzionamento di ognuno di questi elementi fondamentali per migliorare la sicurezza dell'infrastruttura di Lync Server.

  - [Servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Controllo dell'accesso basato sui ruoli (RBAC) per Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)

  - [Infrastruttura a chiave pubblica per Lync Server 2013](lync-server-2013-public-key-infrastructure.md)

  - [TLS e MTLS per Lync Server 2013](lync-server-2013-tls-and-mtls.md)

  - [Crittografia per Lync Server 2013](lync-server-2013-encryption.md)

  - [Autenticazione utente e client per Lync Server 2013](lync-server-2013-user-and-client-authentication.md)

  - [Strumenti di gestione di Windows PowerShell e Lync Server 2013](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

