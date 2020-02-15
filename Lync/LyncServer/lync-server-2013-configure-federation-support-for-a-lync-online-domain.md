---
title: 'Lync Server 2013: configurare il supporto federativo per un dominio Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83d14f66c03ccc7def2773f7c5c8ae841b71d103
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>Configurare il supporto federativo per un dominio Lync online in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Per la Federazione con un cliente di Microsoft Lync Online 2010 è necessario completare i passaggi seguenti:

  - Configurare il supporto per il dominio del cliente di Lync Online 2010 (ad esempio, contoso.onmicrosoft.com). Come specificato nei [prerequisiti per la Federazione con un cliente di Lync online in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) sezione di questa documentazione, è necessario avere già abilitato la Federazione per l'organizzazione. Se si abilita la federazione, è necessario specificare il metodo da utilizzare per controllare l'accesso da parte dei domini federati. Se l'organizzazione è stata configurata in modo da utilizzare l'individuazione, l'aggiunta del dominio all'elenco dei domini consentiti dell'organizzazione è facoltativa. Se l'individuazione del dominio non è stata abilitata, è necessario aggiungere il nome di dominio del cliente Lync Online all'elenco dei domini consentiti. È possibile aggiungere un nome di dominio utilizzando il pannello di controllo di Lync Server o eseguendo il cmdlet **New-CsAllowedDomain** . Per informazioni dettagliate sull'utilizzo del pannello di controllo di Lync Server, inclusa l'abilitazione dell'individuazione dei domini, vedere [Manage SIP Federated Providers for your organization in Lync server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) nella documentazione relativa alle operazioni. Per informazioni dettagliate sull'utilizzo del cmdlet **New-CsAllowedDomain** per aggiungere un dominio, vedere [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) nella documentazione relativa alle operazioni.
    
    <div>
    

    > [!NOTE]  
    > Un cliente di Lync Online può disporre di più domini. Se si desidera eseguire la Federazione con più domini, è necessario configurare il supporto per ogni singolo dominio con cui si desidera supportare il servizio federativo e l'amministratore del cliente di Lync Online deve abilitare la Federazione per ognuno dei domini da federata.

    
    </div>

  - Configurare il supporto per il provider di hosting del dominio dei clienti di Lync Online 2010 con cui si desidera eseguire la Federazione. Utilizzare la procedura disponibile in questa sezione per configurare il supporto per tale provider.
    
    <div>
    

    > [!NOTE]  
    > Questo passaggio è obbligatorio solo per la Federazione con un dominio di un cliente di Lync Online, non per la Federazione con qualsiasi dominio distribuito in locale nella posizione di un partner federato.

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>Per configurare il supporto per un provider di hosting

1.  Da un front end server, avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet **New-CsHostingProvider** per creare e configurare il provider di hosting. Ad esempio, eseguire:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    Nell'esempio precedente vengono impostati i parametri seguenti:
    
      - **Identity** specifica un identificatore di valore stringa univoco per il provider di hosting che si sta creando. Il comando avrà esito negativo se è stato già configurato un provider esistente con lo stesso valore di Identity.
    
      - **ProxyFQDN** specifica il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting. Questo valore non può essere modificato. Se il provider di hosting cambia server proxy, sarà necessario eliminare e quindi ricreare la voce per il provider.
    
      - **VerificationLevel** specifica come o se i messaggi inviati da un provider di hosting devono essere verificati per accertare che provengano effettivamente da quel provider.
    
      - **Enabled** indica se la connessione di rete fra il proprio dominio e il provider di hosting è abilitata. Finché il valore non viene impostato su **True**, le due organizzazioni non potranno scambiarsi messaggi.
    
      - **EnabledSharedAddressSpace** indica se il provider di hosting verrà utilizzato in uno scenario con spazio degli indirizzi SIP condiviso (dominio diviso).
    
      - **HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare gli account di Lync Server. Se **False**, il provider ospiterà altri tipi di account, ad esempio quelli di Microsoft Exchange.
    
      - La **lingua locale** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia di Lync Server.
    
    Per informazioni dettagliate sull'utilizzo di questo cmdlet, vedere [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) nella documentazione relativa alle operazioni.

</div>

</div>

<span> </span>

</div>

</div>

</div>

