---
title: Eseguire la migrazione di Response Group
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c01ec246ba99d2a2f71a16179d839409e6b57b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Eseguire la migrazione di Response Group

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Dopo lo spostamento degli utenti nei pool di Lync Server 2013, è possibile eseguire la migrazione dei gruppi di risposta. La migrazione dei gruppi di risposte include la copia di gruppi di agenti, code, flussi di lavoro e file audio e lo spostamento di oggetti contatto del gruppo di risposte dalla distribuzione legacy al pool di Lync Server 2013. Dopo la migrazione dei gruppi di risposta legacy, le chiamate ai gruppi di risposta vengono gestite dall'applicazione Response Group nel pool di Lync Server 2013. Le chiamate ai gruppi di risposte non vengono più gestite dal pool legacy.

<div>


> [!NOTE]  
> Anche se è possibile eseguire la migrazione di gruppi di risposte prima di spostare tutti gli utenti nel pool di Lync Server 2013, è consigliabile spostare prima tutti gli utenti. In particolare, gli utenti che sono agenti del gruppo di risposta non avranno la piena funzionalità delle nuove caratteristiche finché non verranno spostati nel pool di Lync Server 2013.



</div>

Prima di eseguire la migrazione dei gruppi di risposte, è necessario che sia stato implementato un pool di Lync Server 2013 che include l'applicazione Response Group. L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale. Puoi verificare che l'applicazione Response Group sia installata eseguendo il cmdlet **Get-CsService-ApplicationServer** .

<div>


> [!NOTE]  
> È possibile creare nuovi gruppi di risposta di Lync Server 2013 nel pool di Lync Server 2013 prima di eseguire la migrazione dei gruppi di risposta legacy.



</div>

Per eseguire la migrazione dei gruppi di risposte da un pool legacy a Lync Server 2013, è possibile usare il cmdlet **Move-CsRgsConfiguration** . Prima di poter eseguire **Move-CsRgsConfiguration**, devi prima installare il pacchetto di interfacce di compatibilità con le versioni precedenti di WMI (Windows Management Instrumentation). Installare questa applicazione eseguendo OCSWMIBC. msi. È possibile trovare OCSWMIBC. msi nel supporto di installazione nella cartella Setup.

<div>


> [!IMPORTANT]  
> Il cmdlet di migrazione del gruppo di risposte sposta la configurazione del gruppo di risposte per l'intero pool. Non è possibile selezionare gruppi, code o flussi di lavoro specifici per la migrazione.



</div>

Dopo la migrazione dei gruppi di risposta, è necessario aggiornare l'URL usato dagli agenti formali per accedere e disconnettersi dai gruppi di risposta e usare il pannello di controllo di Lync Server o i cmdlet di Lync Server Management Shell per verificare che tutti i gruppi di agenti, le code e i flussi di lavoro siano stati spostati correttamente.

<div>


> [!WARNING]  
> Quando si esegue la migrazione dei gruppi di risposte, i gruppi di risposta di Office Communications Server 2007 R2 non vengono rimossi. Non rimuovere i gruppi di risposta di Office Communications Server 2007 R2. Se si rimuove un gruppo di risposte di Office Communications Server 2007 R2, i gruppi di risposta in Lync Server 2013 smettono di funzionare.



</div>

<div>


> [!IMPORTANT]  
> È consigliabile non rimuovere i dati dalla distribuzione precedente fino a quando non si esegue la disattivazione del pool. Inoltre, ti consigliamo vivamente di esportare i Response Group subito dopo la migrazione. Se un gruppo di risposte di Office Communications Server 2007 R2 viene rimosso, è possibile ripristinare i gruppi di risposte dal backup per ottenere i gruppi di risposta di Lync Server 2013 in funzione.



</div>

Quando si esegue il cmdlet **Move-CsRgsConfiguration** , i gruppi di agenti, le code, i flussi di lavoro e i file audio rimangono nel pool legacy per scopi di rollback. Se si ha bisogno di eseguire il rollback al pool legacy, deve comunque essere eseguito il cmdlet **Move-CsApplicationEndpoint** per riportare gli oggetti di contatto nel pool legacy.

