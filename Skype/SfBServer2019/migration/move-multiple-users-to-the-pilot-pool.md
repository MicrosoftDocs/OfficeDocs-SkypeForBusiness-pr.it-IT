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
localization_priority: Normal
description: È possibile spostare più utenti dal pool legacy al pool pilota di Skype for Business Server 2019 utilizzando il pannello di controllo di Skype for Business Server 2019 o Skype for Business Server 2019 Management Shell.
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753428"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Spostare più utenti nel pool pilota

È possibile spostare più utenti dal pool legacy al pool pilota di Skype for Business Server 2019 utilizzando il pannello di controllo di Skype for Business Server 2019 o Skype for Business Server 2019 Management Shell.

 **In questo articolo**
  
[Per spostare più utenti utilizzando il pannello di controllo di Skype for Business Server 2019](#sectionSection0)
  
[Per spostare più utenti tramite la shell di gestione di Skype for Business Server 2019](#sectionSection1)
  
[Per spostare tutti gli utenti contemporaneamente tramite la shell di gestione di Skype for Business Server 2019](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Per spostare più utenti utilizzando il pannello di controllo di Skype for Business Server 2019
<a name="sectionSection0"> </a>

1. Aprire il pannello di controllo di Skype for Business Server.
    
2. Fare clic su **utenti**, fare clic su **Cerca**e quindi su **trova**.
    
3. Selezionare due utenti che si desidera spostare nel pool di Skype for Business Server 2019. In questo esempio spostiamo gli utenti Chen Yang e Claus Hansen.
    
     ![Spostare gli utenti in un pool di registri specifico](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.
    
5. Nell'elenco a discesa selezionare il pool di Skype for Business Server 2019.
    
6. Fare clic su **Azione** e quindi su **Sposta utenti selezionati nel pool**. Fare clic su **OK**.
    
     ![Finestra di dialogo Sposta utenti, pool di registrazione di destinazione](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Verificare che la colonna **pool di registrazione** per gli utenti contenga ora il pool di Skype for Business Server 2019, che indica che gli utenti sono stati spostati correttamente. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Per spostare più utenti tramite la shell di gestione di Skype for Business Server 2019
<a name="sectionSection1"> </a>

1. Aprire la shell di gestione di Skype for Business Server 2019. 
    
2. Nella riga di comando digitare quanto segue e sostituire **User1** e **User2** con nomi utente specifici che si desidera spostare e sostituire **pool_FQDN** con il nome del pool di destinazione. In questo esempio spostiamo gli utenti Hao Chen e Katie Jordan. 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Esempio di cmdlet Get-CsUser di PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Nella riga di comando digitare quanto segue: 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. L'identità del **pool di registrazione** deve ora puntare al pool specificato come **pool_FQDN** nel passaggio precedente. La presenza di questa identità conferma che l'utente è stato correttamente spostato. Ripetere il passaggio per verificare che **User2** sia stato spostato. 
    
     ![Output del cmdlet Get-UsUser-Identity di PowerShell](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Per spostare tutti gli utenti contemporaneamente tramite la shell di gestione di Skype for Business Server 2019
<a name="sectionSection2"> </a>

In questo esempio, tutti gli utenti sono stati restituiti al pool legacy (pool01.contoso.net). Usando la shell di gestione di Skype for Business Server 2019, tutti gli utenti verranno spostati contemporaneamente sul pool Skype for Business Server 2019 (pool02.contoso.net).
  
1. Aprire la shell di gestione di Skype for Business Server 2019.
    
2. Nella riga di comando digitare quanto segue: 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet di PowerShell e risultati in Management Shell](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Eseguire **Get-CsUser** per uno degli utenti pilota. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. L'identità del **pool di registrazione** per ogni utente ora punta al pool specificato come **pool_FQDN** nel passaggio precedente. La presenza di questa identità conferma che l'utente è stato spostato correttamente. 
    
5. Inoltre, è possibile visualizzare l'elenco degli utenti nel pannello di controllo di Skype for Business Server 2019 e verificare che il valore del pool di registrazione punti ora al pool di Skype for Business Server 2019.
    
     ![Elenco utenti del pannello di controllo di Skype for Business Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

