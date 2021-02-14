---
title: Abilitare o disabilitare le conferenze telefoniche con accesso esterno in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Riepilogo: informazioni su come usare il Pannello di controllo o Management Shell per abilitare o disabilitare le conferenze telefoniche con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 99691540306ba0cccf9c63af2e2188e839367bc6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828126"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Abilitare o disabilitare le conferenze telefoniche con accesso esterno in Skype for Business Server
 
**Riepilogo:** Informazioni su come usare il Pannello di controllo o Management Shell per abilitare o disabilitare le conferenze telefoniche con accesso esterno in Skype for Business Server.
  
È possibile abilitare le conferenze telefoniche con accesso esterno utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Abilitare o disabilitare le conferenze telefoniche con accesso esterno tramite il Pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire il Pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su Servizio **di** conferenza e quindi su **Criteri conferenza.**
    
4. Nell'elenco dei criteri conferenza selezionare il criterio per il quale abilitare il servizio di conferenza con accesso esterno e quindi fare clic su **Modifica** e su **Mostra dettagli**. 
    
5. Per consentire agli utenti la partecipazione a una riunione mediante accesso esterno, selezionare la casella di controllo **Consenti conferenza telefonica con accesso esterno PSTN**. Per impostazione predefinita, gli utenti possono connettersi alle riunioni utilizzando la rete PSTN (Public Switched Telephone Network).
    
6. Fare clic su **Commit**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Abilitare o disabilitare le conferenze telefoniche con accesso esterno tramite Skype for Business Server Management Shell

Per abilitare o disabilitare le conferenze telefoniche con accesso esterno, utilizzare il cmdlet **Set-CsConferencingPolicy** con il parametro EnableDialInConferencing nel modo seguente:
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Per ulteriori informazioni, vedere [Set-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
  

