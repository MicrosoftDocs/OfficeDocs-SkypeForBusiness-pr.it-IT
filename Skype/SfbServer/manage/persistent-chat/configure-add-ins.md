---
title: Configurare i componenti aggiuntivi per le chat room di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Riepilogo: informazioni su come configurare i componenti aggiuntivi per le chat room del server di chat persistenti in Skype for Business Server 2015.'
ms.openlocfilehash: c7243184f273704335dda3c8709de17e767f6b51
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992111"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Configurare i componenti aggiuntivi per le chat room di Chat persistente
 
**Riepilogo:** Informazioni su come configurare i componenti aggiuntivi per le chat room del server di chat persistenti in Skype for Business Server 2015.
  
I componenti aggiuntivi vengono usati per estendere l'esperienza in camera associando gli URL alle chat room. Questi URL vengono visualizzati nel riquadro Extensibility della conversazione client. Un componente aggiuntivo tipico può includere un URL che punta a un'applicazione Silverlight che intercetta quando un ticker del titolo viene inserito in una chat room e Mostra la cronologia del titolo nel riquadro estensibilità. Altri esempi sono l'incorporamento di un URL di OneNote 2013 nella chat room come componente aggiuntivo per includere contenuto condiviso, ad esempio "In primo piano" o "Argomento del giorno".
  
 Prima che gli utenti possano vedere un componente aggiuntivo nel client, è necessario aggiungere il componente aggiuntivo all'elenco di componenti aggiuntivi registrati e i responsabili delle chat room o i creatori devono associare le camere al componente aggiuntivo.
  
> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Configurare i componenti aggiuntivi per le chat room tramite il pannello di controllo

Per configurare i componenti aggiuntivi per le chat room tramite il pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.
    
2. Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Componente aggiuntivo**.
    
    Per più distribuzioni di pool di server di chat persistenti, selezionare il pool appropriato nell'elenco a discesa.
    
4. Nella pagina **Componente aggiuntivo** fare clic su **Nuovo**.
    
5. In **Seleziona un servizio**selezionare il servizio corrispondente al pool del server di chat persistente in cui è necessario creare il componente aggiuntivo. I componenti aggiuntivi non possono essere spostati da un pool a un altro o condivisi da pool diversi.
    
6. In **Nuovo componente aggiuntivo** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per il nuovo componente aggiuntivo.
    
   - In **URL** specificare l'URL da associare al componente aggiuntivo. Gli URL sono limitati ai protocolli http e HTTPS.
    
7. Fare clic su **Commit**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Configurare i componenti aggiuntivi tramite Windows PowerShell

Puoi configurare i componenti aggiuntivi per le chat room usando i cmdlet di Windows PowerShell seguenti. Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, Vedi [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Creare un nuovo componente aggiuntivo  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configurare le impostazioni per un componente aggiuntivo esistente  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recuperare informazioni sui componenti aggiuntivi  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Rimuovere un componente aggiuntivo  <br/> |
   
### <a name="create-a-new-add-in"></a>Creare un nuovo componente aggiuntivo

Puoi creare un nuovo componente aggiuntivo usando il cmdlet **New-CsPersistentChatAddin** .
  
Ad esempio, il comando seguente crea un nuovo componente aggiuntivo (con il nome ITPersistentChatAddin) per il pool atl-cs-001.contoso.com. Il parametro URL e il valore http://atl-cs-001.contoso.com/itchat del parametro specificano la posizione della pagina Web del componente aggiuntivo:
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Configurare le impostazioni per un componente aggiuntivo esistente

Puoi configurare le impostazioni per un componente aggiuntivo esistente usando il cmdlet **set-CsPersistentChatAddIn** . Ad esempio, il comando seguente modifica l'URL assegnato al componente aggiuntivo chat persistente ITPersistentChatAddin. In questo caso, l'URL viene modificato inhttp://atl-cs-001.contoso.com/itchat2:
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Recuperare informazioni sui componenti aggiuntivi

Puoi ottenere informazioni sui componenti aggiuntivi usando il cmdlet **Get-CsPersistentChatAddin** . Ad esempio, il comando seguente restituisce informazioni su tutti i componenti aggiuntivi della chat persistente configurati per l'uso nell'organizzazione:
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Rimuovere un componente aggiuntivo

Puoi rimuovere un componente aggiuntivo usando il cmdlet **Remove-CsPersistentChatAddIn** . Ad esempio, il comando seguente rimuove il componente aggiuntivo della chat persistente ITChatAddin trovato nel pool atl-cs-001.contoso.com:
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


