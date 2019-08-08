---
title: Configurare le esclusioni di archiviazione per utenti esterni in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: "Riepilogo: leggere questo argomento per informazioni su come configurare una dichiarazione di non responsabilità per l'archiviazione per Skype for Business Server."
ms.openlocfilehash: 5901429918d4cf346cbbf9f1fdad6ff4736817ea
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234568"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Configurare le esclusioni di archiviazione per utenti esterni in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare una dichiarazione di non responsabilità per l'archiviazione per Skype for Business Server.
  
Se l'organizzazione comunica con partner esterni, è necessario comunicare loro di archiviare le comunicazioni. Quando si distribuisce un server perimetrale e si Abilita la Federazione per l'organizzazione, viene chiesto se si vuole inviare automaticamente una dichiarazione di non responsabilità per l'archiviazione a partner esterni. 
  
Se è necessario modificare questa configurazione, è possibile usare il pannello di controllo di Skype for Business Server o il cmdlet **Set-CsAccessEdgeConfiguration** di Windows PowerShell. I cmdlet possono essere eseguiti da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.
  
Per consentire agli utenti esterni di collaborare con gli utenti nella distribuzione di Skype for Business Server, è anche necessario configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti esterni. Per informazioni dettagliate, vedere gestire partner federativi XMPP per l'organizzazione. Per informazioni dettagliate su come controllare l'accesso per specifici domini federati, vedere controllare l'accesso in base a singoli domini federati.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Abilitare o disabilitare l'archiviazione della dichiarazione di non responsabilità tramite il pannello di controllo

1. Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server. 
    
3. Nella barra di spostamento sinistra fare clic su **Federazione e accesso esterno**e quindi su **configurazione bordo di Access**.
    
4. Nella scheda **configurazione di Access Edge** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
5. In **modifica configurazione di Access Edge**selezionare o deselezionare la casella di controllo **Invia dichiarazione di non responsabilità per i partner federati** in Abilitazione o disabilitazione dell'archiviazione automatica per abilitare o disabilitare la **connettività di messaggistica istantanea pubblica** Disclaimer.
    
6. Fare clic su **Commit**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Abilitare o disabilitare l'archiviazione della dichiarazione di non responsabilità tramite Windows PowerShell

Per abilitare la dichiarazione di non responsabilità per l'archiviazione, imposta il valore della proprietà **EnableArchivingDisclaimer** su True ($true):
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Per disabilitare la dichiarazione di non responsabilità per l'archiviazione, imposta il valore della proprietà **EnableArchivingDisclaimer** su False ($false):
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


