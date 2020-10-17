---
title: Eseguire la migrazione di Response Group
description: Eseguire la migrazione di Response Group.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19da4d39b6f11931bffb5a6e422c2826e7351d69
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570322"
---
# <a name="migrate-response-groups"></a>Eseguire la migrazione di Response Group

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-09-23_

Dopo lo spostamento degli utenti nei pool di Lync Server 2013, è possibile eseguire la migrazione dei Response Group. La migrazione dei Response Group include i gruppi di agenti di copia, le code, i flussi di lavoro, i file audio e gli oggetti contatto del gruppo di risposta in movimento dalla distribuzione legacy al pool di Lync Server 2013. Dopo aver eseguito la migrazione dei gruppi di risposta legacy, le chiamate ai Response Group vengono gestite dall'applicazione Response gruppo nel pool Lync Server 2013. Le chiamate ai Response Group non sono più gestite dal pool legacy.

<div>


> [!NOTE]  
> Anche se è possibile eseguire la migrazione dei Response Group prima di spostare tutti gli utenti nel pool di Lync Server 2013, è consigliabile spostare innanzitutto tutti gli utenti. In particolare, gli utenti che sono agenti di Response Group non disporranno di funzionalità complete di nuove funzionalità finché non verranno spostati nel pool di Lync Server 2013.



</div>

Prima di eseguire la migrazione dei Response Group, è necessario che sia stato distribuito un pool di Lync Server 2013 che includa l'applicazione del gruppo di risposta. L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale. È possibile verificare che l'applicazione Response Group sia installata eseguendo il cmdlet **Get-CsService – ApplicationServer** .

<div>


> [!NOTE]  
> È possibile creare nuovi gruppi di risposta di Lync Server 2013 nel pool Lync Server 2013 prima di eseguire la migrazione dei Response Group Legacy.



</div>

Per eseguire la migrazione dei Response Group da un pool legacy a Lync Server 2013, è necessario utilizzare il cmdlet **Move-CsRgsConfiguration** .

<div>


> [!IMPORTANT]  
> Il cmdlet Response Group Migration sposta la configurazione del Response Group per l'intero pool. Non è possibile selezionare gruppi, code o flussi di lavoro specifici di cui eseguire la migrazione.



</div>

Dopo aver eseguito la migrazione dei Response Group, è necessario utilizzare il pannello di controllo di Lync Server o i cmdlet di Lync Server Management Shell per verificare che tutti i gruppi di agenti, le code e i flussi di lavoro siano stati spostati correttamente.

Quando si esegue la migrazione dei Response Group, i Response Group di Lync Server 2010 non vengono rimossi. Quando si gestiscono i Response Group dopo la migrazione utilizzando il pannello di controllo di Lync Server o Lync Server Management Shell, è possibile visualizzare entrambi i Response Group di Lync Server 2010 e i Response Group di Lync Server 2013. È consigliabile applicare gli aggiornamenti solo ai Response Group di Lync Server 2013. I Response Group di Lync Server 2010 vengono mantenuti solo per scopi di rollback.

<div>


> [!WARNING]  
> Dopo che la migrazione è stata completata e che sono stati creati i nuovi Response Group, il pannello di controllo di Lync Server e Lync Server Management Shell visualizzeranno le versioni di Lync Server 2010 e Lync Server 2013 di ogni Response Group. Non utilizzare il pannello di controllo di Lync Server o Lync Server Management Shell per rimuovere i Response Group di Lync Server 2010. Se si rimuove uno, il Response Group corrispondente che è stato creato durante la migrazione smetterà di funzionare. I Response Group di Lync Server 2010 verranno rimossi quando si rimuove la Commissione del pool di Lync Server 2010.



</div>

<div>


> [!IMPORTANT]  
> È consigliabile rimuovere i dati dalla distribuzione precedente solo dopo la rimozione del pool. È inoltre consigliabile esportare i Response Group subito dopo la migrazione. Se un Response Group di Lync Server 2010 deve essere rimosso, è possibile ripristinare i Response Group dal backup per ottenere i Response Group di Lync Server 2013 in esecuzione di nuovo.



</div>

Lync Server 2013 introduce una nuova funzionalità Response Group denominata **tipo di flusso di lavoro**. Il **Tipo di flusso di lavoro** può essere **Gestito** o **Non gestito**. Tutti i Response Group vengono migrati con il **Tipo di flusso di lavoro** impostato su **Non gestito** e con un elenco di responsabili vuoto.

Quando si esegue il cmdlet **Move-CsRgsConfiguration**, i gruppi di agenti, le code, i flussi di lavoro e i file audio rimangono nel pool legacy per consentirne il ripristino. Se occorre eseguire il rollback dello stato precedente nel pool legacy, tuttavia, è necessario eseguire il cmdlet **Move-CsApplicationEndpoint** per rispostare gli oggetti contatto nel pool legacy.

La procedura seguente per eseguire la migrazione delle configurazioni di Response Group presuppone che si disponga di una relazione uno-a-uno tra i pool legacy e i pool di Lync Server 2013. Se si prevede di consolidare o dividere i pool durante la migrazione e la distribuzione, è necessario pianificare la mappa del pool legacy al pool di Lync Server 2013.

<div>

## <a name="to-migrate-response-group-configurations"></a>Per eseguire la migrazione delle configurazioni di Response Group

1.  Accedere al computer con un account membro del gruppo RTCUniversalServerAdmins o con le autorizzazioni e i diritti di amministratore equivalenti.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Eseguire: 
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Ad esempio:
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  Dopo aver eseguito la migrazione di Response Group e agenti nel pool di Lync Server 2013, l'URL utilizzato dagli agenti per accedere e disconnettersi è un URL di Lync Server 2013 ed è disponibile dal menu **strumenti** . Ricordare agli agenti di aggiornare eventuali riferimenti, come segnalibri, al nuovo URL.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Per verificare la migrazione di Response Group tramite il Pannello di controllo di Lync Server

1.  Eseguire l'accesso al computer con un account membro del gruppo RTCUniversalReadOnlyAdmins o come minimo membro del ruolo CsViewOnlyAdministrator.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nel riquadro di spostamento sinistro fare clic su **Response Group**.

4.  Nella scheda **flusso di lavoro** verificare che nell'elenco siano inclusi tutti i flussi di lavoro dell'ambiente Lync Server 2010.

5.  Fare clic sulla scheda **coda** e verificare che nell'elenco siano incluse tutte le code dell'ambiente Lync Server 2010.

6.  Fare clic sulla scheda **gruppo** e verificare che nell'elenco siano inclusi tutti i gruppi di agenti nell'ambiente Lync Server 2010.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>Per verificare la migrazione di Response Group tramite Lync Server Management Shell

1.  Eseguire l'accesso al computer con un account membro del gruppo RTCUniversalReadOnlyAdmins o come minimo membro del ruolo CsViewOnlyAdministrator.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.
    
    Per informazioni dettagliate sui cmdlet seguenti, eseguire:
    
        Get-Help <cmdlet name> -Detailed

3.  Eseguire: 
    
        Get-CsRgsAgentGroup

4.  Verificare che nell'elenco siano inclusi tutti i gruppi di agenti nell'ambiente Lync Server 2010.

5.  Eseguire: 
    
        Get-CsRgsQueue

6.  Verificare che nell'elenco siano incluse tutte le code dell'ambiente Lync Server 2010.

7.  Eseguire: 
    
        Get-CsRgsWorkflow

8.  Verificare che nell'elenco siano inclusi tutti i flussi di lavoro dell'ambiente Lync Server 2010.

</div>

</div>

<span> </span>

</div>

</div>

</div>

