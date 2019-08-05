---
title: Modificare le impostazioni di configurazione delle riunioni in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Riepilogo: informazioni su come modificare le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: 6e2566a5bc48e081c1912753586aef2213e1c727
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188948"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Modificare le impostazioni di configurazione delle riunioni in Skype for Business Server
 
**Riepilogo:** Informazioni su come modificare le impostazioni di configurazione delle riunioni in Skype for Business Server.
  
Puoi modificare le impostazioni di configurazione delle riunioni usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Modificare le impostazioni di configurazione delle riunioni tramite il pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **Configurazione riunione**.
    
4. Nell'elenco delle configurazioni delle riunioni fare clic sulla configurazione che si vuole modificare, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. In **modifica configurazione riunione**modificare le impostazioni di configurazione, ad eccezione del nome della configurazione, che non può essere modificato.
    
6. Fare clic su **Commit**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Modificare le impostazioni di configurazione delle riunioni con Skype for Business Server Management Shell

Per modificare le impostazioni di configurazione della riunione, usare il cmdlet **Set-CsMeetingConfiguration** .
  
Il comando illustrato nell'esempio seguente consente di modificare le impostazioni di configurazione della riunione assegnate al sito Redmond (-Identity site: Redmond). In questo caso, il valore della proprietà DesignateAsPresenter è impostato su tutti:
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Per altre informazioni, incluso un elenco completo dei parametri, vedere [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).
  

