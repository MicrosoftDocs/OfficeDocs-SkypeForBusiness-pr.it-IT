---
title: Trasferire un singolo utente nel pool pilota
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: È possibile trasferire un utente dal pool legacy al pool pilota di Skype for Business Server 2019 usando il pannello di controllo di Skype for Business Server 2019 o Skype for Business Server 2019 Management Shell. Nell'esempio seguente, nella colonna del pool di registrazione, pool01.contoso.net è il pool legacy e tutti e sei di questi utenti sono connessi al pool. Usare le procedure seguenti per trasferire un utente nel pool di Skype for Business Server 2019 usando il pannello di controllo di Skype for Business Server 2019 e Skype for Business Server Management Shell.
ms.openlocfilehash: cc8c657b5e8d9cea760472c80da28bad4cf21f2e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813304"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Trasferire un singolo utente nel pool pilota

È possibile trasferire un utente dal pool legacy al pool pilota di Skype for Business Server 2019 usando il pannello di controllo di Skype for Business Server 2019 o Skype for Business Server 2019 Management Shell. Nell'esempio seguente, nella colonna del **pool di registrazione** , **pool01.contoso.NET** è il pool legacy e tutti e sei di questi utenti sono connessi al pool. Usare le procedure seguenti per trasferire un utente nel pool di Skype for Business Server 2019 usando il pannello di controllo di Skype for Business Server 2019 e Skype for Business Server Management Shell. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Per trasferire un utente usando il pannello di controllo di Skype for Business Server 2019
  
1. Accedere al server front-end con un account che sia un membro del gruppo RTCUniversalServerAdmins o un membro del ruolo di amministratore di CsAdministrator o CsUserAdministrator.
    
2. Aprire il **Pannello di controllo di Skype for Business Server**.
    
3. Fare clic su **utenti**, fare clic su **Cerca**e quindi su **trova**.
    
4. Selezionare un utente che si vuole trasferire nel pool di Skype for Business Server 2019. In questo esempio si sposterà l'utente Sara Davis.
    
5. Nel menu **azione** selezionare **Trasferisci utenti selezionati in pool**.
    
6. Nell'elenco a discesa selezionare il pool di Skype for Business Server 2019.
    
7. Fare clic su **azione**e quindi su **Trasferisci utenti selezionati in pool**. Fare clic su **OK**.
  
8. Verificare che la colonna del **pool di registrar** per l'utente contenga ora il pool di Skype for Business Server 2019, che indica che l'utente è stato spostato correttamente. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Per trasferire un utente usando Skype for Business Server 2019 Management Shell

1. Aprire Skype for Business Server Management Shell.
    
2. Nella riga di comando digitare quanto segue: 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. Nella riga di comando, quindi, digitare quanto segue: 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. L'identità **RegistrarPool** punta ora sul pool di Skype for Business Server 2019. La presenza di questa identità conferma che l'utente è stato spostato correttamente. 

    > [!NOTE]
    > Per informazioni dettagliate sul cmdlet **Get-CsUser** , eseguire: **Get-Help Get-CsUser-detailed**
  

