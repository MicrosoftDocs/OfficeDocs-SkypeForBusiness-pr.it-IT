---
title: 'Lync Server 2013: distribuzione di pool Front End abbinati per il ripristino di emergenza'
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
ms.openlocfilehash: a18b92dde9b6ca48ffe8912f216331c39ef9cc9d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>Distribuzione di pool Front End abbinati per il ripristino di emergenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

È possibile distribuire facilmente la topologia di ripristino di emergenza dei pool Front End associati utilizzando Generatore di topologie.

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>Per distribuire una coppia di pool Front End

1.  Se i pool sono nuovi e non ancora definiti, utilizzare Generatore di topologie per creare i pool.

2.  In Generatore di topologie fare clic con il pulsante destro del mouse su uno dei due pool e quindi scegliere **modifica proprietà**.

3.  Fare clic su **Resilienza** nel riquadro a sinistra e selezionare **Pool di backup associato** nel riquadro a destra.

4.  Nella casella sotto **Pool di backup associato** selezionare il pool da accoppiare a questo pool. Sarà possibile selezionare solo pool esistenti che non sono già accoppiati con un altro pool.
    
    ![36080581-db76-497D-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497D-bf9e-f02b39574d0e")  

5.  Selezionare **Failover e failback automatico per VoIP** e quindi fare clic su **OK**.
    
    Quando vengono visualizzati i dettagli su questo pool, il pool associato apparirà nel riquadro a destra sotto **Resilienza**.

6.  Utilizzare Generatore di topologie per pubblicare la topologia.

7.  Se i due pool non sono stati ancora distribuiti, distribuirli ora in modo da completare la configurazione. È possibile ignorare i due passaggi finali di questa procedura.
    
    Tuttavia, se i pool erano già distribuiti prima che venisse definita la relazione accoppiata, è necessario completare i due passaggi finali che seguono.

8.  Su ogni Front End Server in entrambi i pool eseguire:
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    Consente di configurare altri servizi necessari per il corretto funzionamento dell'accoppiamento di backup.

9.  Da un prompt dei comandi di Lync Server Management Shell, eseguire le operazioni seguenti:
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. Forzare la sincronizzazione dei dati utente e di conferenza di entrambi i pool specificando i cmdlet seguenti:
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    La sincronizzazione dei dati potrebbe richiedere alcuni minuti. Per controllare lo stato è possibile usare i cmdlet seguenti. Assicurarsi che lo stato di entrambe le direzioni sia in stato stazionario.
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> L'opzione <STRONG>failover automatico e failback per la voce</STRONG> e gli intervalli di tempo associati in Generatore di topologie si applicano solo alle funzionalità di resilienza vocale introdotte in Lync Server 2010. La selezione di questa opzione non implica che il failover del pool descritto in questo documento sia automatico. Il failover e il failback del pool richiedono sempre che un amministratore richiami manualmente i cmdlet di failover e di failback, rispettivamente.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

