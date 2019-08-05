---
title: Eliminare le impostazioni di configurazione della qualità delle esperienze in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Riepilogo: informazioni su come eliminare le impostazioni di qualità delle esperienze (QoE) in Skype for Business Server.'
ms.openlocfilehash: 4b521afd85a97550b27f320b9e49c5439e431681
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195698"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Eliminare le impostazioni di configurazione della qualità delle esperienze in Skype for Business Server
 
**Riepilogo:** Informazioni su come eliminare le impostazioni di qualità delle esperienze (QoE) in Skype for Business Server.
  
Le metriche sulla qualità delle esperienze (QoE) tengono traccia della qualità delle chiamate audio e video effettuate nell'organizzazione, tra cui il numero di pacchetti di rete persi, il rumore di fondo e la quantità di "jitter" (differenze nel ritardo del pacchetto). Queste metriche sono archiviate in un database, oltre ad altri dati, ad esempio i record dettagli chiamata, che consentono di abilitare e disabilitare QoE indipendentemente da altre registrazioni di dati.
  
Quando si installa Skype for Business Server, viene creata una singola raccolta globale di impostazioni di configurazione QoE. Gli amministratori hanno anche la possibilità di creare raccolte di impostazioni personalizzate che possono essere applicate a singoli siti. In base alla progettazione, le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale. Se si eliminano le impostazioni con ambito sito, QoE verrà gestito in tale sito utilizzando le impostazioni globali.
  
Tieni presente che puoi anche "eliminare" le impostazioni globali. Tuttavia, le impostazioni globali non verranno effettivamente rimosse. Tutte le proprietà della raccolta verranno invece reimpostate sui rispettivi valori predefiniti. Ad esempio, per impostazione predefinita, l'eliminazione è abilitata in una raccolta di impostazioni di configurazione QoE. Supponiamo che tu modifichi la raccolta globale in modo che l'eliminazione sia disabilitata. Se in seguito si eliminano le impostazioni globali, tutte le proprietà verranno reimpostate sui valori predefiniti. In questo caso, ciò significa che l'eliminazione sarà ancora una volta abilitata.
  
Puoi rimuovere le impostazioni di configurazione QoE usando il pannello di controllo di Skype for Business Server o usando il cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Per eliminare le impostazioni di configurazione QoE usando il pannello di controllo di Skype for Business Server

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere delegare le **autorizzazioni di configurazione**.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.
    
4. Nella pagina **qualità di dati esperienza** fare clic sui criteri desiderati, fare clic su **modifica**e quindi su **Elimina**.
    
5. Fare clic su **OK**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione QoE con i cmdlet di Windows PowerShell

Puoi eliminare le impostazioni di configurazione QoE usando Windows PowerShell e il cmdlet **Remove-CsQoEConfiguration** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>Per rimuovere una raccolta specificata di impostazioni di configurazione QoE

 Questo comando rimuove le impostazioni di configurazione QoE applicate al sito Redmond:
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>Per rimuovere tutte le impostazioni di configurazione QoE applicate all'ambito del sito

 Questo comando rimuove tutte le impostazioni di configurazione QoE applicate all'ambito del sito:
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Per rimuovere tutte le impostazioni di configurazione QoE in cui il monitoraggio QoE è disabilitato

 Questo comando rimuove tutte le impostazioni di configurazione QoE in cui è stato disabilitato il monitoraggio QoE:
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

Per informazioni dettagliate, vedere [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>Vedere anche

[Eliminare manualmente la registrazione dei dettagli delle chiamate e i database di qualità dell'esperienza in Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

