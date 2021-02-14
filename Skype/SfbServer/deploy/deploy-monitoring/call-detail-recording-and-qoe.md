---
title: Configurare le impostazioni di registrazione dettagli chiamata e Qualità dell'esperienza in Skype for Business Server
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
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Riepilogo: informazioni su come configurare cdr e QoE in Skype for Business Server.'
ms.openlocfilehash: dd8611723e3d83f8a4553ba2148ee5ae29791e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802286"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>Configurare le impostazioni di registrazione dettagli chiamata e Qualità dell'esperienza in Skype for Business Server
 
**Riepilogo:** Informazioni su come configurare cdr e QoE in Skype for Business Server.
  
Configurare il monitoraggio cdr e QoE SQL Server report di Reporting Services per Skype for Business Server.
  
## <a name="configure-cdr-and-qoe"></a>Configurare cdr e QoE

Dopo aver associato un archivio di monitoraggio a un pool Front End, aver configurato l'archivio di monitoraggio e aver installato e configurato SQL Server Reporting Services e i rapporti di monitoraggio, è possibile gestire il monitoraggio della registrazione dettagli chiamata (CDR) e della qualità dell'esperienza (QoE) tramite Skype for Business Server Management Shell. I cmdlet di Skype for Business Server Management Shell consentono di abilitare e disabilitare il monitoraggio CDR e/o QoE per un determinato sito o per l'intera distribuzione di Skype for Business Server; che può essere eseguita con un comando semplice come il seguente:
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Quando installi Skype for Business Server, installi anche una raccolta predefinita di impostazioni di configurazione globali sia per registrazione cdr che per QoE. I valori predefiniti di alcune delle impostazioni usate più di frequente da CDR sono mostrati nella tabella seguente:
  
|**Proprietà**|**Descrizione**|**Valore predefinito**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |Indica se la registrazione dettagli chiamata è abilitata o meno. Se è impostata su True, tutti i record CDR verranno raccolti e scritti nel database di monitoraggio.  <br/> |Vero  <br/> |
|EnablePurging  <br/> |Indica se i record CDR verranno eliminati periodicamente dal database. Se è impostata su True, i record verranno eliminati dopo il periodo di tempo specificato dalle proprietà KeepCallDetailForDays (per record CDR) e KeepErrorReportForDays (per errori CDR). Se False, i record verranno mantenuti indefinitamente.  <br/> |Vero  <br/> |
|KeepCallDetailForDays  <br/> |Indica il numero di giorni per cui i record CDR verranno mantenuti nel database. Qualsiasi record che ha superato il numero di giorni specificato verrà eliminato automaticamente, ma solo se l'eliminazione è stata abilitata.  <br/> KeepCallDetailForDays può essere impostato su qualsiasi valore intero compreso tra 1 e 2562 giorni (circa 7 anni).  <br/> |60 giorni  <br/> |
|KeepErrorReportForDays  <br/> |Indica il numero di giorni in cui vengono mantenute le segnalazioni errori di registrazione dei dati. i rapporti precedenti al numero di giorni specificato verranno eliminati automaticamente. Le segnalazioni errori cdR sono rapporti diagnostici caricati da applicazioni client come Skype for Business Server.  <br/> È possibile impostare questa proprietà su qualsiasi valore intero compreso tra 1 e 2562 giorni.  <br/> |60 giorni  <br/> |
   
Analogamente, i valori predefiniti per le impostazioni QoE selezionate vengono mostrati nella tabella seguente:
  
|**Proprietà**|**Descrizione**|**Valore predefinito**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |Indica se il monitoraggio QoE è abilitato. Se impostata su True, tutti i record QoE verranno raccolti e scritti nel database di monitoraggio.  <br/> |Vero  <br/> |
|EnablePurging  <br/> |Indica se i record QoE verranno eliminati periodicamente dal database. Se è impostata su True, i record verranno eliminati dopo il periodo di tempo specificato dalle proprietà KeepQoEDataForDays. Se False, i record QoE verranno mantenuti indefinitamente.  <br/> |Vero  <br/> |
|KeepQoEDataForDays  <br/> |Indica il numero di giorni per cui i record QoE verranno mantenuti nel database. Qualsiasi record che ha superato il numero di giorni specificato verrà eliminato automaticamente, ma solo se l'eliminazione è stata abilitata.  <br/> KeepCallDetailForDays può essere impostato su qualsiasi valore intero compreso tra 1 e 2562 giorni.  <br/> |60 giorni  <br/> |
   
Se è necessario modificare queste impostazioni globali, è possibile utilizzare i cmdlet Set-CsCdrConfiguration e Set-CsQoEConfiguration globali. Ad esempio, questo comando (eseguito dall'interno di Skype for Business Server Management Shell) disabilita il monitoraggio cdR nell'ambito globale; questa operazione viene eseguita impostando la proprietà EnableCDR su False ($False):
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

Si noti che la disabilitazione del monitoraggio non annulla l'associazione dell'archivio di monitoraggio dal pool Front End e non disinstallerà o influirà in alcun modo sul database di monitoraggio back-end. Quando si utilizza Skype for Business Server Management Shell per disabilitare il monitoraggio cdr o QoE, è possibile interrompere temporaneamente la raccolta e l'archiviazione dei dati di monitoraggio di Skype for Business Server. Se, in questo caso, si desidera riprendere la raccolta e l'archiviazione di dati CDR, è sufficiente impostare di nuovo la proprietà EnableCDR su True ($True):
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Analogamente, questo comando disabilita l'eliminazione dei record QoE a livello di ambito globale:
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

Oltre alle impostazioni globali, le impostazioni di configurazione di CDR e QoE possono essere assegnate all'ambito del sito. Ciò offre una maggiore flessibilità a livello di gestione per il monitoraggio. Ad esempio, un amministratore può abilitare il monitoraggio CDR per il sito di Redmond ma disabilitarlo per il sito di Dublino. Per creare nuove impostazioni di configurazione CDR a livello di ambito di sito, utilizzare un comando simile a questo:
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

È necessario ricordare che le impostazioni configurate a livello di ambito di sito hanno priorità maggiore rispetto alle impostazioni configurate a livello di ambito globale. Ad esempio, si supponga che il monitoraggio CDR sia abilitato a livello di ambito globale, ma disabilitato a livello di ambito di sito (per il sito di Redmond). Le informazioni sulle registrazioni dettagli chiamata non verranno quindi archiviate per gli utenti del sito di Redmond, ma verranno archiviate per gli utenti di altri siti, ovvero utenti gestiti dalle impostazioni globali invece che dalle impostazioni de sito di Redmond.
  
Nuove impostazioni di configurazione QoE possono essere create a livello di ambito di sito utilizzando un comando simile a questo:
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

Per ulteriori informazioni, digitare i comandi seguenti da Skype for Business Server Management Shell:
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
