---
title: Testare e segnalare la disponibilità funzionale per l'autenticazione Kerberos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8763203827afd3d14638b68474c4f9bd9d6d0cfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a>Testare e segnalare la disponibilità funzionale per l'autenticazione Kerberos in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-01-16_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso come utente membro del gruppo RTCUniversalServerAdmins.

Puoi usare il cmdlet **Test-CsKerberosAccountAssignment** di Windows PowerShell per testare e segnalare la disponibilità funzionale di un'assegnazione di sito per l'autenticazione Kerberos. Questo comando esegue una query sul sito specificato nel parametro Identity obbligatorio. Il parametro facoltativo report fa sì che il cmdlet scriva un report HTML in C\\: log nel computer in cui viene eseguito il comando. Il parametro Verbose facoltativo riporta le informazioni sull'attività sullo schermo.

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a>Per testare e segnalare la disponibilità funzionale per l'autenticazione Kerberos per un sito

1.  Come membro del gruppo RTCUniversalServerAdmins, accedere a un computer nel dominio in cui è in uso Lync Server 2013 o nel computer in cui sono installati gli strumenti di amministrazione.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Nella riga di comando eseguire il comando seguente:
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    Ad esempio:
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

