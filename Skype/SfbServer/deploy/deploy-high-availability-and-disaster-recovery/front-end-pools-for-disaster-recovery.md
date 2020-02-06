---
title: Distribuire pool Front End associati per il ripristino di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Si può decidere di usare i pool Front-End associati per ottenere protezione dal ripristino di emergenza, ma non è un requisito.
ms.openlocfilehash: 63b9c55aad2b31e01eec506ce28e54d2145ee636
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790084"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>Distribuire pool Front End associati per il ripristino di emergenza in Skype for Business Server
 
Si può decidere di usare i pool Front-End associati per ottenere protezione dal ripristino di emergenza, ma non è un requisito.
  
È possibile distribuire facilmente la topologia di ripristino di emergenza di pool Front-End associati usando generatore di topologie. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>Per distribuire una coppia di pool Front-End

1. Se i pool sono nuovi e non ancora definiti, usare generatore di topologie per creare i pool.
    
2. In Generatore di topologie fare clic con il pulsante destro del mouse su uno dei due pool e quindi scegliere **modifica proprietà**.
    
3. Fare clic su **resilienza** nel riquadro sinistro e quindi selezionare **pool di backup associato** nel riquadro destro.
    
4. Nella casella sotto il **pool di backup associato**selezionare il pool che si vuole associare al pool. Solo i pool esistenti che non sono già associati a un altro pool saranno disponibili per la selezione.
    
5. Selezionare **failover automatico e failback per la voce**e quindi fare clic su **OK**.
    
    Quando si visualizzano i dettagli su questo pool, il pool associato ora viene visualizzato nel riquadro destro in **resilienza**. 
    
6. USA generatore di topologia per pubblicare la topologia.
    
7. Se i due pool non sono stati ancora distribuiti, distribuirli ora e la configurazione verrà completata. È possibile ignorare i passaggi finali di questa procedura.
    
    Tuttavia, se i pool sono già stati distribuiti prima di definire la relazione associata, è necessario completare la procedura finale seguente.
    
8. In tutti i server front-end in entrambi i pool eseguire le operazioni seguenti:
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    In questo modo vengono configurati altri servizi necessari per il corretto funzionamento delle associazioni di backup.
    
9. Una volta completata l'installazione dei componenti necessari per l'associazione di backup in tutti i server front-end in entrambi i pool, assicurati di riapplicare tutti gli aggiornamenti cumulativi esistenti applicati in precedenza in questi server front-end in entrambi i pool e quindi continuare con il passaggio successivo.

10. Da un prompt dei comandi di Skype for Business Server Management Shell eseguire le operazioni seguenti: 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. Costringere i dati dell'utente e della conferenza di entrambi i pool a essere sincronizzati tra loro con i cmdlet seguenti:
    
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

> [!NOTE]
> L'opzione **failover automatico e il failback per la voce** e gli intervalli di tempo associati in Generatore di topologia si applicano solo alle caratteristiche di resilienza vocale introdotte in Lync Server. La selezione di questa opzione non implica che il failover del pool illustrato in questo documento sia automatico. Il failover del pool e il failback richiedono sempre che un amministratore richiami manualmente rispettivamente i cmdlet failover e failback.
  
## <a name="see-also"></a>Vedere anche

[Ripristino di emergenza del pool di front-end in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
