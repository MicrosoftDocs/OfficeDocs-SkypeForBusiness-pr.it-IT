---
title: 'Lync Server 2013: Distribuzione di pool Front End abbinati per il ripristino di emergenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d264128a7fef38fd220d2527772d6065dca7c964
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>Distribuzione di pool Front End abbinati per il ripristino di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

È possibile distribuire facilmente la topologia di ripristino di emergenza di pool Front-End associati usando generatore di topologie.

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>Per distribuire una coppia di pool Front-End

1.  Se i pool sono nuovi e non ancora definiti, usare generatore di topologie per creare i pool.

2.  In Generatore di topologie fare clic con il pulsante destro del mouse su uno dei due pool e quindi scegliere **modifica proprietà**.

3.  Fare clic su **resilienza** nel riquadro sinistro e quindi selezionare **pool di backup associato** nel riquadro destro.

4.  Nella casella sotto il **pool di backup associato**selezionare il pool che si vuole associare al pool. Solo i pool esistenti che non sono già associati a un altro pool saranno disponibili per la selezione.
    
    ![36080581-db76-497D-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497D-bf9e-f02b39574d0e")  

5.  Selezionare **failover automatico e failback per la voce**e quindi fare clic su **OK**.
    
    Quando si visualizzano i dettagli su questo pool, il pool associato ora viene visualizzato nel riquadro destro in **resilienza**.

6.  USA generatore di topologia per pubblicare la topologia.

7.  Se i due pool non sono stati ancora distribuiti, distribuirli ora e la configurazione verrà completata. È possibile ignorare i due passaggi finali descritti in questa procedura.
    
    Se tuttavia i pool sono già stati distribuiti prima di definire la relazione associata, è necessario completare i due passaggi finali seguenti.

8.  In tutti i server front-end in entrambi i pool eseguire le operazioni seguenti:
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    In questo modo vengono configurati altri servizi necessari per il corretto funzionamento delle associazioni di backup.

9.  Da un prompt dei comandi di Lync Server Management Shell eseguire le operazioni seguenti:
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. Costringere i dati dell'utente e della conferenza di entrambi i pool a essere sincronizzati tra loro, con i cmdlet seguenti:
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    La sincronizzazione dei dati può richiedere del tempo. Puoi usare i cmdlet seguenti per verificare lo stato. Verificare che lo stato in entrambe le direzioni sia in stato stabile.
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> L'opzione <STRONG>failover automatico e il failback per la voce</STRONG> e gli intervalli di tempo associati in Generatore di topologia si applicano solo alle caratteristiche di resilienza vocale introdotte in Lync Server 2010. La selezione di questa opzione non implica che il failover del pool illustrato in questo documento sia automatico. Il failover del pool e il failback richiedono sempre che un amministratore richiami manualmente rispettivamente i cmdlet failover e failback.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

