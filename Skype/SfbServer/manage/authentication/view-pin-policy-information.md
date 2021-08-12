---
title: Visualizzare le informazioni sui criteri PIN in Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: 'Riepilogo: visualizzare le informazioni sui criteri PIN di un utente per Skype for Business Server.'
ms.openlocfilehash: 385602c4395ec0a189bc25d8a1ab052a8bf1475b440fc34795d54110b4bcffc2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286835"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a>Visualizzare le informazioni sui criteri PIN in Skype for Business Server
 
**Riepilogo:** Visualizzare le informazioni sui criteri PIN di un utente per Skype for Business Server.
  
È possibile utilizzare la **scheda Criteri PIN** per visualizzare l'autenticazione PIN (Personal Identification Number) degli utenti che si connettono Skype for Business con telefoni IP. Per utilizzare l'autenticazione tramite PIN, verificare che sia selezionata l'opzione **Abilita autenticazione PIN** nelle impostazioni relative ai servizi Web.
  
Effettuare la procedura seguente per modificare i criteri PIN a livello di utente o a livello di sito. 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a>Per visualizzare le informazioni su un criterio PIN nel Skype for Business Server Di controllo

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer nella rete in cui è stato distribuito Skype for Business Server.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.  
    
3. Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Criteri PIN**.
    
4. Nella pagina **Criteri PIN** scegliere i criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Visualizzazione dei criteri PIN tramite Windows PowerShell cmdlet

È inoltre possibile visualizzare i criteri PIN utilizzando Windows PowerShell e il cmdlet Get-CsPinPolicy. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-view-pin-policies"></a>Per visualizzare i criteri PIN

Per visualizzare informazioni su tutti i criteri PIN, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
  ```PowerShell
  Get-CsPinPolicy
  ```

Verranno restituite informazioni simili alle seguenti:

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsPinPolicy.](/powershell/module/skype/get-cspinpolicy?view=skype-ps)
  
## <a name="see-also"></a>Vedere anche

[Creare un nuovo criterio PIN in Skype for Business Server](create-a-new-pin-policy.md)