---
title: 'Lync Server 2013: requisiti delle app di Windows Store per Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5e85bf0d6e4281094be562bd94c8e5b76e02453
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Requisiti delle app di Windows Store di Lync per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-12-03_

Le organizzazioni che dispongono di una distribuzione locale di Lync Server devono soddisfare i requisiti seguenti per supportare l'app Windows Store di Lync.

<div>


> [!NOTE]  
> Per Lync Server 2010, eseguire l'aggiornamento cumulativo per Lync Server 2010: febbraio 2012 (disponibile all'indirizzo <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2670352</A>) o versioni successive su tutti i server. Per consentire agli utenti di partecipare alle riunioni, eseguire l'aggiornamento cumulativo per Lync Server 2010: ottobre 2012 (disponibile all'indirizzo <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; kbid = 2737915</A>) nei server.



</div>

  - Abilitare l'individuazione automatica, Lync Web App e i servizi ticket web sul server.

  - Abilitare l'autenticazione dei certificati nel front end server o nel pool Front end. Il processo di registrazione degli utenti nel front end server o nel pool Front End è spesso definito come registrar. Per ulteriori informazioni, vedere [creazione di impostazioni di configurazione di registrazione in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).

  - Pubblicare i record delle risorse di alias DNS (CNAME) per il servizio di individuazione automatica.

  - Non è più necessario verificare che il punto di distribuzione dell'elenco di revoche di certificati (CRL, Certificate Revocation List) per il certificato emesso in Lync Server punti a una risorsa HTTP invece che a una risorsa LDAP. Assicurarsi tuttavia che i computer client dispongano degli aggiornamenti di Windows più recenti.

  - Configurare i proxy HTTP nell'organizzazione per consentire il traffico HTTP relativo a Lync Server.Aggiungere eccezioni per i servizi di individuazione automatica, Lync Web App e webticket, se necessario.

  - Nei client, installare Windows 8,1 e la versione più recente di Lync Windows Store app per correggere un problema di accesso che si verifica generalmente quando si utilizzano più domini (ad esempio, quando l'URI SIP è **usera@domainZ.com** ma il server perimetrale è **SIP.domainX.com**).

Se l'organizzazione sottoscrive Lync Online o Microsoft 365 e si utilizza il proprio nome di dominio, è necessario eseguire alcuni passaggi aggiuntivi per configurare la rete per l'individuazione automatica dei server Lync. I requisiti di configurazione della rete sono gli stessi per l'app Lync Windows Store e Lync su dispositivi mobili.

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione di Lync Windows Store app in Lync Server 2013](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
