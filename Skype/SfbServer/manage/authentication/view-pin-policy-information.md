---
title: Visualizzare le informazioni sui criteri PIN in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Riepilogo: visualizzare le informazioni sui criteri PIN di un utente per Skype for Business Server.'
ms.openlocfilehash: 5f6269b766748d5027c0a8182dd027754cd5cc00
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194956"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Visualizzare le informazioni sui criteri PIN in Skype for Business Server
 
**Riepilogo:** Visualizzare le informazioni sui criteri PIN di un utente per Skype for Business Server.
  
È possibile usare la scheda **criteri PIN** per visualizzare l'autenticazione PIN (Personal Identification Number) degli utenti che si connettono a Skype for business con telefoni IP. Per usare l'autenticazione PIN, verificare che **l'opzione Abilita autenticazione PIN** sia selezionata nelle impostazioni del servizio Web.
  
Seguire questa procedura per modificare un criterio PIN a livello di utente o a livello di sito. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Per visualizzare informazioni su un criterio PIN nel pannello di controllo di Skype for Business Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Skype for Business Server. .
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **sicurezza** e quindi su **criteri PIN**.
    
4. Nella pagina **criteri PIN** fare clic su un criterio, fare clic su **modifica**e quindi su **Mostra dettagli**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Visualizzazione dei criteri PIN tramite i cmdlet di Windows PowerShell

È anche possibile visualizzare i criteri PIN usando Windows PowerShell e il cmdlet Get-CsPinPolicy. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-view-pin-policies"></a>Per visualizzare i criteri PIN

Per visualizzare informazioni su tutti i criteri PIN, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
  ```
  Get-CsPinPolicy
  ```

Questo restituirà informazioni simili alla seguente:

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) .
  
## <a name="see-also"></a>Vedere anche

[Creare un nuovo criterio PIN in Skype for Business Server](create-a-new-pin-policy.md)
