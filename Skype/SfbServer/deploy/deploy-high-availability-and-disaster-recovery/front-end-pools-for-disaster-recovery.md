---
title: Distribuire pool Front End abbinati per il ripristino di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: È possibile decidere di utilizzare pool Front End abbinati per fornire protezione da ripristino di emergenza, ma non è un requisito.
ms.openlocfilehash: 7d066de60bf3ab98d73d8aeee08044803fad983c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830606"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>Distribuire pool Front End abbinati per il ripristino di emergenza in Skype for Business Server
 
È possibile decidere di utilizzare pool Front End abbinati per fornire protezione da ripristino di emergenza, ma non è un requisito.
  
È possibile distribuire facilmente la topologia di ripristino di emergenza di pool Front End abbinati utilizzando Generatore di topologie. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>Per distribuire una coppia di pool Front End

1. Se i pool sono nuovi e non ancora definiti, utilizzare Generatore di topologie per creare i pool.
    
2. In Generatore di topologie fare clic con il pulsante destro del mouse su uno dei due pool e quindi **scegliere Modifica proprietà.**
    
3. Fare clic su **Resilienza** nel riquadro a sinistra e selezionare **Pool di backup associato** nel riquadro a destra.
    
4. Nella casella sotto **Pool di backup associato** selezionare il pool da accoppiare a questo pool. Sarà possibile selezionare solo pool esistenti che non sono già accoppiati con un altro pool.
    
5. Selezionare **Failover e failback automatico per VoIP** e quindi fare clic su **OK**.
    
    Quando vengono visualizzati i dettagli su questo pool, il pool associato apparirà nel riquadro a destra sotto **Resilienza**. 
    
6. Utilizzare Generatore di topologie per pubblicare la topologia.
    
7. Se i due pool non sono stati ancora distribuiti, distribuirli ora in modo da completare la configurazione. È possibile ignorare i passaggi finali di questa procedura.
    
    Tuttavia, se i pool sono già stati distribuiti prima di definire la relazione associata, è necessario completare i passaggi finali seguenti.
    
8. Su ogni Front End Server in entrambi i pool eseguire:
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    Consente di configurare altri servizi necessari per il corretto funzionamento dell'accoppiamento di backup.
    
9. Al termine dell'installazione dei componenti necessari per l'associazione di backup in ogni Front End Server in entrambi i pool, assicurarsi di ri applicare nuovamente qualsiasi aggiornamento cumulativo esistente applicato in precedenza in questi Front End Server in entrambi i pool e quindi continuare con il passaggio successivo.

10. Da un prompt dei comandi di Skype for Business Server Management Shell, eseguire le operazioni seguenti: 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. Forzare la sincronizzazione tra l'utente e i dati delle conferenze di entrambi i pool con i cmdlet seguenti:
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    La sincronizzazione dei dati potrebbe richiedere alcuni minuti. Per controllare lo stato è possibile usare i cmdlet seguenti. Assicurati che lo stato in entrambe le direzioni sia stabile.
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> L'opzione failover e **failback** automatici per VoIP e gli intervalli di tempo associati in Generatore di topologie si applicano solo alle funzionalità di resilienza vocale introdotte in Lync Server. La selezione di questa opzione non implica che il failover del pool descritto in questo documento sia automatico. Il failover e il failback del pool richiedono sempre che un amministratore richiami manualmente i cmdlet di failover e di failback, rispettivamente.
  
## <a name="see-also"></a>Vedere anche

[Ripristino di emergenza del pool Front End in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
