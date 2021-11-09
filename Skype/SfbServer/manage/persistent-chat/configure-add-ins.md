---
title: Configurare i componenti aggiuntivi per le chat room di Persistent Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Riepilogo: informazioni su come configurare i componenti aggiuntivi per le chat room del server Chat persistente Skype for Business Server 2015.'
ms.openlocfilehash: c23a0dd11d51bbfa1c49d8a910decda5be0ac48f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854300"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Configurare i componenti aggiuntivi per le chat room di Persistent Chat in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come configurare i componenti aggiuntivi per le chat room del server Chat persistente in Skype for Business Server 2015.
  
I componenti aggiuntivi vengono utilizzati per estendere l'esperienza in sala associando gli URL alle chat room. Questi URL vengono visualizzati nel riquadro di estendibilità della conversazione client. Un componente aggiuntivo tipico può includere un URL che punta a un'applicazione Silverlight che intercetta quando un ticker di azioni viene pubblicato in una chat room e mostra la cronologia delle azioni nel riquadro di estendibilità. Tra gli altri esempi c'è l'integrazione di un URL OneNote 2013 nella chat room in forma di componente aggiuntivo, per includere un contesto condiviso, ad esempio "Di facile riconoscibilità" o "Argomento del giorno".
  
 Prima che gli utenti possano visualizzare un componente aggiuntivo nel client, è necessario aggiungerlo all'elenco dei componenti aggiuntivi registrati e i responsabili o i creatori delle chat room devono associare le chat room al componente aggiuntivo.
  
> [!NOTE]
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Configurare i componenti aggiuntivi per le chat room tramite il Pannello di controllo

Per configurare i componenti aggiuntivi per le chat room tramite il Pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il pannello di Skype for Business Server o apri una finestra del browser e quindi immetti l'URL amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Componente aggiuntivo**.
    
    Per più distribuzioni di pool di server Chat persistente, selezionare il pool appropriato nell'elenco a discesa.
    
4. Nella pagina **Componente aggiuntivo** fare clic su **Nuovo**.
    
5. In **Selezionare un servizio** selezionare il servizio corrispondente al pool di server Chat persistente in cui è necessario creare il componente aggiuntivo. I componenti aggiuntivi non possono essere spostati da un pool all'altro o condivisi tra diversi pool.
    
6. In **Nuovo componente aggiuntivo** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per il nuovo componente aggiuntivo.
    
   - In **URL** specificare l'URL da associare al componente aggiuntivo. Gli URL sono limitati ai protocolli http e https.
    
7. Fare clic su **Commit**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Configurare i componenti aggiuntivi tramite Windows PowerShell

È possibile configurare i componenti aggiuntivi per le chat room utilizzando i cmdlet Windows PowerShell seguenti. Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, [vedere Skype for Business Server 2015 Management Shell.](../management-shell.md)
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Creare un nuovo componente aggiuntivo  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configurare le impostazioni per un componente aggiuntivo esistente  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recuperare informazioni sui componenti aggiuntivi  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Rimuovere un componente aggiuntivo  <br/> |
   
### <a name="create-a-new-add-in"></a>Creare un nuovo componente aggiuntivo

È possibile creare un nuovo componente aggiuntivo utilizzando il cmdlet **New-CsPersistentChatAddin.**
  
Ad esempio, il comando seguente crea un nuovo componente aggiuntivo (con il nome ITPersistentChatAddin) per il `atl-cs-001.contoso.com` pool. Il parametro URL e il valore del parametro specificano il percorso della pagina Web `http://atl-cs-001.contoso.com/itchat` del componente aggiuntivo:
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Configurare le impostazioni per un componente aggiuntivo esistente

È possibile configurare le impostazioni per un componente aggiuntivo esistente utilizzando il cmdlet **Set-CsPersistentChatAddIn.** Ad esempio, il comando seguente modifica l'URL assegnato al componente aggiuntivo di Persistent Chat ITPersistentChatAddin. In questo caso, l'URL viene modificato in `http://atl-cs-001.contoso.com/itchat2` :
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Recuperare informazioni sui componenti aggiuntivi

È possibile ottenere informazioni sui componenti aggiuntivi utilizzando il cmdlet **Get-CsPersistentChatAddin.** Ad esempio, il comando seguente restituisce informazioni su tutti i componenti aggiuntivi di Persistent Chat configurati per l'utilizzo nell'organizzazione:
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Rimuovere un componente aggiuntivo

È possibile rimuovere un componente aggiuntivo utilizzando il cmdlet **Remove-CsPersistentChatAddIn.** Ad esempio, il comando seguente rimuove il componente aggiuntivo di Persistent Chat ITChatAddin trovato nel `atl-cs-001.contoso.com` pool:
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


