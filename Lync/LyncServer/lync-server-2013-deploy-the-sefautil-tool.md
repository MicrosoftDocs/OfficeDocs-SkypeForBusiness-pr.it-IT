---
title: 'Lync Server 2013: distribuire lo strumento SEFAUtil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91392470d47cc4d59130e7c304656f9eee48ae5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531373"
---
# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Distribuire lo strumento SEFAUtil in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-30_

Per distribuire e gestire il prelievo delle chiamate di gruppo, è necessario utilizzare lo strumento SEFAUtil Resource Kit. Lo strumento fa parte degli strumenti di Lync Server 2013 Resource Kit. Prima di poter installare SEFAUtil, è necessario disporre di un pool di applicazioni attendibili nella topologia, specificare SEFAUtil come applicazione attendibile e abilitare la topologia.

<div>


> [!IMPORTANT]  
> Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK deve essere installato in tutti i computer in cui si prevede di eseguire lo strumento SEFAUtil.



</div>

È possibile eseguire la SEFAUtil in qualsiasi pool Front end della distribuzione.

<div>


> [!NOTE]  
> Per ulteriori informazioni sull'esecuzione di SEFAUtil, vedere l'articolo del Blog di TechNet, "How to get SEFAutil running?" in <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A> .



</div>

<div>

## <a name="to-deploy-sefautil"></a>Per distribuire SEFAUtil

1.  Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibili. Se necessario, definire un pool di applicazioni attendibili per il pool Front end in cui si prevede di eseguire SEFAUtil. Nella riga di comando digitare il comando seguente:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  Definire lo strumento SEFAUtil come applicazione attendibile. Nella riga di comando digitare il comando seguente:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Se necessario, è possibile utilizzare una porta diversa.

    
    </div>

5.  Abilitare la topologia con le modifiche apportate. Nella riga di comando digitare il comando seguente:
    
        Enable-CsTopology

6.  Installare gli strumenti di Lync Server 2013 Resource Kit in un front end server che si trova nel pool di applicazioni attendibili creato nel passaggio 3.

7.  Verificare che lo strumento SEFAUtil sia in esecuzione correttamente, come indicato di seguito:
    
    1.  Eseguire lo strumento dal prompt dei comandi di Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.
        
        <div>
        

        > [!NOTE]  
        > Lo strumento si trova nella cartella \Programmi\microsoft Lync Server 2013 \ reskit.

        
        </div>
    
    2.  Visualizzare le impostazioni di inoltro di chiamata di un utente. Nella riga di comando digitare il comando seguente:
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        Verranno visualizzate le impostazioni di inoltro di chiamata per l'utente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

