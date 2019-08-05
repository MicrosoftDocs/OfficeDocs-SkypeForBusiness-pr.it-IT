---
title: Eliminare una raccolta esistente di impostazioni di configurazione CDR in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Riepilogo: informazioni su come rimuovere le impostazioni di configurazione CDR in Skype for Business Server.'
ms.openlocfilehash: 91ee9676b3087c5b125c6cfe935f706bbfb22812
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195699"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Eliminare una raccolta esistente di impostazioni di configurazione CDR in Skype for Business Server
 
**Riepilogo:** Informazioni su come rimuovere le impostazioni di configurazione CDR in Skype for Business Server.
  
La registrazione dei dettagli delle chiamate (CDR) consente di tenere traccia dell'uso di elementi come sessioni di messaggistica istantanea peer-to-peer, chiamate telefoniche VoIP (Voice over Internet Protocol) e chiamate in conferenza. Questo dati di utilizzo include informazioni su chi ha chiamato chi, quando ha chiamato, e per quanto tempo ha parlato.
  
Quando si installa Skype for Business Server, viene creata una singola raccolta globale di impostazioni di configurazione CDR. Gli amministratori hanno anche la possibilità di creare raccolte di impostazioni personalizzate che possono essere applicate a singoli siti. In base alla progettazione, le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale. Se si eliminano le impostazioni con ambito sito, il CDR verrà gestito in tale sito usando le impostazioni globali.
  
Tieni presente che puoi anche "eliminare" le impostazioni globali. Tuttavia, le impostazioni globali non verranno effettivamente rimosse. Tutte le proprietà della raccolta verranno invece reimpostate sui rispettivi valori predefiniti. Ad esempio, per impostazione predefinita, l'eliminazione è abilitata in una raccolta di impostazioni di configurazione CDR. Supponiamo che tu modifichi la raccolta globale in modo che l'eliminazione sia disabilitata. Se in seguito si eliminano le impostazioni globali, tutte le proprietà verranno reimpostate sui valori predefiniti. In questo caso, ciò significa che l'eliminazione sarà ancora una volta abilitata.
  
È possibile rimuovere le impostazioni di configurazione CDR usando il pannello di controllo di Skype for Business Server o il cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>Per rimuovere le impostazioni di configurazione CDR con il pannello di controllo di Skype for Business Server

1. Nel pannello di controllo di Skype for Business Server fare clic su **monitoraggio e archiviazione**. 
    
2. Nella scheda **registrazione dettagli chiamata** selezionare la raccolta (o le raccolte) delle impostazioni CDR da rimuovere. Per selezionare più raccolte, fare clic sulla prima raccolta, tenere premuto il tasto CTRL e fare clic su altre raccolte.
    
3. Fare clic su **modifica**e quindi su **Elimina**.
    
4. Nella finestra di dialogo Pannello di controllo di Skype for Business Server fare clic su **OK**.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione CDR con i cmdlet di Windows PowerShell

Puoi eliminare le impostazioni di configurazione della registrazione dei dettagli delle chiamate usando Windows PowerShell e il cmdlet **Remove-CsCdrConfiguration** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>Per rimuovere una raccolta specificata di impostazioni di configurazione CDR

 Questo comando rimuove le impostazioni di configurazione CDR applicate al sito Redmond:
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>Per rimuovere tutte le impostazioni di configurazione CDR applicate all'ambito del sito

 Questo comando rimuove tutte le impostazioni di configurazione CDR applicate all'ambito del sito:
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>Per rimuovere tutte le impostazioni di configurazione CDR che disabilitano la registrazione dei dettagli delle chiamate

 Questo comando rimuove tutte le impostazioni di configurazione CDR in cui la registrazione dei dettagli delle chiamate è stata disattivata:
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Vedere anche

[Eliminare manualmente la registrazione dei dettagli delle chiamate e i database di qualità dell'esperienza in Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

