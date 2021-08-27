---
title: Spostare più utenti nel pool pilota
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: È possibile spostare più utenti dal pool legacy al pool pilota di Skype for Business Server 2019 utilizzando il Pannello di controllo di Skype for Business Server 2019 o Skype for Business Server 2019 Management Shell.
ms.openlocfilehash: 50525ce139cb324d71ebcdce54ef96463dc933b5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624578"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Spostare più utenti nel pool pilota

È possibile spostare più utenti dal pool legacy al pool pilota di Skype for Business Server 2019 utilizzando il Pannello di controllo di Skype for Business Server 2019 o Skype for Business Server 2019 Management Shell.

 **In questo articolo**
  
[Per spostare più utenti tramite il Pannello di controllo Skype for Business Server 2019](#sectionSection0)
  
[Per spostare più utenti tramite Skype for Business Server 2019 Management Shell](#sectionSection1)
  
[Per spostare tutti gli utenti contemporaneamente utilizzando Skype for Business Server 2019 Management Shell](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Per spostare più utenti tramite il Pannello di controllo Skype for Business Server 2019
<a name="sectionSection0"> </a>

1. Aprire Skype for Business Server Pannello di controllo.
    
2. Fare **clic su** Utenti, su **Cerca** e quindi su **Trova.**
    
3. Selezionare due utenti che si desidera spostare nel pool Skype for Business Server 2019. In questo esempio spostiamo gli utenti Chen Yang e Claus Hansen.
    
     ![Spostare gli utenti in un pool di registrazione specifico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.
    
5. Nell'elenco a discesa selezionare il pool Skype for Business Server 2019.
    
6. Fare clic su **Azione** e quindi su **Sposta utenti selezionati nel pool**. Fare clic su **OK**.
    
     ![Finestra di dialogo Sposta utenti, pool di registrazione di destinazione](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Verificare che la colonna **Pool** di registrazione per gli utenti contenga ora il pool Skype for Business Server 2019, che indica che gli utenti sono stati spostati correttamente. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Per spostare più utenti tramite Skype for Business Server 2019 Management Shell
<a name="sectionSection1"> </a>

1. Aprire la Skype for Business Server 2019 Management Shell. 
    
2. Nella riga di comando digitare il comando seguente e sostituire **User1** e **User2** con nomi utente specifici che si desidera spostare e sostituire **pool_FQDN** con il nome del pool di destinazione. In questo esempio spostiamo gli utenti Hao Chen e Katie Jordan. 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Esempio di cmdlet powershell Get-CsUser](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Nella riga di comando digitare quanto segue: 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. L'identità del **pool di registrazione** deve ora puntare al pool specificato come **pool_FQDN** nel passaggio precedente. La presenza di questa identità conferma che l'utente è stato correttamente spostato. Ripetere il passaggio per verificare **che User2** sia stato spostato. 
    
     ![Output del cmdlet PowerShell Get-UsUser -Identity](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Per spostare tutti gli utenti contemporaneamente tramite Skype for Business Server 2019 Management Shell
<a name="sectionSection2"> </a>

In questo esempio, tutti gli utenti sono stati restituiti al pool legacy (pool01.contoso.net). Utilizzando Skype for Business Server 2019 Management Shell, tutti gli utenti verranno spostati contemporaneamente nel pool di Skype for Business Server 2019 (pool02.contoso.net).
  
1. Aprire la Skype for Business Server 2019 Management Shell.
    
2. Nella riga di comando digitare quanto segue: 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet di PowerShell e risultati in Management Shell](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Eseguire **Get-CsUser** per uno degli utenti pilota. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. **L'identità del pool** di registrazione per ogni utente ora punta al pool specificato come **pool_FQDN** nel passaggio precedente. La presenza di questa identità conferma che l'utente è stato spostato correttamente. 
    
5. Inoltre, è possibile visualizzare l'elenco degli utenti nel Pannello di controllo di Skype for Business Server 2019 e verificare che il valore del pool di registrazione punti ora al pool di Skype for Business Server 2019.
    
     ![Skype for Business Server utente del Pannello di controllo 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

