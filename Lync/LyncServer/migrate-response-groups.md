---
title: Eseguire la migrazione di Response Group
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ef26b86b1de3fa7f9656cdb2ea82bb7a220948
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Eseguire la migrazione di Response Group

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-09-23_

Dopo lo spostamento degli utenti nei pool di Lync Server 2013, è possibile eseguire la migrazione dei gruppi di risposta. La migrazione dei gruppi di risposte include la copia di gruppi di agenti, code, flussi di lavoro, file audio e oggetti contatto del gruppo di risposte in spostamento dalla distribuzione legacy al pool di Lync Server 2013. Dopo la migrazione dei gruppi di risposta legacy, le chiamate ai gruppi di risposta vengono gestite dall'applicazione Response Group nel pool di Lync Server 2013. Le chiamate ai gruppi di risposte non vengono più gestite dal pool legacy.

<div>


> [!NOTE]  
> Anche se è possibile eseguire la migrazione di gruppi di risposte prima di spostare tutti gli utenti nel pool di Lync Server 2013, è consigliabile spostare prima tutti gli utenti. In particolare, gli utenti che sono agenti del gruppo di risposta non avranno la piena funzionalità delle nuove caratteristiche finché non verranno spostati nel pool di Lync Server 2013.



</div>

Prima di eseguire la migrazione dei gruppi di risposte, è necessario che sia stato implementato un pool di Lync Server 2013 che include l'applicazione Response Group. L'applicazione Response Group viene installata e attivata per impostazione predefinita quando si distribuisce VoIP aziendale. Puoi verificare che l'applicazione Response Group sia installata eseguendo il cmdlet **Get-CsService-ApplicationServer** .

<div>


> [!NOTE]  
> È possibile creare nuovi gruppi di risposta di Lync Server 2013 nel pool di Lync Server 2013 prima di eseguire la migrazione dei gruppi di risposta legacy.



</div>

Per eseguire la migrazione dei gruppi di risposte da un pool legacy a Lync Server 2013, è possibile usare il cmdlet **Move-CsRgsConfiguration** .

<div>


> [!IMPORTANT]  
> Il cmdlet di migrazione del gruppo di risposte sposta la configurazione del gruppo di risposte per l'intero pool. Non è possibile selezionare gruppi, code o flussi di lavoro specifici per la migrazione.



</div>

Dopo la migrazione dei gruppi di risposta, è necessario utilizzare il pannello di controllo di Lync Server o i cmdlet di Lync Server Management Shell per verificare che tutti i gruppi di agenti, le code e i flussi di lavoro siano stati spostati correttamente.

Quando si esegue la migrazione dei gruppi di risposte, i gruppi di risposta di Lync Server 2010 non vengono rimossi. Quando si gestiscono i gruppi di risposta dopo la migrazione tramite il pannello di controllo di Lync Server o Lync Server Management Shell, è possibile visualizzare i gruppi di risposta di Lync Server 2010 e i gruppi di risposta di Lync Server 2013. È consigliabile applicare gli aggiornamenti solo ai gruppi di risposta di Lync Server 2013. I gruppi di risposte di Lync Server 2010 vengono mantenuti solo per scopi di rollback.

<div>


> [!WARNING]  
> Dopo aver completato la migrazione e creato i nuovi gruppi di risposta, il pannello di controllo di Lync Server e Lync Server Management Shell visualizzeranno le versioni Lync Server 2010 e Lync Server 2013 di ogni gruppo di risposte. Non usare il pannello di controllo di Lync Server o Lync Server Management Shell per rimuovere i gruppi di risposta di Lync Server 2010. Se si rimuove uno, il gruppo di risposte corrispondente creato durante la migrazione smetterà di funzionare. I gruppi di risposta di Lync Server 2010 verranno rimossi quando si decommissionerà il pool di Lync Server 2010.



</div>

<div>


