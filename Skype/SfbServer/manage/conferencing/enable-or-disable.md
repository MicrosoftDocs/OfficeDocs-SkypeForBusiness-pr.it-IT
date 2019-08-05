---
title: Abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Riepilogo: informazioni su come usare il pannello di controllo o la shell di gestione per abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 6723c3501b226d11977ad176a804210540f1a2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194524"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
 
**Riepilogo:** Informazioni su come usare il pannello di controllo o Management Shell per abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.
  
Puoi abilitare i servizi di conferenza telefonica con accesso esterno usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno tramite il pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2.  Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri di conferenza**.
    
4. Nell'elenco dei criteri di conferenza selezionare i criteri per cui si desidera abilitare i servizi di conferenza telefonica con accesso esterno, fare clic su **modifica**e quindi su **Mostra dettagli**. 
    
5. Per consentire agli utenti di partecipare a una riunione effettuando la chiamata, selezionare la casella di controllo **Abilita conferenza telefonica con accesso esterno PSTN** . Per impostazione predefinita, gli utenti possono eseguire la chiamata alle riunioni tramite la rete PSTN (Public Switched Telephone Network).
    
6. Fare clic su **Commit**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno usando Skype for Business Server Management Shell

Per abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno, usare il cmdlet **Set-CsConferencingPolicy** con il parametro EnableDialInConferencing come indicato di seguito:
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Per altre informazioni, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

