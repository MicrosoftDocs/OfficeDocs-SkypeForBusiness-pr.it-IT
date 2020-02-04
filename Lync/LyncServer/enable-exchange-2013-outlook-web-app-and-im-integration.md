---
title: Abilitare l'integrazione di Outlook Web App e messaggistica istantanea di Exchange 2013
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
ms.openlocfilehash: 0bd9fb94dd0f068547819aa884b608ac6ddf7e39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723036"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Abilitare l'integrazione di Outlook Web App e messaggistica istantanea di Exchange 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Per abilitare l'integrazione di Outlook Web Access (OWA) e messaggistica istantanea di Exchange 2013 con Lync Server 2013, è necessario aggiungere il server di accesso client di Exchange 2013 Server (CAS) alla topologia di Lync Server 2013 come server applicazioni attendibile.

<div>

## <a name="to-create-a-trusted-application-pool"></a>Per creare un pool di applicazioni attendibili

1.  Avviare Lync Server 2013 Management Shell.

2.  Eseguire il cmdlet seguente:
    
        Get-CsSite
    
    Viene restituita la siteID per il nomesito in cui si sta creando il pool. Per informazioni dettagliate, vedere [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) nella documentazione di Lync Server 2013 Management Shell.

3.  Eseguire il cmdlet seguente:
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Per informazioni dettagliate, vedere [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) nella documentazione di Lync Server 2013 Management Shell.
    
    L'FQDN di Exchange Server deve essere configurato come nome soggetto del certificato OWA di Exchange (SN) o il nome alternativo soggetto (SAN).
    
    In Exchange OWA verificare che sia attendibile anche il nome di dominio completo del pool.
    
    <div>
    

    > [!IMPORTANT]  
    > Se il server CAS <EM>non</EM> è collocato nello stesso server in cui è in esecuzione la messaggistica unificata di Exchange 2013, ignorare i passaggi rimanenti di questa procedura ed eseguire la procedura "creare un'applicazione attendibile per il server CAS di Exchange 2013" più avanti in questo argomento. Se il server CAS è collocato nello stesso server in cui è in esecuzione la messaggistica unificata di Exchange 2013, completare i passaggi descritti in questa procedura e non eseguire la procedura "creare un'applicazione attendibile per il server CAS di Exchange 2013" più avanti in questo argomento.

    
    </div>

4.  Eseguire **Enable-CsTopology**.

5.  Aprire Generatore di topologia e scaricare la topologia esistente.

6.  Nel riquadro sinistro espandere l'albero fino a raggiungere i **server delle applicazioni attendibili**.

7.  Espandere il nodo **Trusted Application Servers** .

8.  È ora necessario vedere il server CAS di Exchange 2013 elencato come server delle applicazioni attendibile.

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>Per creare un'applicazione attendibile per il server CAS di Exchange 2013

1.  Avviare Lync Server 2013 Management Shell.

2.  Se il server CAS *non* è collocato nello stesso server in cui è in esecuzione la messaggistica unificata di Exchange 2013, eseguire il cmdlet seguente:
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Per informazioni dettagliate, vedere l'argomento [New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) nella documentazione di Lync Server 2013 Management Shell.

3.  Eseguire **Enable-CsTopology**.

4.  Nel riquadro sinistro di generatore di topologia espandere l'albero fino a raggiungere i **server delle applicazioni attendibili**.

5.  Espandere il nodo **Trusted Application Servers** .

6.  È ora necessario vedere il server CAS di Exchange 2013 elencato come server delle applicazioni attendibile.

</div>

</div>

<span> </span>

</div>

</div>

</div>

