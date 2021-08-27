---
title: Spostare un singolo utente nel pool pilota
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
description: È possibile spostare un utente dal pool legacy al pool pilota di Skype for Business Server 2019 utilizzando il Pannello di controllo di Skype for Business Server 2019 o Skype for Business Server 2019 Management Shell. Nell'esempio seguente, nella colonna Pool di registrazione, pool01.contoso.net è il pool legacy e tutti e sei questi utenti sono connessi a questo pool. Utilizzare le procedure seguenti per spostare un utente nel pool di Skype for Business Server 2019 utilizzando il Pannello di controllo di Skype for Business Server 2019 e Skype for Business Server Management Shell.
ms.openlocfilehash: 987eeec96d28257b995b5e27ce02e282df019980
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596160"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Spostare un singolo utente nel pool pilota

È possibile spostare un utente dal pool legacy al pool pilota di Skype for Business Server 2019 utilizzando il Pannello di controllo di Skype for Business Server 2019 o Skype for Business Server 2019 Management Shell. Nell'esempio seguente, nella colonna Pool di **registrazione,** **pool01.contoso.net** è il pool legacy e tutti e sei questi utenti sono connessi a questo pool. Utilizzare le procedure seguenti per spostare un utente nel pool di Skype for Business Server 2019 utilizzando il Pannello di controllo di Skype for Business Server 2019 e Skype for Business Server Management Shell. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Per spostare un utente tramite il Pannello di controllo Skype for Business Server 2019
  
1. Eseguire l'accesso al Front End Server con un account membro del gruppo RTCUniversalServerAdmins oppure membro del ruolo amministrativo CsAdministrator o CsUserAdministrator.
    
2. Aprire **Skype for Business Server Pannello di controllo.**
    
3. Fare **clic su** Utenti, su **Cerca** e quindi su **Trova.**
    
4. Selezionare un utente che si desidera spostare nel pool Skype for Business Server 2019. In questo esempio, sposteremo l'utente Sara Davis.
    
5. Scegliere **Sposta utenti selezionati nel pool** dal menu **Azione**.
    
6. Nell'elenco a discesa selezionare il pool Skype for Business Server 2019.
    
7. Fare clic su **Azione** e quindi su **Sposta utenti selezionati nel pool**. Fare clic su **OK**.
  
8. Verificare che la colonna **Pool di registrazione** per l'utente contenga ora il pool Skype for Business Server 2019, che indica che l'utente è stato spostato correttamente. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Per spostare un utente tramite Skype for Business Server 2019 Management Shell

1. Aprire la Skype for Business Server Management Shell.
    
2. Nella riga di comando digitare quanto segue: 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. Nella riga di comando, digitare quindi quanto segue: 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. **L'identità RegistrarPool** ora punta al pool Skype for Business Server 2019. La presenza di questa identità conferma che l'utente è stato spostato correttamente. 

    > [!NOTE]
    > Per informazioni dettagliate sul cmdlet **Get-CsUser,** eseguire: **Get-Help Get-CsUser -Detailed**
  

