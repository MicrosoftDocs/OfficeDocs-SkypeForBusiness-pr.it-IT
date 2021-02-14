---
title: Configurare le dichiarazioni di non responsabilità relative all'archiviazione per gli utenti esterni in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: "Riepilogo: leggere questo argomento per informazioni su come configurare una dichiarazione di non responsabilità per l'archiviazione per Skype for Business Server."
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820666"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Configurare le dichiarazioni di non responsabilità relative all'archiviazione per gli utenti esterni in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni su come configurare una dichiarazione di non responsabilità di archiviazione per Skype for Business Server.
  
Se l'organizzazione comunica con partner esterni, è necessario comunicare loro che si stanno archiviando le comunicazioni con essi. Quando si distribuisce un server perimetrale e si abilita la federazione per l'organizzazione, viene chiesto se si desidera inviare automaticamente una dichiarazione di non responsabilità per l'archiviazione ai partner esterni. 
  
Se è necessario modificare questa configurazione, è possibile utilizzare il Pannello di controllo di Skype for Business Server o il cmdlet **Set-CsAccessEdgeConfiguration Windows PowerShell Set-CsAccessEdgeConfiguration.** I cmdlet possono essere eseguiti da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell.
  
Per consentire agli utenti esterni di collaborare con gli utenti nella distribuzione di Skype for Business Server, è inoltre necessario configurare almeno un criterio di accesso esterno per supportare l'accesso degli utenti esterni. Per informazioni dettagliate, vedere Manage XMPP Federated Partners for Your Organization. Per informazioni dettagliate sul controllo dell'accesso per domini federati specifici, vedere Control Access by Individual Federated Domains.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Abilitare o disabilitare la dichiarazione di non responsabilità per l'archiviazione tramite il Pannello di controllo

1. Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server. 
    
3. Sulla barra di spostamento sinistra fare clic su **Federazione e accesso esterno** e quindi su **Configurazione Access Edge**.
    
4. Nella scheda **Configurazione Access Edge** fare clic su **Globale**, quindi su **Modifica** e infine su **Mostra dettagli**.
    
5. In Modifica configurazione **Access Edge,** in Abilita federazione e connettività per messaggistica istantanea **pubblica,** selezionare o deselezionare la casella di controllo Invia dichiarazione di non responsabilità per l'archiviazione ai **partner federati** per abilitare o disabilitare l'invio automatico della dichiarazione di non responsabilità per l'archiviazione.
    
6. Fare clic su **Commit**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Abilitare o disabilitare la dichiarazione di non responsabilità per l'archiviazione Windows PowerShell

Per abilitare la dichiarazione di non responsabilità relativa all'archiviazione, impostare il valore della proprietà **EnableArchivingDisclaimer** su True ($True):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Per disabilitare la dichiarazione di non responsabilità relativa all'archiviazione, impostare il valore della proprietà **EnableArchivingDisclaimer** su False ($False):
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


