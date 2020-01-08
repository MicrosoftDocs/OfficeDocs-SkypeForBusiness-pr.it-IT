---
title: 'Lync Server 2013: Security Framework per Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17900e0ca9db8f9dbc1bf66a1bd65aff62d9dd62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a>Framework di sicurezza per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-08_

Questa sezione offre una panoramica degli elementi fondamentali che costituiscono il Framework di sicurezza per Microsoft Lync Server 2013. È essenziale comprendere il modo in cui questi elementi collaborano per prendere decisioni informate sulla protezione della specifica distribuzione di Lync Server 2013.

Questi elementi sono i seguenti:

  - Active Directory Domain Services (AD DS) offre un unico repository back-end attendibile per gli account utente e le risorse di rete.

  - Controllo di accesso basato sui ruoli (RBAC) consente di delegare le attività amministrative mantenendo standard elevati per la sicurezza.

  - Infrastruttura a chiave pubblica (PKI) USA i certificati emessi da autorità di certificazione (CAs) attendibili per autenticare i server e garantire l'integrità dei dati.

  - Transport Layer Security (TLS), HTTPS su SSL (HTTPS) e TLS reciproche (MTLS) abilitano l'autenticazione dell'endpoint e la crittografia della messaggistica istantanea (IM). I flussi audio, video e di condivisione delle applicazioni Point-to-Point vengono crittografati usando il protocollo SRTP (Secure Real-Time Transport Protocol).

  - Protocolli standard del settore per l'autenticazione dell'utente, ove possibile.

  - Windows PowerShell offre funzionalità di sicurezza abilitate per impostazione predefinita in modo che gli utenti non possano eseguire facilmente o inconsapevolmente gli script.

Questi elementi di sicurezza fondamentali collaborano per definire gli utenti, i server, le connessioni e le operazioni attendibili per garantire una base sicura per Lync Server 2013.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

Negli argomenti di questa sezione viene descritto il funzionamento di ognuno di questi elementi fondamentali per migliorare la sicurezza dell'infrastruttura di Lync Server.

  - [Servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [Controllo di accesso basato sui ruoli (RBAC) per Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md)

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

