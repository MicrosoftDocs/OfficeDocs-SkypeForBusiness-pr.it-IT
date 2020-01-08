---
title: 'Lync Server 2013: distribuire lo strumento SEFAUtil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0783ab251359582d232d558da2161a149dea5117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Distribuire lo strumento SEFAUtil in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-30_

Per distribuire e gestire il ritiro delle chiamate di gruppo, è necessario usare lo strumento SEFAUtil Resource Kit. Lo strumento fa parte degli strumenti di Lync Server 2013 Resource Kit. Prima di poter installare SEFAUtil, è necessario disporre di un pool di applicazioni attendibili nella topologia, specificare SEFAUtil come applicazione attendibile e abilitare la topologia.

<div>


> [!IMPORTANT]  
> Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK deve essere installato in qualsiasi computer in cui si prevede di eseguire lo strumento SEFAUtil.



</div>

È possibile eseguire SEFAUtil in qualsiasi pool Front-end della distribuzione.

<div>


> [!NOTE]  
> Per altre informazioni sull'uso di SEFAUtil, vedere l'articolo del Blog di TechNet "come ottenere SEFAutil in corso?" at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.



</div>

<div>

## <a name="to-deploy-sefautil"></a>Per distribuire SEFAUtil

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibile. Se necessario, definire un pool di applicazioni attendibili per il pool Front-end in cui si prevede di eseguire SEFAUtil. Nella riga di comando eseguire:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Definire lo strumento SEFAUtil come applicazione attendibile. Nella riga di comando eseguire:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Se necessario, è possibile usare una porta diversa.

    
    </div>

5.  Abilitare la topologia con le modifiche apportate. Nella riga di comando eseguire:
    
        Enable-CsTopology

6.  Installare gli strumenti del Resource Kit di Lync Server 2013 in un server front-end che si trova nel pool di applicazioni attendibile creato nel passaggio 3.

7.  Verificare che lo strumento SEFAUtil sia in uso correttamente, come indicato di seguito:
    
    1.  Eseguire lo strumento dal prompt dei comandi di Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.
        
        <div>
        

        > [!NOTE]  
        > Lo strumento si trova nella cartella \Programmi\microsoft Lync Server 2013 \ reskit.

        
        </div>
    
    2.  Visualizzare le impostazioni di inoltro di chiamata di un utente. Nella riga di comando eseguire:
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        Verranno visualizzate le impostazioni di inoltro di chiamata per l'utente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

