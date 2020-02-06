---
title: Gestire le impostazioni di configurazione del server di conferenza in Skype for Business Server
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
ms.assetid: 36bed690-6e22-4e11-88c1-b40a20836c6a
description: 'Riepilogo: informazioni su come gestire le impostazioni di configurazione del server di conferenza in Skype for Business Server.'
ms.openlocfilehash: c43734a2d79bf07023486eb163fff7bbef56e73f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818637"
---
# <a name="manage-conferencing-server-configuration-settings-in-skype-for-business-server"></a>Gestire le impostazioni di configurazione del server di conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire le impostazioni di configurazione del server di conferenza in Skype for Business Server.
  
Questo argomento descrive come gestire le impostazioni di configurazione delle conferenze. Per altre informazioni su come pianificare e distribuire i servizi di conferenza, vedere [pianificare le conferenze in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) e [distribuire servizi di conferenza in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Le impostazioni di configurazione della conferenza determinano elementi come la dimensione massima consentita per il contenuto della riunione e gli stampati; quantità massima di larghezza di banda per il servizio di conferenza di condivisione applicazioni limiti di spazio di archiviazione e periodi di scadenza; URL per i download interni ed esterni del client supportato; puntatori a URL interni ed esterni in cui gli utenti possono ottenere assistenza e risorse per i servizi di conferenza; e le porte usate per la condivisione delle applicazioni, l'audio client, i trasferimenti di file e il traffico multimediale. Queste impostazioni consentono di gestire i server effettivi. Queste impostazioni possono essere impostate usando Skype for Business Server Management Shell.
  
Quando si installa Skype for Business Server, il sistema offre una singola raccolta di impostazioni di configurazione per i servizi di conferenza (raccolta globale). Se è necessario creare impostazioni personalizzate per un sito o un servizio, è possibile farlo usando il cmdlet **New-CsConferencingConfiguration** . Tieni presente che le nuove impostazioni possono essere applicate solo nell'ambito del sito o del servizio. non è possibile creare una nuova raccolta globale di impostazioni di configurazione per i servizi di conferenza, ma è possibile modificare la raccolta globale usando il cmdlet **Set-CsConferencingConfiguration** . Inoltre, nessun sito o servizio può ospitare più di una raccolta di impostazioni. Se si prova a creare nuove impostazioni per il sito Redmond e il sito Redmond ospita già una raccolta di impostazioni di configurazione per i servizi di conferenza, il comando avrà esito negativo.
  
## <a name="manage-conferencing-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Gestire le impostazioni di configurazione dei servizi di conferenza tramite Skype for Business Server Management Shell

Per gestire le impostazioni di configurazione dei servizi di conferenza tramite Skype for Business Server Management Shell, usare i cmdlet seguenti:
  
**Impostazioni di configurazione per i servizi di conferenza**

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|[Get-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csconferencingconfiguration?view=skype-ps) <br/> |Restituisce informazioni sulle impostazioni di configurazione per i servizi di conferenza per l'organizzazione.  <br/> |
|[New-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csconferencingconfiguration?view=skype-ps) <br/> |Crea una nuova raccolta di impostazioni di configurazione per i servizi di conferenza.  <br/> |
|[Remove-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingconfiguration?view=skype-ps) <br/> |Rimuove la raccolta specificata di impostazioni di configurazione per i servizi di conferenza.  <br/> |
|[Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csconferencingconfiguration?view=skype-ps) <br/> |Modifica una raccolta esistente di impostazioni di configurazione per i servizi di conferenza.  <br/> |
   
Il comando seguente crea una nuova raccolta di impostazioni di configurazione per i servizi di conferenza per il sito Redmond (sito: Redmond). In questo esempio viene incluso un altro parametro (organizzazione) che viene usato per impostare il valore della proprietà Organization su litwareinc: 
  
```PowerShell
New-CsConferencingConfiguration -Identity site:Redmond -Organization Litwareinc
```

Tieni presente che puoi avere una sola raccolta per ogni sito, quindi questo comando non riesce se il sito Redmond ha già una raccolta di impostazioni di configurazione per i servizi di conferenza. 
  
L'esempio seguente definisce una nuova raccolta di impostazioni di configurazione per i servizi di conferenza, archiviate inizialmente in memoria e quindi applicate al sito Redmond in un secondo momento. 
  
Il primo comando usa il cmdlet **New-CsConferencingConfiguration** per creare una nuova raccolta in memoria di impostazioni archiviate nella variabile $x. Il parametro InMemory specifica che la raccolta deve essere creata in memoria piuttosto che applicata immediatamente al sito Redmond.
  
Dopo aver creato la raccolta, il secondo comando imposta il valore della proprietà Organization su litwareinc. 
  
Infine, il terzo comando usa il cmdlet **Set-CsConferencingConfiguration** per applicare effettivamente le nuove impostazioni al sito Redmond:
  
```PowerShell
$x = New-CsConferencingConfiguration -Identity site:Redmond -InMemory
$x.Organization = "Litwareinc"
Set-CsConferencingConfiguration -Instance $x
```

Se non si chiama il cmdlet **Set-CsConferencingConfiguration** , le nuove impostazioni non avranno mai effetto. Scompariranno invece non appena si termina la sessione di Windows PowerShell o si elimina la variabile $x.
  

