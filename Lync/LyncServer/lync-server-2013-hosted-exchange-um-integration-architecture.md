---
title: "Lync Server 2013: Architettura dell'integrazione della messaggistica unificata di Exchange ospitata"
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
ms.openlocfilehash: 49fbb815514d9a338412b638bdf373a285ebf6f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a>Architettura dell'integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-25_

L'applicazione di routing ExUM di Lync Server 2013 supporta l'integrazione con una distribuzione di messaggistica unificata di Exchange locale, con la messaggistica unificata di Exchange ospitata da un provider di servizi o con una combinazione dei due. Il diagramma seguente mostra tutte e tre le possibilità.

**Integrazione con una distribuzione della messaggistica unificata di Exchange locale e due provider di Exchange ospitati**

![Distribuzione della messaggistica unificata di Exchange con Lync Server in locale](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Distribuzione della messaggistica unificata di Exchange con Lync Server in locale")

Sono supportate le modalità seguenti:

  - **Distribuzione locale:** Lync Server 2013 e messaggistica unificata di Exchange sono entrambi distribuiti nei server locali all'interno dell'organizzazione.

  - **Distribuzione tra più locali:** Lync Server 2013 è distribuito nei server locali all'interno dell'organizzazione e la messaggistica unificata di Exchange è ospitata nella struttura di un provider di servizi online, ad esempio un Data Center di Microsoft Exchange Online.

  - **Distribuzione mista:** La distribuzione di Lync Server 2013 include alcune cassette postali utente in server Exchange locali all'interno dell'organizzazione e alcune cassette postali ospitate in un centro dati del servizio Exchange ospitato.
    
    <div>
    

    > [!NOTE]  
    > La distribuzione mista può essere usata come soluzione transitoria durante la valutazione e la migrazione graduale degli utenti alla messaggistica unificata di Exchange ospitata o una soluzione permanente se si sceglie di conservare i servizi di messaggistica unificata di Exchange in locale dopo il trasferimento di altri utenti.

    
    </div>

<div>

## <a name="shared-sip-address-space"></a>Spazio di indirizzi SIP condiviso

Per integrare Lync Server 2013 con una distribuzione di messaggistica unificata di Exchange locale, è possibile concedere a Lync Server 2013 l'autorizzazione per la lettura degli oggetti servizi di dominio Active Directory di Exchange UM. Questo approccio non funziona per l'integrazione con la messaggistica unificata di Exchange ospitata, tuttavia, poiché Lync Server 2013 e messaggistica unificata di Exchange vengono installati in foreste separate senza attendibilità.

Per integrare Lync Server 2013 con UM ospitata di Exchange, è necessario configurare uno *spazio di indirizzi SIP condiviso*. In questa configurazione lo stesso spazio per l'indirizzo del dominio SIP è disponibile sia per Lync Server 2013 che per il provider di servizi di messaggistica unificata di Exchange ospitati.

<div>


> [!NOTE]  
> L'uso dello spazio di indirizzi SIP condiviso è simile a quello usato in un ambiente di Lync Server 2013 tra più locali, in cui alcuni utenti si trovano nella distribuzione locale e alcuni sono ospitati in una distribuzioni ospitato, ad esempio Lync Online. Il dominio SIP viene diviso tra di essi. Quando si integra Lync Server 2013 con la messaggistica unificata di Exchange ospitata, assicurarsi di includere il provider di servizi di messaggistica unificata di Exchange nello spazio di indirizzi SIP condiviso.



</div>

Per configurare lo spazio di indirizzi SIP condiviso per l'integrazione con un provider di servizi di messaggistica unificata di Exchange, è necessario configurare il server perimetrale nel modo seguente:

1.  Configurare il server perimetrale per la federazione eseguendo il cmdlet **Set-CsAccessEdgeConfiguration** per impostare i parametri seguenti:
    
      - **UseDnsSrvRouting ** specifica che i server perimetrali si baseranno su record DNS SRV per l'invio e la ricezione di richieste di federazione.
    
      - **AllowFederatedUsers ** specifica se agli utenti interni è consentito comunicare con utenti di domini federati. Questa proprietà determina inoltre se gli utenti interni possono comunicare con gli utenti in uno scenario di dominio diviso.
    
      - **EnablePartnerDiscovery** specifica se Lync Server 2013 userà i record DNS per provare a individuare i domini partner non elencati nell'elenco domini consentiti di Active Directory. Se false, Lync Server 2013 verrà federato solo con i domini trovati nell'elenco domini consentiti. Questo parametro è obbligatorio se si utilizza il routing del servizio DNS. Nella maggior parte delle distribuzioni, il valore è impostato su False per impedire di aprire la federazione a tutti i partner.

2.  Replicare l'archivio di gestione centrale nel server perimetrale e verificare la replica. Per informazioni dettagliate, vedere [esportare la topologia di Lync Server 2013 e copiarla in elementi multimediali esterni per l'installazione di Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) nella documentazione relativa alla distribuzione.

3.  Configurare un *provider di hosting* nel server perimetrale eseguendo il cmdlet **New-CsHostingProvider** per impostare i parametri seguenti:
    
      - **Identity** specifica un identificatore di valore stringa univoco per il provider di hosting da creare, ad esempio **um ospitata di Exchange**.
    
      - **Enabled ** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Deve essere impostato su **true**.
    
      - **EnabledSharedAddressSpace** indica se il provider di hosting verrà usato in uno scenario di spazio di indirizzi SIP condiviso. Deve essere impostato su **true**.
    
      - **HostsOCSUsers** indica se il provider di hosting viene usato per ospitare gli account di 2013 di Lync Server. Deve essere impostato su **false**.
    
      - **ProxyFqdn** specifica il nome di dominio completo (FQDN) per il server proxy usato dal provider di hosting, ad esempio **proxyserver.fabrikam.com**. Contattare il provider di hosting per queste informazioni. Questo valore non può essere modificato. Se il provider di hosting cambia il server proxy, sarà necessario eliminarlo e ricrearlo.
    
      - La **lingua locale** indica se il server proxy usato dal provider di hosting è contenuto nella topologia di Lync Server 2013. Deve essere impostato su **false**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

