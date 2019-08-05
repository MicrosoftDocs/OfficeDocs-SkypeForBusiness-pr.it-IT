---
title: Skype for Business Server Management Shell
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype for Business Server Management Shell offre l'interfaccia della riga di comando per l'amministrazione e la gestione dei server. È basato su Windows PowerShell e include un set completo di cmdlet di gestione e amministrazione specifici per i prodotti Skype e legacy Lync Server.
ms.openlocfilehash: ce031b15e2146036d77c7336aa9c2b73f000fe4a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188606"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server Management Shell
 
Skype for Business Server Management Shell offre l'interfaccia della riga di comando per l'amministrazione e la gestione dei server. È basato su Windows PowerShell e include un set completo di cmdlet di gestione e amministrazione specifici per i prodotti Skype e legacy Lync Server.
  
Windows PowerShell consente di gestire le applicazioni Microsoft dalla riga di comando. Include un ambiente da riga di comando, comandi specifici del prodotto e un linguaggio di script completo. Windows PowerShell è stato introdotto per la prima volta come versione scaricabile per il sistema operativo Windows in ritardo in 2006 ed è stato incorporato come interfaccia della riga di comando per la gestibilità di Microsoft Exchange Server 2007. È stata incorporata nella maggior parte dei prodotti Microsoft Server, inclusi i server Lync e Skype che iniziano con Lync Server 2010. In Skype for Business Server Management Shell sono disponibili più di 700 cmdlet specifici di Lync e Skype.
  
> [!NOTE]
> Il riferimento ai cmdlet di Skype for business è stato spostato in docs.microsoft.com. Facendo clic sui collegamenti seguenti si accede alla nuova pagina di docs.microsoft.com. Il contenuto è ora aperto e disponibile per i contributi della community tramite GitHub. Vuoi contribuire? Vedere il file README nel repository qui:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server viene fornito con più di 700 cmdlet che consentono agli amministratori di gestire Skype for Business Server con Skype for Business Server Management Shell. È possibile recuperare la guida per un cmdlet direttamente dalla riga di comando digitando un comando simile al seguente:
  
```
Get-Help New-CsVoicePolicy -Full
```

Il comando precedente recupera la guida completa disponibile per il cmdlet **New-CsVoicePolicy** . Per visualizzare la guida per un cmdlet diverso, sostituire **New-CsVoicePolicy** con il nome del cmdlet per cui si vuole recuperare la guida.
  
Per recuperare un elenco completo dei cmdlet disponibili per la gestione di Skype for Business Server, digitare quanto segue al prompt dei comandi della shell: 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Informazioni da sapere su Windows PowerShell in Skype for Business Server:
  
- Per eseguire i cmdlet di Skype for Business Server, aprire Skype for Business Server Management Shell.
    
    > [!CAUTION]
    > Se si apre una finestra di Windows PowerShell invece di Skype for Business Server Management Shell, per impostazione predefinita potrebbe non essere possibile eseguire i cmdlet Skype. Per eseguire i cmdlet di Skype for Business Server da Windows PowerShell, digitare quanto segue al prompt dei comandi di Windows PowerShell: >`Import-Module SkypeforBusiness`
  
- Skype for Business Server Management Shell viene installato automaticamente in ogni server Skype for Business Server Enterprise Edition front-end o Standard Edition.
    
- Puoi aggiornare il contenuto della Guida di Skype for Business Server Management Shell eseguendo il cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) . Il cmdlet Update-Help Scarica e installa i file della guida più recenti disponibili per tutti i moduli installati nel computer, inclusi gli aggiornamenti ai cmdlet di Skype for business.
    
    Per impostazione predefinita, il cmdlet **Update-Help** aggiornerà tutti i moduli installati in Skype for Business Server. Per aggiornare soltanto alcuni moduli, è possibile usare il parametro _Module_ per limitare l'ambito del cmdlet. L'esempio seguente aggiorna solo il modulo Skype for business.
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    Se è necessario aggiornare la guida per i server che non sono connessi a Internet, è possibile usare il cmdlet [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) per ottenere la versione più recente della guida e salvarla in un percorso specificato. È quindi possibile usare il cmdlet **Update-Help** con il parametro _-SourcePath_ nei server non connessi a Internet per ottenere la guida aggiornata dalla posizione selezionata. L'esempio seguente mostra come salvare i file della Guida in una condivisione file di rete e quindi aggiornare la guida per il modulo Skype for business dalla condivisione file.
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Per informazioni più dettagliate, vedere informazioni [sulla guida aggiornabile](https://technet.microsoft.com/library/hh847735.aspx).
    
    > [!NOTE]
    > Se si usa PowerShell in remoto, potrebbe essere necessario consentire la comunicazione tramite un firewall. Per altre informazioni sui servizi remoti di PowerShell per le porte, vedere [quale porta viene usata da PowerShell remoting?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    

