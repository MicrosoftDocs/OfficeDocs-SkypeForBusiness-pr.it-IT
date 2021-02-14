---
title: Eliminare le impostazioni di configurazione della qualità dell'esperienza in Skype for Business Server
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
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Riepilogo: informazioni su come eliminare le impostazioni QoE (Quality of Experience) in Skype for Business Server.'
ms.openlocfilehash: 45150b6aa2e6f48eedb28f180cfff8f291f58abc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816936"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Eliminare le impostazioni di configurazione della qualità dell'esperienza in Skype for Business Server
 
**Riepilogo:** Informazioni su come eliminare le impostazioni QoE (Quality of Experience) in Skype for Business Server.
  
La metrica QoE registra la qualità delle chiamate audio e video effettuate nell'organizzazione, includendo informazioni quali il numero di pacchetti di rete persi, i rumori di fondo e il livello di "instabilità" (differenze nel ritardo dei pacchetti). Questa metrica viene archiviata in un database separatamente rispetto ad altri dati, ad esempio la registrazione dettagli chiamata, in modo che sia possibile abilitare e disabilitare il servizio QoE in maniera indipendente rispetto ad altre registrazioni di dati.
  
Quando si installa Skype for Business Server, viene creata automaticamente una singola raccolta globale di impostazioni di configurazione QoE. Gli amministratori hanno inoltre la possibilità di creare raccolte di impostazioni personalizzate da applicare ai siti individuali. Per impostazione predefinita, le impostazioni configurate in ambito sito hanno la precedenza sulle impostazioni configurate in ambito globale. Se si eliminano le impostazioni in ambito sito, le metriche QoE verranno gestite nel sito utilizzando le impostazioni globali.
  
Si noti che è anche possibile "eliminare" le impostazioni globali. Tuttavia, le impostazioni globali non vengono effettivamente rimosse. Invece, tutte le proprietà nella raccolta vengono reimpostate sui valori predefiniti. Ad esempio, per impostazione predefinita, l'eliminazione è abilitata in una raccolta di impostazioni di configurazione QoE. Supponiamo di modificare la raccolta globale in modo da disabilitare la rimozione. Se successivamente si eliminano le impostazioni globali, tutte le proprietà verranno reimpostate sui valori predefiniti. In questo caso, ciò significa che l'eliminazione verrà riabilitata.
  
È possibile rimuovere le impostazioni di configurazione QoE utilizzando il Pannello di controllo di Skype for Business Server o il cmdlet [Remove-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Per eliminare le impostazioni di configurazione QoE tramite il Pannello di controllo di Skype for Business Server

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **Delegate Setup Permissions**.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.
    
4. Nella pagina **Dati QoE** fare clic sul criterio desiderato, selezionare **Modifica** e quindi fare clic su **Elimina**.
    
5. Fare clic su **OK**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione QoE tramite Windows PowerShell cmdlet

È possibile eliminare le impostazioni di configurazione QoE utilizzando Windows PowerShell e il cmdlet **Remove-CsQoEConfiguration.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>Per rimuovere una raccolta specificata di impostazioni di configurazione QoE

 Questo comando rimuove le impostazioni di configurazione QoE applicate al sito Redmond.
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>Per rimuovere tutte le impostazioni di configurazione QoE applicate all'ambito sito

 Questo comando rimuove tutte le impostazioni di configurazione QoE applicate all'ambito sito.
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Per rimuovere tutte le impostazioni di configurazione QoE dove il monitoraggio QoE è disabilitato

 Questo comando rimuove tutte le impostazioni di configurazione QoE dove il monitoraggio QoE è stato disabilitato
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

Per informazioni dettagliate, [vedere Remove-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)
  
## <a name="see-also"></a>Vedere anche

[Eliminare manualmente i database di registrazione dettagli chiamata e Qualità dell'esperienza in Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

