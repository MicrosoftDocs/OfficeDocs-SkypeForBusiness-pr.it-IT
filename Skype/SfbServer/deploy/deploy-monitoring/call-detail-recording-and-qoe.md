---
title: Configurare le impostazioni di registrazione dettagli chiamata e qualità dell'esperienza in Skype for Business Server
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
description: 'Riepilogo: informazioni su come configurare cdR e QoE in Skype for Business Server.'
ms.openlocfilehash: 7c7cd1efefb2cfc52e6cf40d3b78cbc87774b40db4e4d2b012e79d1f657994cd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304368"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>Configurare le impostazioni di registrazione dettagli chiamata e qualità dell'esperienza in Skype for Business Server
 
**Riepilogo:** Informazioni su come configurare cdR e QoE in Skype for Business Server.
  
Configurare il monitoraggio cdR e QoE SQL Server Reporting Services report per Skype for Business Server.
  
## <a name="configure-cdr-and-qoe"></a>Configurare cdR e QoE

Dopo aver associato un archivio di monitoraggio a un pool Front End, aver configurato l'archivio di monitoraggio e aver installato e configurato SQL Server Reporting Services e i report di monitoraggio, è possibile gestire il monitoraggio della registrazione dettagli chiamata (CDR) e della qualità dell'esperienza (QoE) tramite Skype for Business Server Management Shell. Skype for Business Server I cmdlet di Management Shell consentono di abilitare e disabilitare il monitoraggio cdR e/o QoE per un sito specifico o per l'intera Skype for Business Server distribuzione. che possono essere eseguite con un comando semplice come questo:
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Quando si installa Skype for Business Server, si installerà anche una raccolta predefinita di impostazioni di configurazione globali sia per la registrazione cdR che per la QoE. I valori predefiniti di alcune delle impostazioni usate più di frequente da CDR sono mostrati nella tabella seguente:
  
|**Proprietà**|**Descrizione**|**Valore predefinito**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |Indica se la registrazione dettagli chiamata è abilitata o meno. Se è impostata su True, tutti i record CDR verranno raccolti e scritti nel database di monitoraggio.  <br/> |Vero  <br/> |
|EnablePurging  <br/> |Indica se i record CDR verranno eliminati periodicamente dal database. Se è impostata su True, i record verranno eliminati dopo il periodo di tempo specificato dalle proprietà KeepCallDetailForDays (per record CDR) e KeepErrorReportForDays (per errori CDR). Se False, i record verranno mantenuti indefinitamente.  <br/> |Vero  <br/> |
|KeepCallDetailForDays  <br/> |Indica il numero di giorni per cui i record CDR verranno mantenuti nel database. Qualsiasi record che ha superato il numero di giorni specificato verrà eliminato automaticamente, ma solo se l'eliminazione è stata abilitata.  <br/> KeepCallDetailForDays può essere impostato su qualsiasi valore intero compreso tra 1 e 2562 giorni (circa 7 anni).  <br/> |60 giorni  <br/> |
|KeepErrorReportForDays  <br/> |Indica il numero di giorni in cui vengono mantenute le segnalazioni errori di registrazione dei dati. i rapporti precedenti al numero di giorni specificato verranno eliminati automaticamente. Le segnalazioni errori cdR sono report di diagnostica caricati da applicazioni client, ad esempio Skype for Business Server.  <br/> È possibile impostare questa proprietà su qualsiasi valore intero compreso tra 1 e 2562 giorni.  <br/> |60 giorni  <br/> |
   
Analogamente, i valori predefiniti per le impostazioni QoE selezionate vengono mostrati nella tabella seguente:
  
|**Proprietà**|**Descrizione**|**Valore predefinito**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |Indica se il monitoraggio QoE è abilitato. Se impostata su True, tutti i record QoE verranno raccolti e scritti nel database di monitoraggio.  <br/> |Vero  <br/> |
|EnablePurging  <br/> |Indica se i record QoE verranno eliminati periodicamente dal database. Se è impostata su True, i record verranno eliminati dopo il periodo di tempo specificato dalle proprietà KeepQoEDataForDays. Se False, i record QoE verranno mantenuti indefinitamente.  <br/> |Vero  <br/> |
|KeepQoEDataForDays  <br/> |Indica il numero di giorni per cui i record QoE verranno mantenuti nel database. Qualsiasi record che ha superato il numero di giorni specificato verrà eliminato automaticamente, ma solo se l'eliminazione è stata abilitata.  <br/> KeepCallDetailForDays può essere impostato su qualsiasi valore intero compreso tra 1 e 2562 giorni.  <br/> |60 giorni  <br/> |
   
Se è necessario modificare queste impostazioni globali, è possibile farlo utilizzando i cmdlet Set-CsCdrConfiguration e Set-CsQoEConfiguration. Ad esempio, questo comando (eseguito dall'interno di Skype for Business Server Management Shell) disabilita il monitoraggio della registrazione dei dati nell'ambito globale; questa operazione viene eseguita impostando la proprietà EnableCDR su False ($False):
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

Si noti che la disabilitazione del monitoraggio non annulla l'associazione dell'archivio di monitoraggio dal pool Front End e non disinstallerà o influirà in alcun modo sul database di monitoraggio back-end. Quando si utilizza Skype for Business Server Management Shell per disabilitare il monitoraggio della registrazione dei dati cdr o QoE, è necessario interrompere temporaneamente Skype for Business Server raccogliere e archiviare i dati di monitoraggio. Se, in questo caso, si desidera riprendere la raccolta e l'archiviazione di dati CDR, è sufficiente impostare di nuovo la proprietà EnableCDR su True ($True):
  
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
