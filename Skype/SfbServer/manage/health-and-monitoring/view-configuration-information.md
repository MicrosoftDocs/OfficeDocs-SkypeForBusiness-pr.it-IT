---
title: Visualizzare le informazioni di configurazione di registrazione dettagli chiamata in Skype for Business Server
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
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: 'Riepilogo: informazioni su come usare la registrazione dettagli chiamata (CDR) in Skype for Business Server.'
ms.openlocfilehash: 55e5e4e2f1b9d3d54ecb6a4a2614b2b1d206f2fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816636"
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server"></a>Visualizzare le informazioni di configurazione di registrazione dettagli chiamata in Skype for Business Server
 
**Riepilogo:** Informazioni su come usare la registrazione dettagli chiamata (CDR) in Skype for Business Server.
  
La registrazione dettagli chiamata consente di tenere traccia dell'utilizzo delle sessioni di messaggistica istantanea peer-to-peer, delle chiamate telefoniche VoIP (Voice over Internet Protocol) e delle conferenze telefoniche. Questi dati sull'utilizzo includono informazioni sui chiamanti, sugli utenti chiamati, sulla data della chiamata e sulla durata della conversazione.
  
Quando si installa Skype for Business Server, viene creata automaticamente una singola raccolta globale di impostazioni di configurazione di registrazione dei dati. Gli amministratori hanno inoltre la possibilità di creare raccolte di impostazioni personalizzate da applicare ai siti individuali. È possibile visualizzare le impostazioni di configurazione di registrazione dettagli chiamata in uso nell'organizzazione utilizzando il Pannello di controllo di Skype for Business Server o il cmdlet [Get-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a>Per visualizzare le informazioni di configurazione di registrazione dettagli chiamata tramite il Pannello di controllo di Skype for Business Server

1. Nel Pannello di controllo di Skype for Business Server fare clic **su Monitoraggio e archiviazione.**
    
2. Nella scheda **Registrazione dettagli chiamata** viene visualizzato un elenco delle impostazioni di configurazione per la registrazione dettagli chiamata; per ciascuna raccolta di impostazioni comparirà il **Nome** della raccolta, se la Registrazione dettagli chiamata è abilitata o meno (la proprietà **CDR** property), e se l'eliminazione è abilitata (la proprietà **Eliminazione CDR**). Per visualizzare informazioni dettagliate su una raccolta, fare doppio clic sulla raccolta o selezionare la raccolta appropriata, fare clic su **Modifica** e quindi su **Mostra dettagli**. Si noti che è possibile visualizzare le informazioni dettagliate per una raccolta singola di impostazioni di configurazione per la registrazione dettagli chiamata alla volta.
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni di configurazione di Registrazione registrazione Windows PowerShell cmdlet

È possibile visualizzare le impostazioni di configurazione di registrazione dettagli Windows PowerShell e il cmdlet Get-CsCdrConfiguration registrazione dettagli Get-CsCdrConfiguration. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-view-cdr-configuration-information"></a>Visualizzare le informazioni di configurazione della registrazione dettagli chiamata

- Per visualizzare informazioni su tutte le impostazioni di configurazione di registrazione dettagli chiamata, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:
    
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

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)
  

