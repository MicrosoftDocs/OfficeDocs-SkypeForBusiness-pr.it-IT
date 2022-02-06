---
title: Eliminare le impostazioni di configurazione di Qualità dell'esperienza in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Riepilogo: informazioni su come eliminare le impostazioni QoE (Quality of Experience) in Skype for Business Server.'
---

# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Eliminare le impostazioni di configurazione di Qualità dell'esperienza in Skype for Business Server
 
**Riepilogo:** Informazioni su come eliminare le impostazioni QoE (Quality of Experience) in Skype for Business Server.
  
La metrica QoE registra la qualità delle chiamate audio e video effettuate nell'organizzazione, includendo informazioni quali il numero di pacchetti di rete persi, i rumori di fondo e il livello di "instabilità" (differenze nel ritardo dei pacchetti). Questa metrica viene archiviata in un database separatamente rispetto ad altri dati, ad esempio la registrazione dettagli chiamata, in modo che sia possibile abilitare e disabilitare il servizio QoE in maniera indipendente rispetto ad altre registrazioni di dati.
  
Quando si installa Skype for Business Server, viene creata automaticamente una singola raccolta globale di impostazioni di configurazione QoE. Gli amministratori hanno inoltre la possibilità di creare raccolte di impostazioni personalizzate da applicare ai siti individuali. Per impostazione predefinita, le impostazioni configurate in ambito sito hanno la precedenza sulle impostazioni configurate in ambito globale. Se si eliminano le impostazioni in ambito sito, le metriche QoE verranno gestite nel sito utilizzando le impostazioni globali.
  
Tieni presente che puoi anche "eliminare" le impostazioni globali. Tuttavia, le impostazioni globali non vengono effettivamente rimosse. Invece, tutte le proprietà nella raccolta vengono reimpostate sui valori predefiniti. Ad esempio, per impostazione predefinita l'eliminazione è abilitata in una raccolta di impostazioni di configurazione QoE. Supponiamo di modificare la raccolta globale in modo da disabilitare la rimozione. Se successivamente si eliminano le impostazioni globali, tutte le proprietà verranno reimpostate sui valori predefiniti. In questo caso, ciò significa che l'eliminazione verrà riabilitata.
  
È possibile rimuovere le impostazioni di configurazione QoE utilizzando Skype for Business Server pannello di controllo o il cmdlet [Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Per eliminare le impostazioni di configurazione QoE tramite Skype for Business Server Pannello di controllo

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **Delegate Setup Permissions**.
    
2. Aprire una finestra del browser e quindi immettere l'URL dell'amministratore per aprire il Skype for Business Server di controllo.  
    
3. Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.
    
4. Nella pagina **Dati QoE** fare clic sul criterio desiderato, selezionare **Modifica** e quindi fare clic su **Elimina**.
    
5. Fare clic su **OK**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione della configurazione QoE Impostazioni tramite Windows PowerShell cmdlet

È possibile eliminare le impostazioni di configurazione QoE utilizzando Windows PowerShell e il cmdlet **Remove-CsQoEConfiguration**. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remota per connettersi a Skype for Business Server, vedere Amministrazione remota [di PowerShell per Microsoft Lync](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Il processo è lo stesso in Skype for Business Server.
  
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

Per informazioni dettagliate, [vedere Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>Vedere anche

[Eliminare manualmente i database di registrazione dettagli chiamata e qualità dell'esperienza in Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)