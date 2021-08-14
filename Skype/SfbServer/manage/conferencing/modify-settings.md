---
title: Modificare le impostazioni di configurazione delle riunioni in Skype for Business Server
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Riepilogo: informazioni su come modificare le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: e1b283c5d50c955464d4af9b8f92f9e210f60f35a1fad5320c9f6bb8b6ede11d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343460"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Modificare le impostazioni di configurazione delle riunioni in Skype for Business Server
 
**Riepilogo:** Informazioni su come modificare le impostazioni di configurazione delle riunioni in Skype for Business Server.
  
È possibile modificare le impostazioni di configurazione delle riunioni Skype for Business Server pannello di controllo o tramite Skype for Business Server Management Shell.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modificare le impostazioni di configurazione delle riunioni utilizzando Skype for Business Server pannello di controllo

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire Skype for Business Server Pannello di controllo.
    
3. Sulla barra di spostamento sinistra fare clic su **Conferenza** e quindi su **Configurazione riunione.**
    
4. Nell'elenco delle configurazioni delle riunioni fare clic sulla configurazione che si desidera modificare, fare clic su **Modifica** e quindi su **Mostra dettagli.**
    
5. In **Modifica configurazione riunione** modificare qualsiasi impostazione di configurazione, tranne il nome della configurazione, che non può essere modificato.
    
6. Fare clic su **Commit**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modificare le impostazioni di configurazione delle riunioni tramite Skype for Business Server Management Shell

Per modificare le impostazioni di configurazione delle riunioni, utilizzare il cmdlet **Set-CsMeetingConfiguration.**
  
Il comando riportato nell'esempio seguente modifica le impostazioni di configurazione delle riunioni assegnate al sito Redmond (-Identity site:Redmond). In questo caso, il valore della proprietà DesignateAsPresenter è impostato su Everyone:
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Per ulteriori informazioni, incluso un elenco completo di parametri, [vedere Set-CsMeetingConfiguration.](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)
