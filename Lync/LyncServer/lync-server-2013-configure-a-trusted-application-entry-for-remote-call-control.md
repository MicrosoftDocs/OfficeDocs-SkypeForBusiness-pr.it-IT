---
title: Configurare una voce applicazione attendibile per il controllo delle chiamate remote
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be0dda3eedc73e5c64f7c275714955f3ce92af3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a>Configurare una voce applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-11-02_

Il gateway SIP/CSTA deve essere configurato come applicazione attendibile per consentire a Lync Server di applicare una route statica per instradare le chiamate al gateway.

<div>


> [!IMPORTANT]
> Se si sta eseguendo la migrazione di utenti da una versione precedente della distribuzione di Lync Server, assicurarsi di aver rimosso tutte le voci di applicazione attendibili esistenti (precedentemente note come voci di host autorizzati) create per il gateway SIP/CSTA prima di seguire le procedure descritte in questo argomento. Per informazioni dettagliate, vedere <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">rimuovere un host autorizzato legacy in Lync Server 2013 (facoltativo)</A>.<BR>Se si prevede di distribuire un nuovo controllo delle chiamate remote usando una connessione TCP (Transmission Control Protocol), è necessario verificare che il <STRONG>limite di utilizzo del servizio agli indirizzi IP selezionati</STRONG> sia impostato sulle applicazioni e i pool attendibili esistenti, se si vuole usare la stessa porta TCP per la nuova applicazione attendibile.



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a>Per configurare una voce di applicazione attendibile per il gateway SIP/CSTA

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o di un ruolo di controllo di accesso basato sui ruoli a cui è stato assegnato il cmdlet **New-CsTrustedApplicationPool** .

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Per creare una voce di applicazione attendibile, eseguire una delle operazioni seguenti:
    
      - Per una connessione TLS (Transport Layer Security), digitare quanto segue al prompt dei comandi:
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Ad esempio:
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - Per una connessione TCP (Transmission Control Protocol), digitare quanto segue al prompt dei comandi:
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Ad esempio:
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  Per aggiungere l'applicazione attendibile al pool, eseguire una delle operazioni seguenti:
    
      - Per una connessione TLS, digitare quanto segue al prompt dei comandi:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        Ad esempio:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - Per una connessione TCP, digitare quanto segue al prompt dei comandi:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        Ad esempio:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  Per implementare le modifiche pubblicate effettuate alla topologia, digitare quanto segue al prompt dei comandi:
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare una route statica per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Definire l'indirizzo IP di un gateway SIP/CSTA in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

