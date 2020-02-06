---
title: Visualizzare le informazioni di configurazione CDR in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Riepilogo: informazioni su come usare la registrazione dei dettagli delle chiamate (CDR) in Skype for Business Server.'
ms.openlocfilehash: f4a216f1c2d8892370b80eef42c19cf07c133312
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817595"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Visualizzare le informazioni di configurazione CDR in Skype for Business Server
 
**Riepilogo:** Informazioni su come usare la registrazione dei dettagli delle chiamate (CDR) in Skype for Business Server.
  
La registrazione dei dettagli delle chiamate (CDR) consente di tenere traccia dell'uso di elementi come sessioni di messaggistica istantanea peer-to-peer, chiamate telefoniche VoIP (Voice over Internet Protocol) e chiamate in conferenza. Questo dati di utilizzo include informazioni su chi ha chiamato chi, quando ha chiamato, e per quanto tempo ha parlato.
  
Quando si installa Skype for Business Server, viene creata una singola raccolta globale di impostazioni di configurazione CDR. Gli amministratori hanno anche la possibilità di creare raccolte di impostazioni personalizzate che possono essere applicate a singoli siti. Per visualizzare le impostazioni di configurazione CDR in uso nell'organizzazione, è possibile usare il pannello di controllo di Skype for Business Server o il cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Per visualizzare le informazioni di configurazione CDR tramite il pannello di controllo di Skype for Business Server

1. Nel pannello di controllo di Skype for Business Server fare clic su **monitoraggio e archiviazione**.
    
2. Nella scheda **registrazione dettagli chiamata** verrà visualizzato un elenco di tutte le impostazioni di configurazione CDR. per ogni raccolta di impostazioni verrà visualizzato il **nome**della raccolta; indipendentemente dal fatto che CDR sia stato abilitato (la proprietà **CDR** ); e indipendentemente dal fatto che l'eliminazione sia stata abilitata (la proprietà **cancellazione CDR** ). Per visualizzare informazioni dettagliate su una raccolta, fare doppio clic sulla raccolta oppure selezionare la raccolta appropriata, fare clic su **modifica**e quindi su **Mostra dettagli**. Tieni presente che puoi visualizzare solo informazioni dettagliate per una singola raccolta di impostazioni di configurazione CDR alla volta.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni di configurazione CDR tramite i cmdlet di Windows PowerShell

Per visualizzare le impostazioni di configurazione CDR, è possibile usare Windows PowerShell e il cmdlet Get-CsCdrConfiguration. Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-view-cdr-configuration-information"></a>Per visualizzare le informazioni sulla configurazione CDR

- Per visualizzare informazioni su tutte le impostazioni di configurazione CDR, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    Questo restituirà informazioni simili alla seguente:
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) .
  

