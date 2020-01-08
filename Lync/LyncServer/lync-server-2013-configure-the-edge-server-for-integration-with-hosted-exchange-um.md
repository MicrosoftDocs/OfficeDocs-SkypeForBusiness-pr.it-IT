---
title: Configurare il server perimetrale per l'integrazione con la messaggistica unificata di Exchange ospitata
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7d9d37e5ed9127c81f0aec4fcdc8f2e90b5940f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a>Configurare il server perimetrale per l'integrazione con la messaggistica unificata di Exchange ospitata

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-01-23_

Per specificare agli utenti di Lync Server 2013 le funzionalità della segreteria telefonica ospitata di messaggistica unificata di Exchange, è necessario eseguire le attività di configurazione seguenti nell'Edge Server:

  - Configurare il server perimetrale per la federazione.

  - Replicare i dati dell'archivio di gestione centrale nel server perimetrale e verificare la replica.

  - Creare un provider di hosting nel server perimetrale.

Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))

  - [New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))

<div>


> [!IMPORTANT]
> Prima di eseguire queste operazioni, è necessario creare un record DNS SRV esterno per il servizio Exchange di hosting. Per informazioni dettagliate, vedere <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">creare un record SRV DNS per l'integrazione con la messaggistica unificata di Exchange ospitata</A>.



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a>Per configurare il server perimetrale per la federazione

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet Set-CsAccessEdgeConfiguration per configurare il server per la federazione. Ad esempio, eseguire:
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    Nell'esempio precedente vengono impostati i parametri seguenti:
    
      - **UseDnsSrvRouting ** specifica che i server perimetrali si baseranno su record DNS SRV per l'invio e la ricezione di richieste di federazione.
    
      - **AllowFederatedUsers ** specifica se agli utenti interni è consentito comunicare con utenti di domini federati. Questa proprietà determina inoltre se gli utenti interni possono comunicare con gli utenti in uno scenario di dominio diviso.
    
      - **EnablePartnerDiscovery** specifica se Lync Server userà i record DNS per provare a individuare i domini partner non elencati nell'elenco domini consentiti di Active Directory. Se false, Lync Server 2013 verrà solo federato con i domini trovati nell'elenco domini consentiti. Questo parametro è obbligatorio se si utilizza il routing del servizio DNS. Nella maggior parte delle distribuzioni, il valore è impostato su False per impedire di aprire la federazione a tutti i partner.

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a>Per replicare i dati nel server perimetrale e verificare la replica

  - Verificare che la replica nel server perimetrale sia completa. Per la procedura, vedere [verificare la connettività tra server interni e Edge Server in Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a>Per creare un provider di hosting nel server perimetrale

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet **New-CsHostingProvider** per configurare il provider di hosting. Ad esempio, eseguire:
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    Nell'esempio precedente vengono impostati i parametri seguenti:
    
      - **Identity ** specifica un identificatore di valore di stringa univoco per il provider di hosting da creare, in questo esempio **Fabrikam.com **. Si noti che il comando non riesce se è già stato configurato un provider esistente per questo valore Identity.
    
      - **Enabled ** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Finché il valore non verrà impostato su **True **, le due organizzazioni non potranno scambiarsi messaggi.
    
      - **EnabledSharedAddressSpace ** indica se il provider di hosting verrà utilizzato in uno scenario con spazio degli indirizzi SIP condiviso (dominio diviso).
        
        <div>
        

        > [!NOTE]
        > Prima di impostare <CODE>EnableSharedAddressSpace</CODE> true, provare a risolvere internamente il record SRV della Federazione. Se il record non può essere risolto internamente, è necessario creare i record _sipfederationtls. _tcp. &lt;domain&gt; e _sip. _tls. &lt;dominio&gt; nel DNS interno. Tali record devono fare riferimento all'indirizzo IP esterno di Access Interface del server perimetrale.

        
        </div>
    
      - **HostsOCSUsers** indica se il provider di hosting viene usato per ospitare gli account di 2013 di Lync Server. Se **False **, il provider ospiterà altri tipi di account, ad esempio quelli di Microsoft Exchange.
    
      - **ProxyFQDN ** specifica il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting, in questo esempio **proxyserver.fabrikam.com **. Questo valore non può essere modificato. Se il provider di hosting cambia server proxy è necessario eliminare e ricreare la voce per il provider.
    
      - La **lingua locale** indica se il server proxy usato dal provider di hosting è contenuto nella topologia di Lync Server 2013.
    
      - **VerficationLevel ** indica il livello di verifica consentito per i messaggi inviati e ricevuti dal provider ospitato. Specificare **UseSourceVerification**, che si basa sul livello di verifica incluso nei messaggi inviati dal provider di hosting. Se il livello non è specificato, il messaggio verrà rifiutato in quanto non verificabile.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[Verificare la connettività tra server interni e server perimetrali in Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

