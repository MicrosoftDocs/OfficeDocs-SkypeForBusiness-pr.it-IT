---
title: Creare impostazioni di configurazione della qualità delle esperienze in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Riepilogo: informazioni sulle impostazioni di qualità delle esperienze (QoE) in Skype for Business Server.'
ms.openlocfilehash: 254e6f1032026f715c30017f984bc2906f46e0df
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992793"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Creare impostazioni di configurazione della qualità delle esperienze in Skype for Business Server
 
**Riepilogo:** Informazioni sulle impostazioni di qualità delle esperienze (QoE) in Skype for Business Server.
  
Le metriche sulla qualità delle esperienze (QoE) tengono traccia della qualità delle chiamate audio e video effettuate nell'organizzazione, tra cui il numero di pacchetti di rete persi, il rumore di fondo e la quantità di "jitter" (differenze nel ritardo del pacchetto). Queste metriche sono archiviate in un database, oltre ad altri dati, ad esempio i record dettagli chiamata, che consentono di abilitare e disabilitare QoE indipendentemente da altre registrazioni di dati.
  
Quando si installa Skype for Business Server, viene creata una singola raccolta globale di impostazioni di configurazione QoE. Gli amministratori hanno anche la possibilità di creare impostazioni personalizzate nell'ambito del sito. Ogni volta che vengono usate queste impostazioni con ambito sito, hanno la precedenza sulle impostazioni globali. Ad esempio, se crei impostazioni con ambito sito per il sito Redmond, le impostazioni (invece delle impostazioni globali) verranno usate per gestire i QoE in Redmond.
  
Le impostazioni di configurazione QoE possono essere create usando il pannello di controllo di Skype for Business Server o il cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) . Se si usa il pannello di controllo di Skype for Business Server per creare nuove impostazioni, le opzioni seguenti saranno disponibili:
  
|**Impostazione dell'interfaccia utente**|**Parametro di PowerShell**|**Descrizione**|
|:-----|:-----|:-----|
|Nome  <br/> |Identity  <br/> |Identificatore univoco per le impostazioni da creare. Le impostazioni di configurazione QoE possono essere create solo nell'ambito del sito.  <br/> |
|Abilitare il monitoraggio dei dati QoE  <br/> |EnableQoE  <br/> |Specifica se i record QoE verranno raccolti e salvati nel database di monitoraggio.  <br/> |
|Abilitare l'eliminazione dei dati QoE  <br/> |EnablePurging  <br/> |Specifica se i record verranno eliminati dopo che è trascorso il periodo definito nella proprietà **Mantieni i dati QoE per una durata massima (giorni)** . <br/> |
|Mantieni i dati QoE per la durata massima (giorni)  <br/> |KeepQoEDataForDays  <br/> |Numero di giorni i dati QoE verranno archiviati prima di essere eliminati dal database. Questo valore viene ignorato se l'eliminazione è disabilitata.  <br/> |
   
> [!NOTE]
> Il cmdlet New-CsQoEConfiguration include opzioni aggiuntive non disponibili nel pannello di controllo di Skype for Business Server. Per altre informazioni, vedere l'argomento della Guida [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Per creare impostazioni di configurazione QoE usando il pannello di controllo di Skype for Business Server

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere **delegare le autorizzazioni di configurazione**.
    
2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.  
    
3. Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.
    
4. Nella pagina **qualità di dati esperienza** fare clic su **nuovo**.
    
5. In **Seleziona un sito**fare clic sul sito a cui applicare il criterio e fare clic su **OK**.
    
6. Nell' **impostazione nuova qualità dell'esperienza**, eseguire le operazioni seguenti:
    
   - Selezionare **Abilita il monitoraggio dei dati QoE** per attivare il monitoraggio.
    
   - Selezionare **Abilita l'eliminazione dei dati QoE** per attivare l'eliminazione.
    
   - In **Mantieni QoE per la durata massima (giorni)** selezionare il numero massimo di giorni in cui devono essere conservati i record QoE.
    
7. Fare clic su **Commit**.
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione di impostazioni di configurazione QoE con i cmdlet di Windows PowerShell

Puoi creare impostazioni di configurazione QoE usando Windows PowerShell e il cmdlet New-CsQoEConfiguration. Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Per creare una nuova raccolta di impostazioni di configurazione QoE

 Questo comando crea una nuova raccolta di impostazioni di configurazione QoE applicate al sito Redmond:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Per creare una nuova raccolta di impostazioni di configurazione QoE in cui il monitoraggio QoE è disabilitato

 Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per tutte le relative proprietà. Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati. Ad esempio, per creare una raccolta di impostazioni di configurazione della qualità delle esperienze che, per impostazione predefinita, consentono di disabilitare la registrazione QoE usare un comando simile al seguente:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Per specificare più valori di proprietà quando si crea una nuova raccolta di impostazioni di configurazione QoE

 Puoi includere più valori di proprietà includendo più parametri. Ad esempio, questo comando Configura le nuove impostazioni per conservare i dati QoE per 30 giorni e per eliminare i vecchi dati in 3:00 AM:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .
  

