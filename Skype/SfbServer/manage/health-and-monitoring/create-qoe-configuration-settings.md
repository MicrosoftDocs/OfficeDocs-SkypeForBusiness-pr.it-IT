---
title: Creare le impostazioni di configurazione di Qualità dell'esperienza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Riepilogo: informazioni sulle impostazioni QoE (Quality of Experience) in Skype for Business Server.'
ms.openlocfilehash: 564ab88b349b578cf577893e4119e5e1ebf26fb1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585100"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Creare le impostazioni di configurazione di Qualità dell'esperienza in Skype for Business Server
 
**Riepilogo:** Informazioni sulle impostazioni QoE (Quality of Experience) in Skype for Business Server.
  
La metrica QoE registra la qualità delle chiamate audio e video effettuate nell'organizzazione, includendo informazioni quali il numero di pacchetti di rete persi, i rumori di fondo e il livello di "instabilità" (differenze nel ritardo dei pacchetti). Questa metrica viene archiviata in un database separatamente rispetto ad altri dati, ad esempio la registrazione dettagli chiamata, in modo che sia possibile abilitare e disabilitare il servizio QoE in maniera indipendente rispetto ad altre registrazioni di dati.
  
Quando si installa Skype for Business Server, viene creata automaticamente una singola raccolta globale di impostazioni di configurazione QoE. Gli amministratori hanno inoltre la possibilità di creare impostazioni personalizzato con ambito sito. Ogni volta che vengono utilizzate tali impostazioni con ambito sito, queste avranno la precedenza rispetto alle impostazioni globali. Se si creano impostazioni con ambito sito per il sito Redmond, ad esempio, per gestire i criteri QoE nel sito di Redmond verranno utilizzate tali impostazioni, anziché quelle globali.
  
Le impostazioni di configurazione QoE possono essere create utilizzando Skype for Business Server pannello di controllo o il cmdlet [New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) Se si utilizza il Skype for Business Server di controllo per creare nuove impostazioni, saranno disponibili le opzioni seguenti:
  
|**Impostazione dell'interfaccia utente**|**Parametro di PowerShell**|**Descrizione**|
|:-----|:-----|:-----|
|Nome  <br/> |Identità  <br/> |Identificatore univoco delle impostazioni da creare. Le impostazioni di configurazione QoE possono essere create solo in ambito di sito.  <br/> |
|Abilita monitoraggio dei dati QoE  <br/> |EnableQoE  <br/> |Indica se i record QoE verranno raccolti e salvati nel database di monitoraggio.  <br/> |
|Abilita eliminazione dei dati QoE  <br/> |EnablePurging  <br/> |Indica se i record verranno cancellati dopo la scadenza specificata nella proprietà **Mantieni dati QoE per durata massima (giorni)**. <br/> |
|Mantieni dati QoE per durata massima (giorni)  <br/> |KeepQoEDataForDays  <br/> |Il numero di giorni in cui i dati QoE verranno archiviati prima di essere eliminati dal database. Questo valore viene ignorato se l'eliminazione è disabilitata.  <br/> |
   
> [!NOTE]
> Il cmdlet New-CsQoEConfiguration include opzioni aggiuntive non disponibili Skype for Business Server Pannello di controllo. Per ulteriori informazioni, vedere [l'argomento della Guida New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Per creare le impostazioni di configurazione QoE tramite il Skype for Business Server Pannello di controllo

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **Delegate Setup Permissions**.
    
2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.  
    
3. Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.
    
4. Nella pagina **Dati QoE** fare clic su **Nuovo**.
    
5. In **Seleziona un sito** fare clic sul sito a cui si desidera applicare i criteri e quindi fare clic su **OK**.
    
6. In **Crea nuova impostazione QoE** eseguire le operazioni seguenti:
    
   - Selezionare **Abilita monitoraggio dei dati QoE** per attivare il monitoraggio.
    
   - Selezionare **Abilita eliminazione dei dati QoE** per attivare l'eliminazione.
    
   - In **Mantieni dati QoE per durata massima (giorni)** selezionare il numero massimo di giorni per il mantenimento dei record QoE.
    
7. Fare clic su **Commit**.
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione di Impostazioni QoE tramite i cmdlet Windows PowerShell QoE

È possibile creare impostazioni di configurazione QoE utilizzando Windows PowerShell e il cmdlet New-CsQoEConfiguration QoE. È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remoto per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Per creare una nuova raccolta di impostazioni di configurazione QoE

 Questo comando crea una nuova raccolta di impostazioni di configurazione QoE per il sito Redmond:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Per creare una nuova raccolta di impostazioni di configurazione QoE in cui il monitoraggio QoE è disabilitato

 Dal momento che nel comando precedente non sono stati specificati parametri, oltre al parametro Identity obbligatorio, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per ogni proprietà. Per creare impostazioni che utilizzano valori di proprietà diversi, includere semplicemente il parametro e il valore di parametro appropriato. Per creare una raccolta di impostazioni di configurazione QoE che consenta la disabilitazione della registrazione QoE per impostazione predefinita, utilizzare un comando come il seguente:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Per specificare più valori di proprietà durante la creazione di una nuova raccolta di impostazioni di configurazione QoE

 È possibile specificare più valori di proprietà includendo più parametri. Questo comando, ad esempio, configura le nuove impostazioni per mantenere i dati QoE per 30 giorni ed eliminare i dati obsoleti alle 3.00:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsQoEConfiguration.](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)
