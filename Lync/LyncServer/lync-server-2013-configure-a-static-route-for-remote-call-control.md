---
title: 'Lync Server 2013: Configurare una route statica per il controllo delle chiamate remote'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfb825e51a9beec7010f9f46ed0fc649267897fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a>Configurare una route statica per il controllo delle chiamate remote in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-22_

Il controllo delle chiamate remote richiede che ogni pool di Lync Server sia configurato con un percorso da tale pool al gateway SIP/CSTA che si connette al PBX (Private Branch Exchange). Questo percorso richiede che ogni pool disponga di una route statica per ogni gateway a cui il pool proxy riceverà i messaggi di controllo delle chiamate SIP associati alle chiamate al PBX. Se si configura una route statica globale per il controllo delle chiamate remote, ogni pool che non è configurato con una route statica a livello di pool utilizzerà la route statica globale.

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a>Per configurare una route statica per il controllo delle chiamate remote

1.  Accedere a un computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o di un ruolo di controllo di accesso basato sui ruoli a cui è stato assegnato il cmdlet **New-CsStaticRoute** .

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Per creare una route statica e inserirla nella variabile $TLSRoute o $TCPRoute, eseguire una delle operazioni seguenti:
    
    <div class="">
    

    > [!TIP]  
    > Per confrontare i domini figlio di un dominio, è possibile specificare un valore jolly nel parametro MatchUri. Ad esempio, <STRONG>*. contoso.NET</STRONG>. Tale valore corrisponde a qualsiasi dominio che termina con il suffisso <STRONG>contoso.NET</STRONG>.

    
    </div>
    
      - Per una connessione TLS (Transport Layer Security), digitare quanto segue al prompt dei comandi:
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        Ad esempio:
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        Se UseDefaultCertificate è impostato su false, devi specificare i parametri TLSCertIssuer e TLSCertSerialNumber. Questi parametri indicano il nome dell'autorità di certificazione (CA) che ha emesso il certificato usato nella route statica e il numero seriale di tale certificato TLS, rispettivamente. Per informazioni dettagliate su questi parametri, vedere la Guida di Lync Server Management Shell digitando quanto segue al prompt dei comandi:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - Per una connessione TCP (Transmission Control Protocol), digitare quanto segue al prompt dei comandi:
        
        <div class="">
        

        > [!NOTE]  
        > Se si specifica un nome di dominio completo (FQDN), prima di tutto è necessario configurare un record DNS (Domain Name System).

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        Ad esempio:
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        Di seguito sono riportati i valori predefiniti per i parametri facoltativi per le route statiche:
        
          - Enabled = true
        
          - MatchOnlyPhoneUri = false
        
          - ReplaceHostInRequestUri = false
        
        Ti consigliamo vivamente di non modificare questi valori predefiniti. Se tuttavia è necessario modificare uno di questi parametri, vedere la Guida di Lync Server Management Shell digitando quanto segue al prompt dei comandi:
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  Per rendere persistente una route statica appena creata nell'archivio di gestione centrale, eseguire una delle operazioni seguenti, a seconda delle esigenze:
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare una voce applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[Definire l'indirizzo IP di un gateway SIP/CSTA in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

