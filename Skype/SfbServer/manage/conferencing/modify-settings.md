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
ms.openlocfilehash: 80ba12266ebc45fdae3256f5238ecf18415734c8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827996"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Modificare le impostazioni di configurazione delle riunioni in Skype for Business Server
 
**Riepilogo:** Informazioni su come modificare le impostazioni di configurazione delle riunioni in Skype for Business Server.
  
È possibile modificare le impostazioni di configurazione delle riunioni utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modificare le impostazioni di configurazione delle riunioni utilizzando il Pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2.  Aprire il Pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su Servizio **di** conferenza e quindi su **Configurazione riunione.**
    
4. Nell'elenco delle configurazioni riunione fare clic sulla configurazione che si desidera modificare, fare clic su **Modifica** e quindi su **Mostra dettagli.**
    
5. In **Modifica configurazione riunione** modificare qualsiasi impostazione di configurazione, tranne il nome della configurazione, che non può essere modificato.
    
6. Fare clic su **Commit**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modificare le impostazioni di configurazione delle riunioni tramite Skype for Business Server Management Shell

Per modificare le impostazioni di configurazione delle riunioni, utilizzare il cmdlet **Set-CsMeetingConfiguration.**
  
Il comando riportato nell'esempio seguente consente di modificare le impostazioni di configurazione delle riunioni assegnate al sito Redmond (-Identity site:Redmond). In questo caso, il valore della proprietà DesignateAsPresenter è impostato su Tutti:
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Per ulteriori informazioni, incluso un elenco completo dei parametri, [vedere Set-CsMeetingConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)
  

