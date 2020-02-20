---
title: 'Lync Server 2013: architettura di integrazione della messaggistica unificata di Exchange ospitata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb0e195b10f5c368e2b12d2dfdc00be0fa1b3da2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Architettura di integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-25_

L'applicazione di routing di Lync Server 2013 ExUM supporta l'integrazione con una distribuzione di messaggistica unificata di Exchange locale, con la messaggistica unificata di Exchange ospitata da un provider di servizi o con una combinazione di due. Nella figura riportata di seguito vengono illustrate tutte e tre queste possibilità.

**Integrazione con una distribuzione della messaggistica unificata di Exchange locale e due provider di Exchange ospitati**

![Distribuzione della messaggistica unificata di Exchange in locale di Lync Server](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Distribuzione della messaggistica unificata di Exchange in locale di Lync Server")

Sono supportate le modalità seguenti:

  - **Distribuzione locale:** Lync Server 2013 e la messaggistica unificata di Exchange sono entrambi distribuiti nei server locali all'interno dell'organizzazione.

  - **Distribuzione cross-premise:** Lync Server 2013 è distribuito nei server locali all'interno dell'organizzazione e la messaggistica unificata di Exchange è ospitata nella struttura di un provider di servizi online, ad esempio un Data Center di Microsoft Exchange Online.

  - **Distribuzione mista:** La distribuzione di Lync Server 2013 dispone di alcune cassette postali utente nei server Exchange locali all'interno dell'azienda e di alcune cassette postali ospitate in un data center del servizio di Exchange ospitato.
    
    <div>
    

    > [!NOTE]  
    > La distribuzione mista può essere utilizzata come soluzione di transizione durante la valutazione e la migrazione in fasi degli utenti nella messaggistica unificata di Exchange ospitata oppure come soluzione definitiva se si sceglie di lasciare in locale i servizi di messaggistica unificata di Exchange di alcuni utenti dopo averne trasferiti altri.

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>Spazio di indirizzamento SIP condiviso

Per integrare Lync Server 2013 con una distribuzione di messaggistica unificata di Exchange locale, è possibile concedere l'autorizzazione Lync Server 2013 alla lettura degli oggetti di servizi di dominio Active Directory di messaggistica unificata di Exchange. Questo approccio non funziona per l'integrazione con la messaggistica unificata di Exchange ospitata, tuttavia, perché Lync Server 2013 e la messaggistica unificata di Exchange sono installati in foreste separate senza alcuna relazione di trust tra di essi.

Per integrare Lync Server 2013 con messaggistica unificata di Exchange ospitata, è necessario configurare uno *spazio di indirizzi SIP condiviso*. In questa configurazione, lo stesso spazio degli indirizzi del dominio SIP è disponibile sia per Lync Server 2013 che per il provider di servizi di messaggistica unificata di Exchange ospitati.

<div>


> [!NOTE]  
> L'utilizzo dello spazio di indirizzi SIP condiviso è simile a quello utilizzato in un ambiente Lync Server 2013 cross-premise, in cui alcuni utenti sono ospitati nella distribuzione locale e alcuni sono disponibili in una distribuzione di hosting (come Lync Online). Il dominio SIP è diviso tra loro. Quando si integra Lync Server 2013 con la messaggistica unificata di Exchange ospitata, assicurarsi di includere il provider di servizi di messaggistica unificata di Exchange nello spazio di indirizzi SIP condiviso.



</div>

Per configurare lo spazio di indirizzamento SIP condiviso per l'integrazione con un provider di servizi di messaggistica unificata di Exchange, sarà necessario configurare il server perimetrale come segue:

1.  Configurare il server perimetrale per la federazione eseguendo il cmdlet **Set-CsAccessEdgeConfiguration** per impostare i parametri seguenti:
    
      - **UseDnsSrvRouting** consente di specificare che i server perimetrali si baseranno sui record SRV DNS durante l'invio e la ricezione delle richieste di federazione.
    
      - **AllowFederatedUsers** specifica se agli utenti interni è consentito comunicare con utenti di domini federati. Questa proprietà determina inoltre se gli utenti interni possono comunicare con gli utenti in uno scenario di dominio diviso.
    
      - **EnablePartnerDiscovery** specifica se Lync Server 2013 utilizzerà i record DNS per cercare di individuare i domini dei partner che non sono elencati nell'elenco di domini consentiti di Active Directory. Se false, Lync Server 2013 verrà federata solo con i domini che si trovano nell'elenco dei domini consentiti. Questo parametro è obbligatorio se si utilizza il routing del servizio DNS. Nella maggior parte delle distribuzioni, il valore è impostato su False per impedire di aprire la federazione a tutti i partner.

2.  Replicare l'archivio di gestione centrale nel server perimetrale e verificare la replica. Per ulteriori informazioni, vedere [esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) nella documentazione relativa alla distribuzione.

3.  Configurare un *provider di hosting* nel server perimetrale eseguendo il cmdlet **New-CsHostingProvider** per impostare i parametri seguenti:
    
      - **Identity** consente di specificare un identificatore come valore stringa univoco per il provider di hosting da creare, ad esempio **Messaggistica unificata Exchange ospitata**.
    
      - **Enabled** consente di indicare se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Deve essere impostato su **True**.
    
      - **EnabledSharedAddressSpace** consente di indicare se il provider di hosting verrà utilizzato in uno scenario con spazio di indirizzamento SIP condiviso. Deve essere impostato su **True**.
    
      - **HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare gli account di Lync Server 2013. Deve essere impostato su **False**.
    
      - **ProxyFQDN** consente di specificare il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting, ad esempio **serverproxy.fabrikam.com**. Per avere tali informazioni, rivolgersi al provider di hosting. Questo valore non può essere modificato. Se il provider di hosting cambia server proxy, sarà necessario eliminare e quindi ricreare la voce per il provider.
    
      - La **lingua locale** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia di Lync Server 2013. Deve essere impostato su **False**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

