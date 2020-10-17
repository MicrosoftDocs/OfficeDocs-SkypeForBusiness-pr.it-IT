---
title: Abilitare l'integrazione di Exchange 2013 Outlook Web App e della messaggistica istantanea
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da6866565df12ff4484124836f9164d2bf8c35c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502883"
---
# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Abilitare l'integrazione di Exchange 2013 Outlook Web App e della messaggistica istantanea

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Per abilitare l'integrazione di Exchange 2013 Outlook Web Access (OWA) e della messaggistica istantanea con Lync Server 2013, è necessario aggiungere il server Accesso client (CAS) di Exchange 2013 alla topologia di Lync Server 2013 come server applicazioni attendibili.

<div>

## <a name="to-create-a-trusted-application-pool"></a>Per creare un pool di applicazioni attendibili

1.  Avviare Lync Server 2013 Management Shell.

2.  Eseguire il cmdlet seguente:
    
        Get-CsSite
    
    Verrà restituito l'ID sito per il nome del sito in cui si sta creando il pool. Per informazioni dettagliate, vedere [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) nella documentazione di Lync Server 2013 Management Shell.

3.  Eseguire il seguente cmdlet:
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Per ulteriori informazioni, vedere [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) nella documentazione di Lync Server 2013 Management Shell.
    
    Il nome di dominio completo (FQDN) del server di Exchange deve essere configurato come nome oggetto (SN) del certificato Exchange OWA o come nome alternativo del soggetto (SAN).
    
    In Exchange OWA verificare anche che il nome FQDN del pool sia attendibile.
    
    <div>
    

    > [!IMPORTANT]  
    > Se il server CAS <EM>non</EM> è collocato nello stesso server in cui è in esecuzione la messaggistica unificata di Exchange 2013, ignorare i passaggi rimanenti di questa procedura ed eseguire la procedura "creare un'applicazione attendibile per il server CAS di Exchange 2013" più avanti in questo argomento. Se il server CAS è collocato nello stesso server in cui è in esecuzione la messaggistica unificata di Exchange 2013, completare i passaggi descritti in questa procedura e non eseguire la procedura "creare un'applicazione attendibile per il server CAS di Exchange 2013" più avanti in questo argomento.

    
    </div>

4.  Eseguire **Enable-CsTopology**.

5.  Aprire il Generatore di topologie e scaricare la topologia esistente.

6.  Nel riquadro di sinistra espandere l'albero finché non si raggiunge **Server applicazioni attendibili**.

7.  Espandere il nodo **Server applicazioni attendibili**.

8.  È ora necessario vedere il server CAS di Exchange 2013 elencato come server applicazioni attendibili.

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>Per creare un'applicazione attendibile per il server CAS di Exchange 2013

1.  Avviare Lync Server 2013 Management Shell.

2.  Se il server CAS *non* è collocato nello stesso server che esegue la messaggistica unificata di Exchange 2013, eseguire il cmdlet seguente:
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Per ulteriori informazioni, vedere l'argomento [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) nella documentazione di Lync Server 2013 Management Shell.

3.  Eseguire **Enable-CsTopology**.

4.  Nel riquadro di sinistra del Generatore di topologie espandere l'albero finché non si raggiunge **Server applicazioni attendibili**.

5.  Espandere il nodo **Server applicazioni attendibili**.

6.  È ora necessario vedere il server CAS di Exchange 2013 elencato come server applicazioni attendibili.

</div>

</div>

<span> </span>

</div>

</div>

</div>

