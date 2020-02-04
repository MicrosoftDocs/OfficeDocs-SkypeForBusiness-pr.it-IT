---
title: 'Lync Server 2013: (Facoltativo) Verificare le conferenze telefoniche con accesso esterno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1b5f078ccd5e95df708012b7be1527736133392
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a>(Facoltativo) Verificare le conferenze telefoniche con accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2011-01-21_

Per verificare che la pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno e i numeri per le connessioni in ingresso funzionino correttamente, è necessario eseguire le operazioni seguenti:

  - Testare la pagina Web delle impostazioni dei servizi di conferenza telefonica con accesso esterno accedendo all'URL semplice.

  - Verificare che i numeri di accesso funzionino correttamente per un pool specifico eseguendo lo script più avanti in questo argomento. Questo script simula le chiamate ai numeri di accesso. È necessario l'indirizzo SIP e le credenziali di un client Unified Communications (UC) ospitato nel pool specifico per l'uso di questo script.

Questo passaggio è facoltativo.

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a>Per testare i numeri di accesso per un pool specifico

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo **Cs-ServerAdministrator** o **CsAdministrator** .

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire la procedura seguente al prompt dei comandi:
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    Il report risultante Mostra l'esito positivo o negativo, insieme a specifiche informazioni di diagnostica. Il contrassegno-Verbose fornisce informazioni più dettagliate sul numero di numeri di accesso trovati e sui relativi dettagli.

</div>

</div>

<span> </span>

</div>

</div>

</div>

