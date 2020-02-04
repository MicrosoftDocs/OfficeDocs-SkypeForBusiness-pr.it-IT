---
title: 'Lync Server 2013: eliminare le impostazioni di configurazione del servizio Web esistenti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0eb310836e78d46f94412018f3034a4a5f7d7173
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a>Eliminare le impostazioni di configurazione del servizio Web esistenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Seguire questa procedura per eliminare le impostazioni di configurazione del servizio Web.

<div>

## <a name="to-delete-web-service-configuration-settings"></a>Per eliminare le impostazioni di configurazione del servizio Web

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **servizio Web**.

4.  Nella pagina **servizio Web** e nel campo di ricerca digitare tutto o parte del nome del criterio che si desidera eliminare.

5.  Nell'elenco dei criteri fare clic sui criteri desiderati, fare clic su **modifica**e quindi su **Elimina**.

6.  Fare clic su **OK**.

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Eliminazione delle impostazioni di configurazione del servizio Web tramite i cmdlet di Windows PowerShell

Per eliminare le impostazioni di configurazione del servizio Web, è possibile usare Windows PowerShell e il cmdlet **Remove-CsWebServiceConfiguration** . Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>Per eliminare una raccolta specifica di impostazioni di configurazione del servizio Web

  - Il comando seguente rimuove le impostazioni di sicurezza del servizio Web applicate al sito Redmond:
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>Per eliminare tutte le impostazioni di configurazione del servizio Web applicate all'ambito del sito

  - Il comando seguente rimuove tutte le impostazioni di sicurezza del servizio Web applicate all'ambito del servizio:
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>Per eliminare tutte le impostazioni di configurazione del servizio Web che consentono l'autenticazione dei certificati

  - Il comando seguente rimuove tutte le impostazioni di sicurezza del servizio Web che consentono l'uso dell'autenticazione dei certificati:
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

Per informazioni dettagliate, vedere [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione dell'autenticazione nel pannello di controllo di Lync Server 2013](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

