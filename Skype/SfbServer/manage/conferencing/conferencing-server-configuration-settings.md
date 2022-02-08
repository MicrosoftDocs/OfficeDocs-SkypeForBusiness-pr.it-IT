---
title: Gestire le impostazioni di configurazione del server per conferenze in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Riepilogo: informazioni su come gestire le impostazioni di configurazione del server per conferenze in Skype for Business Server.'
ms.openlocfilehash: 1435c6bd69624d5097d0377ab920ac9fed577072
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393778"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Gestire le impostazioni di configurazione del server per conferenze in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire le impostazioni di configurazione del server per conferenze in Skype for Business Server.
  
In questo argomento viene descritto come gestire le impostazioni di configurazione delle conferenze. Per ulteriori informazioni su come pianificare e distribuire le conferenze, vedere [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Le impostazioni di configurazione delle conferenze determinano elementi quali la dimensione massima consentita per il contenuto e gli stampati delle riunioni; la quantità massima di larghezza di banda per il servizio Conferenza condivisione applicazioni; limiti di archiviazione e periodi di scadenza; gli URL per i download interni ed esterni del client supportato; puntatori a URL interni ed esterni in cui gli utenti possono ottenere informazioni e risorse per le conferenze; e le porte utilizzate per la condivisione delle applicazioni, l'audio client, i trasferimenti di file e il traffico multimediale. Queste impostazioni consentono di gestire i server effettivi. Queste impostazioni possono essere impostate tramite Skype for Business Server Management Shell.
  
Quando si installa Skype for Business Server, il sistema fornisce una singola raccolta di impostazioni di configurazione delle conferenze (la raccolta globale). Se è necessario creare impostazioni personalizzate per un sito o un servizio, è possibile utilizzare il cmdlet **New-CsConferencingConfiguration** per tale scopo. Si noti che le nuove impostazioni possono essere applicate solo nell'ambito del sito o del servizio. non è possibile creare una nuova raccolta globale di impostazioni di configurazione delle conferenze, ma è possibile modificare la raccolta globale utilizzando il cmdlet **Set-CsConferencingConfiguration** . Nessun sito o servizio può inoltre ospitare più di una raccolta di impostazioni. Se si tenta di creare nuove impostazioni per il sito Redmond e il sito Redmond ospita già una raccolta di impostazioni di configurazione delle conferenze, il comando avrà esito negativo.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Gestire le impostazioni di configurazione delle conferenze tramite Skype for Business Server Management Shell

Per gestire le impostazioni di configurazione delle conferenze Skype for Business Server Management Shell, utilizzare i cmdlet seguenti:
  
**Impostazioni di configurazione delle conferenze**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Restituisce informazioni sulle impostazioni di configurazione delle conferenze per l'organizzazione.  <br/> |
|[New-CsConferencingConfiguration](/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione delle conferenze.  <br/> |
|[Remove-CsConferencingConfiguration](/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Rimuove la raccolta specificata di impostazioni di configurazione delle conferenze.  <br/> |
|[Set-CsConferencingConfiguration](/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica una raccolta esistente di impostazioni di configurazione delle conferenze.  <br/> |
   
Il comando seguente crea una nuova raccolta di impostazioni di configurazione delle conferenze per il sito Redmond (site:Redmond). In questo esempio viene incluso un parametro aggiuntivo (Organization) utilizzato per impostare il valore della proprietà Organization su Litwareinc: 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Si noti che è possibile disporre di una sola raccolta di questo tipo per sito, pertanto questo comando avrà esito negativo se il sito Redmond dispone già di una raccolta di impostazioni di configurazione delle conferenze. 
  
Nell'esempio seguente viene definita una nuova raccolta di impostazioni di configurazione delle conferenze, inizialmente archiviate in memoria e quindi applicate al sito Redmond in un secondo momento. 
  
Nel primo comando viene utilizzato il cmdlet **New-CsConferencingConfiguration** per creare una nuova raccolta in memoria di impostazioni archiviate nella variabile $x. Il parametro InMemory consente di specificare che la raccolta deve essere creata in memoria anziché essere immediatamente applicata al sito Redmond.
  
Dopo la creazione della raccolta, il secondo comando imposta il valore della proprietà Organization su Litwareinc. 
  
Infine, il terzo comando utilizza il cmdlet **Set-CsConferencingConfiguration** per applicare effettivamente le nuove impostazioni al sito Redmond:
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Se non si chiama il cmdlet **Set-CsConferencingConfiguration** , le nuove impostazioni non avranno mai effetto. Al contrario, scompariranno non appena terminerai la sessione Windows PowerShell o elimini la variabile $x.
