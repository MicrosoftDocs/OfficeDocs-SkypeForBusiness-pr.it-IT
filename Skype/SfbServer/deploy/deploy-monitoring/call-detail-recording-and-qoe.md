---
title: Configurare la registrazione dei dettagli delle chiamate e la qualità delle impostazioni dell'esperienza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Riepilogo: informazioni su come configurare CDR e QoE in Skype for Business Server.'
ms.openlocfilehash: 3e0ff3e8dab09f38d71f9b5211f900e0f0e5fe9f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790054"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>Configurare la registrazione dei dettagli delle chiamate e la qualità delle impostazioni dell'esperienza in Skype for Business Server
 
**Riepilogo:** Informazioni su come configurare CDR e QoE in Skype for Business Server.
  
Configurare il monitoraggio CDR e QoE tramite report di SQL Server Reporting Services per Skype for Business Server.
  
## <a name="configure-cdr-and-qoe"></a>Configurare CDR e QoE

Dopo avere associato un archivio di monitoraggio con un pool Front-End, configurare l'archivio di monitoraggio e quindi installato e configurato SQL Server Reporting Services e monitoraggio dei report è possibile gestire la registrazione dei dettagli delle chiamate (CDR) e la qualità dell'esperienza (QoE) monitoraggio tramite Skype for Business Server Management Shell. I cmdlet di Skype for Business Server Management Shell consentono di abilitare e disabilitare il monitoraggio CDR e/o QoE per un determinato sito o per l'intera distribuzione di Skype for Business Server. Questa operazione può essere eseguita con un comando semplice come questo:
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Quando si installa Skype for Business Server, viene installata anche una raccolta predefinita di impostazioni di configurazione globali sia per CDR che per QoE. Nella tabella seguente sono illustrati i valori predefiniti per alcune delle impostazioni più comuni usate per la registrazione dei dettagli delle chiamate:
  
|**Proprietà**|**Descrizione**|**Valore predefinito**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |Indica se CDR è abilitato o meno. Se true, tutti i record CDR verranno raccolti e scritti nel database di monitoraggio.  <br/> |True  <br/> |
|EnablePurging  <br/> |Indica se i record CDR verranno eliminati periodicamente dal database. Se true, i record verranno eliminati dopo il periodo di tempo specificato dalle proprietà KeepCallDetailForDays (per i record CDR) e KeepErrorReportForDays (per gli errori CDR). Se false, i record CDR verranno mantenuti indefinitamente.  <br/> |True  <br/> |
|KeepCallDetailForDays  <br/> |Indica il numero di giorni in cui i record CDR verranno conservati nel database. tutti i record antecedenti al numero di giorni specificato verranno eliminati automaticamente. Tuttavia, questo problema si verificherà solo se l'eliminazione è stata abilitata.  <br/> KeepCallDetailForDays può essere impostato su un valore intero compreso tra 1 e 2562 giorni (circa 7 anni).  <br/> |60 giorni  <br/> |
|KeepErrorReportForDays  <br/> |Indica il numero di giorni in cui vengono mantenuti i report di errore CDR; tutti i report antecedenti al numero di giorni specificato verranno eliminati automaticamente. I report di errore CDR sono report di diagnostica caricati da applicazioni client come Skype for Business Server.  <br/> Puoi impostare questa proprietà su qualsiasi valore intero compreso tra 1 e 2562 giorni.  <br/> |60 giorni  <br/> |
   
Allo stesso modo, i valori predefiniti per le impostazioni QoE selezionate sono illustrati in questa tabella:
  
|**Proprietà**|**Descrizione**|**Valore predefinito**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |Indica se è abilitato il monitoraggio QoE. Se true, tutti i record QoE verranno raccolti e scritti nel database di monitoraggio.  <br/> |True  <br/> |
|EnablePurging  <br/> |Indica se i record QoE verranno eliminati periodicamente dal database. Se true, i record verranno eliminati dopo il periodo di tempo specificato dalla proprietà KeepQoEDataForDays. Se false, i record QoE verranno mantenuti indefinitamente.  <br/> |True  <br/> |
|KeepQoEDataForDays  <br/> |Indica il numero di giorni in cui i record QoE verranno conservati nel database; tutti i record antecedenti al numero di giorni specificato verranno eliminati automaticamente. Tuttavia, questo problema si verificherà solo se l'eliminazione è stata abilitata.  <br/> KeepCallDetailForDays può essere impostato su qualsiasi valore intero compreso tra 1 e 2562 giorni.  <br/> |60 giorni  <br/> |
   
Se è necessario modificare queste impostazioni globali, è possibile usare i cmdlet Set-CsCdrConfiguration e Set-CsQoEConfiguration. Ad esempio, questo comando (eseguito da Skype for Business Server Management Shell) Disabilita il monitoraggio CDR nell'ambito globale; Questa operazione viene eseguita impostando la proprietà EnableCDR su false ($False):
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

Tieni presente che la disabilitazione del monitoraggio non dissocia l'archivio di monitoraggio dal pool Front-End, né Disinstalla o influisce in altro modo sul database di monitoraggio del backend. Quando si usa Skype for Business Server Management Shell per disabilitare il monitoraggio CDR o QoE, è possibile interrompere temporaneamente Skype for Business Server dalla raccolta e dall'archiviazione dei dati di monitoraggio. Se si vuole riprendere, in questo caso, la raccolta e l'archiviazione dei dati CDR, è sufficiente impostare la proprietà EnableCDR su true ($True):
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Analogamente, questo comando Disabilita l'eliminazione dei record QoE nell'ambito globale:
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

Oltre alle impostazioni globali, le impostazioni delle configurazioni CDR e QoE possono essere assegnate all'ambito del sito. In questo caso è disponibile un'ulteriore flessibilità di gestione per il monitoraggio. ad esempio, un amministratore può abilitare il monitoraggio CDR per il sito Redmond, ma disabilitare il monitoraggio CDR per il sito di Dublino. Per creare nuove impostazioni di configurazione CDR nell'ambito del sito, usare un comando simile al seguente:
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

Tieni presente che le impostazioni configurate nell'ambito del sito hanno la precedenza sulle impostazioni configurate nell'ambito globale. Supponiamo ad esempio che il monitoraggio CDR sia abilitato nell'ambito globale, ma disabilitato nell'ambito del sito (per il sito Redmond). Ciò significa che le informazioni relative alla registrazione dei dettagli delle chiamate non verranno archiviate per gli utenti nel sito Redmond. Tuttavia, gli utenti di altri siti, ovvero gli utenti gestiti dalle impostazioni globali anziché dalle impostazioni del sito Redmond, riceveranno le informazioni di registrazione dei dettagli delle chiamate archiviate.
  
Le nuove impostazioni di configurazione QoE possono essere create nell'ambito del sito usando un comando come questo:
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

Per altre informazioni, digita i comandi seguenti in Skype for Business Server Management Shell:
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
