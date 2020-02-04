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
ms.openlocfilehash: 9f883e8d730e63788b4cbe0ccd3315f21e6fea97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a>Configurare il supporto federativo per un dominio Lync online in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Per la Federazione con un cliente di Microsoft Lync Online 2010 è necessario eseguire la procedura seguente:

  - Configurare il supporto per il dominio del cliente di Lync Online 2010, ad esempio contoso.onmicrosoft.com. Come specificato nei [prerequisiti per la Federazione con un cliente di Lync Online nella sezione Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) di questa documentazione, è necessario avere già abilitato la Federazione per l'organizzazione. L'abilitazione della Federazione richiede l'impostazione del metodo da usare per controllare l'accesso da domini federati. Se l'organizzazione è stata configurata per l'uso dell'individuazione, l'aggiunta del dominio all'elenco consentiti dell'organizzazione è facoltativa. Se non è stata abilitata l'individuazione del dominio, è necessario aggiungere il nome di dominio del cliente di Lync Online all'elenco dei domini consentiti. È possibile aggiungere un nome di dominio usando il pannello di controllo di Lync Server oppure eseguendo il cmdlet **New-CsAllowedDomain** . Per informazioni dettagliate sull'uso del pannello di controllo di Lync Server, incluso l'attivazione dell'individuazione dei domini, vedere [gestire i provider federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) nella documentazione Operations. Per informazioni dettagliate sull'uso del cmdlet **New-CsAllowedDomain** per aggiungere un dominio, vedere [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) nella documentazione Operations.
    
    <div>
    

    > [!NOTE]  
    > Un cliente di Lync Online può avere più domini. Se si vuole eseguire la Federazione con più di uno dei domini, è necessario configurare il supporto per ogni singolo dominio con cui si vuole supportare la federazioni e l'amministratore del cliente di Lync Online deve abilitare la Federazione per ognuno dei domini come federati.

    
    </div>

  - Configurare il supporto per il provider di hosting del dominio cliente di Lync Online 2010 con cui si vuole eseguire la Federazione. Usare la procedura descritta in questa sezione per configurare il supporto per il provider di hosting.
    
    <div>
    

    > [!NOTE]  
    > Questo passaggio è obbligatorio solo per la Federazione con un dominio di un cliente di Lync Online, non per la Federazione con qualsiasi dominio distribuito localmente nella posizione di un partner federato.

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a>Per configurare il supporto per un provider di hosting

1.  Da un server front-end avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet **New-CsHostingProvider** per creare e configurare il provider di hosting. Ad esempio, eseguire:
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    Nell'esempio precedente vengono impostati i parametri seguenti:
    
      - **Identity** specifica un identificatore di valore stringa univoco per il provider di hosting da creare. Si noti che il comando non riesce se è già stato configurato un provider esistente per questo valore Identity.
    
      - **ProxyFqdn** specifica il nome di dominio completo (FQDN) per il server proxy usato dal provider di hosting. Questo valore non può essere modificato. Se il provider di hosting cambia server proxy è necessario eliminare e ricreare la voce per il provider.
    
      - **VerificationLevel** specifica come vengono verificati i messaggi di posta elettronica inviati da un provider di hosting per verificare che siano stati inviati da tale provider.
    
      - **Enabled ** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata. Finché il valore non verrà impostato su **True **, le due organizzazioni non potranno scambiarsi messaggi.
    
      - **EnabledSharedAddressSpace ** indica se il provider di hosting verrà utilizzato in uno scenario con spazio degli indirizzi SIP condiviso (dominio diviso).
    
      - **HostsOCSUsers** indica se il provider di hosting viene usato per ospitare gli account di Lync Server. Se **False **, il provider ospiterà altri tipi di account, ad esempio quelli di Microsoft Exchange.
    
      - La **lingua locale** indica se il server proxy usato dal provider di hosting è contenuto all'interno della topologia di Lync Server.
    
    Per informazioni dettagliate sull'uso di questo cmdlet, vedere [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) nella documentazione Operations.

</div>

</div>

<span> </span>

</div>

</div>

</div>

