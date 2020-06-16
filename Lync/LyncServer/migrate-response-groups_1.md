---
title: Eseguire la migrazione di Response Group
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de012d0886c51cd70d5003beb24053ff86af05b7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Eseguire la migrazione di Response Group

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Dopo lo spostamento degli utenti nei pool di Lync Server 2013, è possibile eseguire la migrazione dei Response Group. La migrazione dei Response Group include i gruppi di agenti, le code, i flussi di lavoro e i file audio e lo spostamento degli oggetti contatto del gruppo di risposta dalla distribuzione legacy al pool di Lync Server 2013. Dopo aver eseguito la migrazione dei gruppi di risposta legacy, le chiamate ai Response Group vengono gestite dall'applicazione Response gruppo nel pool Lync Server 2013. Le chiamate ai Response Group non sono più gestite dal pool legacy.

<div>


> [!NOTE]  
> Anche se è possibile eseguire la migrazione dei Response Group prima di spostare tutti gli utenti nel pool di Lync Server 2013, è consigliabile spostare innanzitutto tutti gli utenti. In particolare, gli utenti che sono agenti di Response Group non disporranno di funzionalità complete di nuove funzionalità finché non verranno spostati nel pool di Lync Server 2013.



</div>

Prima di eseguire la migrazione dei Response Group, è necessario che sia stato distribuito un pool di Lync Server 2013 che includa l'applicazione del gruppo di risposta. L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale. È possibile verificare che l'applicazione Response Group sia installata eseguendo il cmdlet **Get-CsService – ApplicationServer** .

<div>


> [!NOTE]  
> È possibile creare nuovi gruppi di risposta di Lync Server 2013 nel pool Lync Server 2013 prima di eseguire la migrazione dei Response Group Legacy.



</div>

Per eseguire la migrazione dei Response Group da un pool legacy a Lync Server 2013, è necessario utilizzare il cmdlet **Move-CsRgsConfiguration** . Prima di poter eseguire **Move-CsRgsConfiguration**, è innanzitutto necessario installare il pacchetto di interfacce di compatibilità con le versioni precedenti di Strumentazione gestione Windows (WMI). Installare l'applicazione eseguendo OCSWMIBC.msi. È possibile trovare OCSWMIBC.msi nel supporto di installazione nella cartella Setup.

<div>


> [!IMPORTANT]  
> Il cmdlet Response Group Migration sposta la configurazione del Response Group per l'intero pool. Non è possibile selezionare gruppi, code o flussi di lavoro specifici di cui eseguire la migrazione.



</div>

Dopo aver eseguito la migrazione dei Response Group, è necessario aggiornare l'URL utilizzato dagli agenti formali per accedere ai propri Response Group e utilizzare il pannello di controllo di Lync Server o i cmdlet di Lync Server Management Shell per verificare che tutti i gruppi di agenti, le code e i flussi di lavoro siano stati spostati correttamente.

<div>


> [!WARNING]  
> Quando si esegue la migrazione dei Response Group, i Response Group di Office Communications Server 2007 R2 non vengono rimossi. Non rimuovere i Response Group di Office Communications Server 2007 R2. Se si rimuove un Response Group di Office Communications Server 2007 R2, i Response Group in Lync Server 2013 smettono di funzionare.



</div>

<div>


> [!IMPORTANT]  
> È consigliabile rimuovere i dati dalla distribuzione precedente solo dopo la rimozione del pool. È inoltre consigliabile esportare i Response Group subito dopo la migrazione. Se viene rimosso un Response Group di Office Communications Server 2007 R2, è possibile ripristinare i Response Group dal backup per ottenere i Response Group di Lync Server 2013 in esecuzione di nuovo.



</div>

Quando si esegue il cmdlet **Move-CsRgsConfiguration**, i gruppi di agenti, le code, i flussi di lavoro e i file audio rimangono nel pool legacy per consentirne il ripristino. Se occorre eseguire il ripristino dello stato precedente nel pool legacy, tuttavia, è necessario eseguire il cmdlet **Move-CsApplicationEndpoint** per rispostare gli oggetti contatto nel pool legacy.

