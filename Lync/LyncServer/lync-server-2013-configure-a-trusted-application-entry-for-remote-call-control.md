---
title: Configurare una voce di applicazione attendibile per il controllo delle chiamate remote
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f8175a351d13675c048efce7a2f831af7ab2c31
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523063"
---
# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a>Configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-11-02_

Il gateway SIP/CSTA deve essere configurato come applicazione attendibile affinché Lync Server applichi una route statica per instradare le chiamate al gateway.

<div>


> [!IMPORTANT]
> Se si esegue la migrazione di utenti da una versione precedente della distribuzione di Lync Server, assicurarsi di aver rimosso tutte le voci dell'applicazione attendibile esistenti (in precedenza note come voci host autorizzate) create per il gateway SIP/CSTA prima di seguire le procedure descritte in questo argomento. Per informazioni dettagliate, vedere <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a Legacy Authorized host in Lync Server 2013 (optional)</A>.<BR>Se si prevede di distribuire un nuovo controllo delle chiamate remote utilizzando una connessione TCP (Transmission Control Protocol), è necessario verificare che l' <STRONG>utilizzo del servizio Limit per gli indirizzi IP selezionati</STRONG> sia impostato su applicazioni e pool attendibili esistenti, se si desidera utilizzare la stessa porta TCP per la nuova applicazione attendibile.



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a>Per configurare una voce di applicazione attendibile per il gateway SIP/CSTA

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o di un ruolo di controllo di accesso basato sui ruoli a cui è stato assegnato il cmdlet **New-CsTrustedApplicationPool** .

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Per creare una voce di applicazione attendibile, eseguire una delle operazioni seguenti:
    
      - Per una connessione TLS (Transport Layer Security), al prompt dei comandi digitare quanto segue:
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Ad esempio:
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - Per una connessione TCP (Transmission Control Protocol), al prompt dei comandi digitare quanto segue:
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        Ad esempio:
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  Per aggiungere l'applicazione attendibile al pool, eseguire una delle operazioni seguenti:
    
      - Per una connessione TLS, al prompt dei comandi digitare quanto segue:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        Ad esempio:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - Per una connessione TCP, al prompt dei comandi digitare quanto segue:
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        Ad esempio:
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  Per implementare le modifiche pubblicate apportate alla topologia, al prompt dei comandi digitare quanto segue:
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare una route statica per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Definire un indirizzo IP del gateway SIP/CSTA in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

