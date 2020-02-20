---
title: 'Lync Server 2013: eliminare le impostazioni di configurazione esistenti per il registrar'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19f127efa6e2cab04434dd8de6e541897d50483f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a>Eliminare le impostazioni di configurazione di registrazione esistenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Eseguire la procedura seguente per eliminare una funzione di registrazione.

<div>

## <a name="to-delete-registrar-configuration-settings"></a>Per eliminare le impostazioni di configurazione del servizio di registrazione

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Sicurezza**, quindi su **Funzione di registrazione**.

4.  Nella pagina **Funzione di registrazione** digitare il nome della funzione di registrazione che si desidera eliminare nel campo di ricerca, per intero o in parte.

5.  Nell'elenco fare clic sulla funzione di registrazione desiderata, fare clic su **Modifica**, quindi su **Elimina**.

6.  Fare clic su **OK**.

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione del servizio di registrazione tramite i cmdlet di Windows PowerShell

È possibile eliminare le impostazioni di configurazione del servizio di registrazione utilizzando Windows PowerShell e il cmdlet **Remove-CsProxyConfiguration** . È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>Per rimuovere un set specifico di impostazioni di sicurezza della funzione di registrazione

  - Il comando seguente rimuove le impostazioni di sicurezza della funzione di registrazione applicate al server perimetrale atl-edge-011.litwareinc.com:
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>Per rimuovere tutte le impostazioni di sicurezza della funzione di registrazione applicate all'ambito del sito

  - Il comando seguente rimuove tutte le impostazioni di sicurezza della funzione di registrazione applicate al servizio di registrazione:
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>Per rimuovere tutte le impostazioni di sicurezza della funzione di registrazione che consentono l'autenticazione NTLM

  - Il comando seguente elimina tutte le impostazioni di sicurezza della funzione di registrazione che consentono l'utilizzo di NTLM per l'autenticazione client:
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

Per informazioni dettagliate, vedere [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