<div>


> [!IMPORTANT]  
> È consigliabile eliminare eventuali dati dei Response Group nel pool legacy solo dopo la rimozione del pool.



</div>

La procedura seguente per la migrazione delle configurazioni dei Response Group presuppone che si disponga di una relazione uno-a-uno tra i pool legacy e i pool di Lync Server 2013. Se si prevede di consolidare o dividere i pool durante la migrazione e la distribuzione, è necessario pianificare la mappa del pool legacy al pool di Lync Server 2013.

<div>

## <a name="to-migrate-response-group-configurations"></a>Per eseguire la migrazione delle configurazioni di Response Group

1.  Individuare il file OCSWMIBC.msi nella cartella Setup dei supporti di installazione e installarlo.

2.  Accedere al computer con un account membro del gruppo RTCUniversalServerAdmins o con le autorizzazioni e i diritti di amministratore equivalenti.

3.  Aprire Lync Server Management Shell.

4.  Nella riga di comando digitare quanto segue:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Ad esempio:
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Se è stata distribuita la scheda Response Group per Microsoft Office Communicator 2007 R2 nell'ambiente Office Communications Server 2007 R2, rimuovere la scheda dal file di tabs.xml di Office Communicator 2007 R2.
    
    <div>
    

    > [!NOTE]  
    > Gli agenti formali utilizzavano la scheda Response Group per accedere ai Response Group in modo da poter ricevere le chiamate. Se è stata distribuita la scheda Response Group, si è scelto il percorso del file di tabs.xml di Office Communicator 2007 R2 quando è stata distribuita.

    
    </div>

6.  Fornire agli utenti l'URL aggiornato richiesto dagli agenti per l'accesso e la disconnessione dai Response Group.
    
    <div>
    

    > [!NOTE]  
    > L'URL in genere è la https://webpoolFQDN/RgsClients/Tab.aspx posizione in cui FQDNpoolWeb è il nome di dominio completo (FQDN) del pool Web associato al pool di cui è stata eseguita la migrazione in Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Questo passaggio non è necessario dopo che gli utenti eseguono l'aggiornamento a Lync 2013, poiché l'URL è disponibile dal menu <STRONG>strumenti</STRONG> in Lync.

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Per verificare la migrazione di Response Group tramite il pannello di controllo di Lync Server

1.  Aprire il Pannello di controllo di Lync Server.

2.  Nel riquadro di spostamento sinistro fare clic su **Response Group**.

3.  Nella scheda **flusso di lavoro** verificare che nell'elenco siano inclusi tutti i flussi di lavoro dell'ambiente Office Communications Server 2007 R2.

4.  Fare clic sulla scheda **coda** e verificare che nell'elenco siano incluse tutte le code dell'ambiente Office Communications Server 2007 R2.

5.  Fare clic sulla scheda **gruppo** e verificare che nell'elenco siano inclusi tutti i gruppi di agenti nell'ambiente Office Communications Server 2007 R2.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>Per verificare la migrazione dei Response Group tramite i cmdlet

1.  Aprire Lync Server Management Shell.
    
    Per informazioni dettagliate sui cmdlet seguenti, eseguire:
    
        Get-Help <cmdlet name> -Detailed

2.  Nella riga di comando digitare quanto segue:
    
        Get-CsRgsAgentGroup

3.  Verificare che nell'elenco siano inclusi tutti i gruppi di agenti nell'ambiente Office Communications Server 2007 R2.

4.  Nella riga di comando digitare quanto segue:
    
        Get-CsRgsQueue

5.  Verificare che nell'elenco siano incluse tutte le code dell'ambiente Office Communications Server 2007 R2.

6.  Nella riga di comando digitare quanto segue:
    
        Get-CsRgsWorkflow

7.  Verificare che nell'elenco siano inclusi tutti i flussi di lavoro nell'ambiente Office Communications Server 2007 R2.

</div>

</div>

<span> </span>

</div>

</div>

</div>

