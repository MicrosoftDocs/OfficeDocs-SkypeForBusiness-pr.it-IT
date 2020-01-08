---
title: "Lync Server 2013: requisiti dell'app Lync di Windows Store"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806fb7a71232492be7ef01474136817b7808111e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a>Requisiti dell'app Lync di Windows Store per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-12-03_

Le organizzazioni con una distribuzione locale di Lync Server devono soddisfare i requisiti seguenti per supportare l'app Lync di Windows Store.

<div>


> [!NOTE]  
> Per Lync Server 2010, eseguire l'aggiornamento cumulativo per Lync Server 2010:2012 febbraio (disponibile su <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2670352</A>) o versione successiva in tutti i server. Per consentire agli utenti di partecipare a riunioni, eseguire l'aggiornamento cumulativo per Lync Server 2010: ottobre 2012 (disponibile all'indirizzo <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2737915</A>) nei server.



</div>

  - Abilitare l'individuazione automatica, Lync Web App e i servizi di ticket web nel server.

  - Abilitare l'autenticazione dei certificati nel server front-end o nel pool Front-end. Il processo di registrazione dell'utente nel server front-end o nel pool Front-end viene spesso indicato come registrar. Per informazioni dettagliate, vedere [creare impostazioni di configurazione del registrar in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).

  - Pubblicare i record di risorse DNS alias (CNAME) per il servizio di individuazione automatica.

  - Non è più necessario verificare che il punto di distribuzione dell'elenco di revoche di certificati (CRL) del certificato rilasciato a Lync Server punti a una risorsa HTTP invece che a una risorsa LDAP. Verificare tuttavia che i computer client abbiano installato gli aggiornamenti più recenti di Windows.

  - Configurare i proxy HTTP nell'organizzazione per consentire il traffico HTTP correlato a Lync Server.Se necessario, aggiungere eccezioni per i servizi di individuazione automatica, Lync Web App e webticket.

  - Nei client installare Windows 8,1 e la versione più recente dell'app Lync di Windows Store per risolvere un problema di accesso che si verifica in genere quando si usano più domini, ad esempio quando l'URI SIP è **usera@domainZ.com** ma il server perimetrale è **SIP.domainX.com**.

Se l'organizzazione sottoscrive Lync Online o Office 365 e si usa il proprio nome di dominio, è necessario eseguire alcuni passaggi aggiuntivi per configurare la rete per l'individuazione automatica dei server Lync. I requisiti di configurazione della rete sono gli stessi per l'app Lync di Windows Store e Lync nei dispositivi mobili. Seguire le istruzioni "configurare la rete" nell'articolo wiki di Office 365 "configurare i dispositivi mobili Lync" disponibile all'indirizzo [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione dell'app Lync di Windows Store in Lync Server 2013](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

