---
title: Visualizzare le informazioni di configurazione della registrazione dettagli Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Riepilogo: informazioni su come usare la registrazione dettagli chiamata in Skype for Business Server.'
ms.openlocfilehash: 97019a9d8689cf9eb5cacac82d6776b44bc4283d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743482"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Visualizzare le informazioni di configurazione della registrazione dettagli Skype for Business Server
 
**Riepilogo:** Informazioni su come usare la registrazione dettagli chiamata (CDR) in Skype for Business Server.
  
La registrazione dettagli chiamata consente di tenere traccia dell'utilizzo delle sessioni di messaggistica istantanea peer-to-peer, delle chiamate telefoniche VoIP (Voice over Internet Protocol) e delle conferenze telefoniche. Questi dati sull'utilizzo includono informazioni sui chiamanti, sugli utenti chiamati, sulla data della chiamata e sulla durata della conversazione.
  
Quando si installa Skype for Business Server, viene creata automaticamente una singola raccolta globale di impostazioni di configurazione della registrazione dei dati. Gli amministratori hanno inoltre la possibilità di creare raccolte di impostazioni personalizzate da applicare ai siti individuali. È possibile visualizzare le impostazioni di configurazione della registrazione dettagli dettagli windows in uso nell'organizzazione utilizzando Skype for Business Server pannello di controllo o il cmdlet [Get-CsCdrConfiguration.](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Per visualizzare le informazioni di configurazione della registrazione dettagli dettagli Skype for Business Server pannello di controllo

1. Nel Skype for Business Server di controllo fare clic **su Monitoraggio e archiviazione.**
    
2. Nella scheda **Registrazione dettagli chiamata** viene visualizzato un elenco delle impostazioni di configurazione per la registrazione dettagli chiamata; per ciascuna raccolta di impostazioni comparirà il **Nome** della raccolta, se la Registrazione dettagli chiamata è abilitata o meno (la proprietà **CDR** property), e se l'eliminazione è abilitata (la proprietà **Eliminazione CDR**). Per visualizzare informazioni dettagliate su una raccolta, fare doppio clic sulla raccolta o selezionare la raccolta appropriata, fare clic su **Modifica** e quindi su **Mostra dettagli**. Si noti che è possibile visualizzare le informazioni dettagliate per una raccolta singola di impostazioni di configurazione per la registrazione dettagli chiamata alla volta.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni di configurazione di registrazione dei dati tramite Windows PowerShell cmdlet

È possibile visualizzare le impostazioni di configurazione della registrazione dettagli Windows PowerShell e il cmdlet Get-CsCdrConfiguration registrazione dettagli dettagli. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remota per connettersi a Skype for Business Server, vedere Amministrazione remota di PowerShell per [Microsoft Lync.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-view-cdr-configuration-information"></a>Visualizzare le informazioni di configurazione della registrazione dettagli chiamata

- Per visualizzare le informazioni su tutte le impostazioni di configurazione della registrazione dettagli dettagli ricerca, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
  ```PowerShell
  Get-CsCdrConfiguration
  ```

    Verranno restituite informazioni simili alle seguenti:
    
<pre>
Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2
</pre>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsCdrConfiguration.](/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