> [!IMPORTANT]  
> È consigliabile non rimuovere i dati dalla distribuzione precedente fino a quando non si esegue la disattivazione del pool. Inoltre, ti consigliamo vivamente di esportare i Response Group subito dopo la migrazione. Se un gruppo di risposte di Lync Server 2010 deve essere rimosso, è possibile ripristinare i gruppi di risposte dal backup per ottenere i gruppi di risposta di Lync Server 2013 in funzione.



</div>

Lync Server 2013 introduce una nuova funzionalità del gruppo di risposte denominata **tipo di flusso di lavoro**. Il **tipo di flusso di lavoro** può essere **gestito** o **non gestito**. Tutti i gruppi di risposte vengono migrati con il **tipo di flusso di lavoro** impostato su **non gestito** e con un elenco di gestione vuoto.

Quando si esegue il cmdlet **Move-CsRgsConfiguration** , i gruppi di agenti, le code, i flussi di lavoro e i file audio rimangono nel pool legacy per scopi di rollback. Se si ha bisogno di eseguire il rollback al pool legacy, deve comunque essere eseguito il cmdlet **Move-CsApplicationEndpoint** per riportare gli oggetti di contatto nel pool legacy.

La procedura seguente per la migrazione delle configurazioni di Response Group presuppone che si disponga di una relazione uno-a-uno tra i pool legacy e i pool di Lync Server 2013. Se si prevede di consolidare o suddividere i pool durante la migrazione e la distribuzione, è necessario pianificare le mappe del pool legacy a cui è associato il pool di Lync Server 2013.

<div>

## <a name="to-migrate-response-group-configurations"></a>Per eseguire la migrazione delle configurazioni di Response Group

1.  Accedere al computer con un account che sia membro del gruppo RTCUniversalServerAdmins o disponga di diritti di amministratore e autorizzazioni equivalenti.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Eseguire
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Ad esempio:
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  Dopo la migrazione di gruppi di risposte e agenti al pool di Lync Server 2013, l'URL usato dagli agenti per accedere e disconnettersi è un URL di Lync Server 2013 ed è disponibile nel menu **strumenti** . Ricorda agli agenti di aggiornare tutti i riferimenti, ad esempio i segnalibri, al nuovo URL.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>Per verificare la migrazione dei gruppi di risposte tramite il pannello di controllo di Lync Server

1.  Accedere al computer con un account che è un membro del gruppo RTCUniversalReadOnlyAdmins o è minimamente un membro del ruolo CsViewOnlyAdministrator.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nel riquadro di spostamento sinistro fare clic su **Response Groups**.

4.  Nella scheda **flusso di lavoro** verificare che tutti i flussi di lavoro nell'ambiente Lync Server 2010 siano inclusi nell'elenco.

5.  Fare clic sulla scheda **coda** e verificare che tutte le code nell'ambiente Lync Server 2010 siano incluse nell'elenco.

6.  Fare clic sulla scheda **gruppo** e verificare che tutti i gruppi di agenti nell'ambiente Lync Server 2010 siano inclusi nell'elenco.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a>Per verificare la migrazione dei gruppi di risposte tramite Lync Server Management Shell

1.  Accedere al computer con un account che è un membro del gruppo RTCUniversalReadOnlyAdmins o è minimamente un membro del ruolo CsViewOnlyAdministrator.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.
    
    Per informazioni dettagliate sui cmdlet seguenti, eseguire:
    
        Get-Help <cmdlet name> -Detailed

3.  Eseguire
    
        Get-CsRgsAgentGroup

4.  Verificare che tutti i gruppi di agenti nell'ambiente Lync Server 2010 siano inclusi nell'elenco.

5.  Eseguire
    
        Get-CsRgsQueue

6.  Verificare che tutte le code nell'ambiente Lync Server 2010 siano incluse nell'elenco.

7.  Eseguire
    
        Get-CsRgsWorkflow

8.  Verificare che tutti i flussi di lavoro nell'ambiente Lync Server 2010 siano inclusi nell'elenco.

</div>

</div>

<span> </span>

</div>

</div>

</div>