<div>


> [!IMPORTANT]  
> È consigliabile non eliminare i dati del gruppo di risposte dal pool legacy finché non si rimuove la Commissione dal pool.



</div>

La procedura seguente per la migrazione delle configurazioni di Response Group presuppone che si disponga di una relazione uno-a-uno tra i pool legacy e i pool di Lync Server 2013. Se si prevede di consolidare o suddividere i pool durante la migrazione e la distribuzione, è necessario pianificare le mappe del pool legacy a cui è associato il pool di Lync Server 2013.

<div>

## <a name="to-migrate-response-group-configurations"></a>Per eseguire la migrazione delle configurazioni di Response Group

1.  Individuare OCSWMIBC. msi nella cartella Setup del supporto di installazione e installarlo.

2.  Accedere al computer con un account che sia membro del gruppo RTCUniversalServerAdmins o disponga di diritti di amministratore e autorizzazioni equivalenti.

3.  Aprire Lync Server Management Shell.

4.  Nella riga di comando digitare quanto segue:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Ad esempio:
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Se è stata distribuita la scheda Response Group per Microsoft Office Communicator 2007 R2 nell'ambiente Office Communications Server 2007 R2, rimuovere la scheda dal file Tabs. XML di Office Communicator 2007 R2.
    
    <div>
    

    > [!NOTE]  
    > Gli agenti formali hanno usato la scheda Response Group per accedere ai loro Response Group prima che potessero ricevere chiamate. Se è stata distribuita la scheda Response Group, è stata selezionata la posizione del file Tabs. XML di Office Communicator 2007 R2 quando è stata distribuita.

    
    </div>

6.  Fornisci agli utenti l'URL aggiornato che gli agenti devono eseguire l'accesso e disconnettersi dai gruppi di risposta.
    
    <div>
    

    > [!NOTE]  
    > L'URL è in https://webpoolFQDN/RgsClients/Tab.aspxgenere, dove webpoolFQDN è il nome di dominio completo (FQDN) del pool Web associato al pool appena migrato a Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Questo passaggio non è necessario dopo che gli utenti hanno eseguito l'aggiornamento a Lync 2013 perché l'URL è disponibile dal menu <STRONG>strumenti</STRONG> in Lync.

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Per verificare la migrazione dei gruppi di risposte tramite il pannello di controllo di Lync Server

1.  Aprire il pannello di controllo di Lync Server.

2.  Nel riquadro di spostamento sinistro fare clic su **Response Groups**.

3.  Nella scheda **flusso di lavoro** verificare che tutti i flussi di lavoro nell'ambiente Office Communications Server 2007 R2 siano inclusi nell'elenco.

4.  Fare clic sulla scheda **coda** e verificare che tutte le code nell'ambiente Office Communications Server 2007 R2 siano incluse nell'elenco.

5.  Fare clic sulla scheda **gruppo** e verificare che tutti i gruppi di agenti nell'ambiente Office Communications Server 2007 R2 siano inclusi nell'elenco.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>Per verificare la migrazione dei gruppi di risposte tramite cmdlet

1.  Aprire Lync Server Management Shell.
    
    Per informazioni dettagliate sui cmdlet seguenti, eseguire:
    
        Get-Help <cmdlet name> -Detailed

2.  Nella riga di comando digitare quanto segue:
    
        Get-CsRgsAgentGroup

3.  Verificare che tutti i gruppi di agenti nell'ambiente Office Communications Server 2007 R2 siano inclusi nell'elenco.

4.  Nella riga di comando digitare quanto segue:
    
        Get-CsRgsQueue

5.  Verificare che tutte le code nell'ambiente Office Communications Server 2007 R2 siano incluse nell'elenco.

6.  Nella riga di comando digitare quanto segue:
    
        Get-CsRgsWorkflow

7.  Verificare che tutti i flussi di lavoro nell'ambiente Office Communications Server 2007 R2 siano inclusi nell'elenco.

</div>

</div>

<span> </span>

</div>

</div>

</div>

