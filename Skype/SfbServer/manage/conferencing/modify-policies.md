---
title: Modificare i criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Riepilogo: informazioni su come modificare i criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: b2c192948f0119a70f031c1c2bbe5de8e776c2f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188954"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>Modificare i criteri di conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come modificare i criteri di conferenza in Skype for Business Server.
  
Puoi modificare i criteri di conferenza usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Modificare i criteri di conferenza tramite il pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri di conferenza**.
    
4. Nell'elenco dei criteri di conferenza fare clic sul criterio che si vuole modificare, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. In **modifica criteri di conferenza**modificare le impostazioni dei criteri, ad eccezione del nome del criterio, che non può essere modificato.
    
6. Fare clic su **Commit**.
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Modificare i criteri di conferenza tramite Skype for Business Server Management Shell

Per modificare i criteri di conferenza, usare il cmdlet **Set-CsConferencingPolicy** .
  
Nell'esempio seguente viene modificato il valore di una proprietà del criterio di conferenza SalesConferencingPolicy. Il comando imposta il valore della proprietà AllowConferenceRecording su false:
  
```
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

Per altre informazioni, inclusa la sintassi completa e un elenco di parametri, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

