---
title: Configurare i componenti aggiuntivi per le chat room permanenti in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Riepilogo: informazioni su come configurare i componenti aggiuntivi per le chat room del server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 1aca54f3db1229527256d1e2801cb057f4f79387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815082"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Configurare i componenti aggiuntivi per le chat room permanenti in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come configurare i componenti aggiuntivi per le chat room del server Chat persistente in Skype for Business Server 2015.
  
I componenti aggiuntivi vengono utilizzati per estendere l'esperienza in sala associando gli URL alle chat room. Questi URL vengono visualizzati nel riquadro Extensibility di conversazione client. Un componente aggiuntivo tipico potrebbe includere un URL che punta a un'applicazione Silverlight che intercetta quando un ticker di stock viene inserito in una chat room e visualizza la cronologia del magazzino nel riquadro Extensibility. Tra gli altri esempi c'è l'integrazione di un URL OneNote 2013 nella chat room in forma di componente aggiuntivo, per includere un contesto condiviso, ad esempio "Di facile riconoscibilità" o "Argomento del giorno".
  
 Prima che gli utenti possano visualizzare un componente aggiuntivo nel client, è necessario aggiungere il componente aggiuntivo all'elenco dei componenti aggiuntivi registrati e i responsabili delle chat room o i creatori devono associare le sale al componente aggiuntivo.
  
> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Configurare i componenti aggiuntivi per le chat room utilizzando il pannello di controllo

Per configurare i componenti aggiuntivi per le chat room utilizzando il pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Componente aggiuntivo**.
    
    Per più distribuzioni di pool di server Chat persistente, selezionare il pool appropriato dall'elenco a discesa.
    
4. Nella pagina **Componente aggiuntivo** fare clic su **Nuovo**.
    
5. In **Seleziona un servizio** selezionare il servizio corrispondente al pool di server Chat persistente in cui è necessario creare il componente aggiuntivo. I componenti aggiuntivi non possono essere spostati da un pool all'altro o condivisi tra diversi pool.
    
6. In **Nuovo componente aggiuntivo** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per il nuovo componente aggiuntivo.
    
   - In **URL** specificare l'URL da associare al componente aggiuntivo. Gli URL sono limitati ai protocolli http e HTTPS.
    
7. Fare clic su **Commit**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Configurare i componenti aggiuntivi tramite Windows PowerShell

È possibile configurare i componenti aggiuntivi per le chat room utilizzando i cmdlet di Windows PowerShell seguenti. Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, vedere [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Creare un nuovo componente aggiuntivo  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configurare le impostazioni per un componente aggiuntivo esistente  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recuperare informazioni sui componenti aggiuntivi  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Rimuovere un componente aggiuntivo  <br/> |
   
### <a name="create-a-new-add-in"></a>Creare un nuovo componente aggiuntivo

È possibile creare un nuovo componente aggiuntivo utilizzando il cmdlet **New-CsPersistentChatAddin** .
  
Ad esempio, il comando seguente crea un nuovo componente aggiuntivo (con il nome ITPersistentChatAddin) per il pool atl-cs-001.contoso.com. Il parametro URL e il valore del parametro http://atl-cs-001.contoso.com/itchat specificano il percorso della pagina Web del componente aggiuntivo:
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Configurare le impostazioni per un componente aggiuntivo esistente

È possibile configurare le impostazioni per un componente aggiuntivo esistente utilizzando il cmdlet **set-CsPersistentChatAddIn** . Ad esempio, il comando seguente consente di modificare l'URL assegnato al componente aggiuntivo chat persistente ITPersistentChatAddin. In questo caso, l'URL viene modificato in http://atl-cs-001.contoso.com/itchat2:
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Recuperare informazioni sui componenti aggiuntivi

È possibile ottenere informazioni sui componenti aggiuntivi utilizzando il cmdlet **Get-CsPersistentChatAddin** . Ad esempio, il comando seguente restituisce informazioni su tutti i componenti aggiuntivi di Persistent Chat configurati per l'utilizzo nell'organizzazione:
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Rimuovere un componente aggiuntivo

È possibile rimuovere un componente aggiuntivo utilizzando il cmdlet **Remove-CsPersistentChatAddIn** . Ad esempio, il comando seguente consente di rimuovere il componente aggiuntivo di Persistent Chat ITChatAddin trovato nel pool atl-cs-001.contoso.com:
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


