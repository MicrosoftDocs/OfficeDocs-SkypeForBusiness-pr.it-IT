---
title: Skype for Business Server Management Shell
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Skype for Business Server Management Shell fornisce l'interfaccia della riga di comando per l'amministrazione e la gestione del server. È basato su Windows PowerShell e include un set completo di cmdlet di gestione e amministrazione specifici per Skype e i prodotti server Lync legacy.
ms.openlocfilehash: 24da9ac341129239399ea17218be8547f3549d6f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118585"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server Management Shell
 
Skype for Business Server Management Shell fornisce l'interfaccia della riga di comando per l'amministrazione e la gestione del server. È basato su Windows PowerShell e include un set completo di cmdlet di gestione e amministrazione specifici per Skype e i prodotti server Lync legacy.
  
Windows PowerShell consente di gestire le applicazioni Microsoft dalla riga di comando. Include un ambiente da riga di comando, comandi specifici del prodotto e un linguaggio di script completo. Windows PowerShell è stata introdotta come versione scaricabile per il sistema operativo Windows alla fine del 2006 ed è stata incorporata come interfaccia della riga di comando per la gestibilità di Microsoft Exchange Server 2007. È stato incorporato nella maggior parte dei prodotti Microsoft Server, inclusi i server Lync e Skype a partire da Lync Server 2010. Sono disponibili oltre 700 cmdlet specifici di Lync e Skype in Skype for Business Server Management Shell.
  
> [!NOTE]
> Il riferimento al cmdlet di Skype for Business è stato spostato in docs.microsoft.com. Se si fa clic sui collegamenti seguenti, verrà visualizzata la nuova docs.microsoft.com pagina. Il contenuto è ora open source e disponibile per i contributi della community tramite GitHub. Sei interessato a contribuire? Consultare il file README nel repo qui: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server viene fornito con più di 700 cmdlet che consentono agli amministratori di gestire Skype for Business Server utilizzando Skype for Business Server Management Shell. È possibile recuperare la Guida per un cmdlet direttamente dalla riga di comando digitando un comando simile al seguente:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

Il comando precedente consente di recuperare le informazioni complete della Guida per il cmdlet **New-CsVoicePolicy**. Per visualizzare le informazioni della Guida per un altro cmdlet, sostituire **New-CsVoicePolicy** con il nome del cmdlet in questione.
  
Per recuperare un elenco completo dei cmdlet disponibili per la gestione di Skype for Business Server, digitare quanto segue al prompt dei comandi della shell: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Informazioni sulle Windows PowerShell in Skype for Business Server:
  
- Per eseguire i cmdlet di Skype for Business Server, aprire Skype for Business Server Management Shell.
    
    > [!CAUTION]
    > Se si apre una finestra Windows PowerShell anziché Skype for Business Server Management Shell, per impostazione predefinita potrebbe non essere possibile eseguire i cmdlet di Skype. Per eseguire i cmdlet di Skype for Business Server dall'Windows PowerShell, digitare innanzitutto quanto segue al prompt dei comandi di Windows PowerShell: >  `Import-Module SkypeforBusiness`
  
- Skype for Business Server Management Shell viene installato automaticamente in ogni server Skype for Business Server Enterprise Edition Front End Server o Standard Edition.
    
- È possibile aggiornare il contenuto della Guida di Skype for Business Server Management Shell eseguendo il cmdlet [Update-Help.](/powershell/module/microsoft.powershell.core/update-help) Il cmdlet Update-Help scarica e installa i file della Guida più recenti disponibili per tutti i moduli installati nel computer, inclusi gli aggiornamenti ai cmdlet di Skype for Business.
    
    Per impostazione predefinita, il cmdlet **Update-Help** aggiornerà tutti i moduli installati in Skype for Business Server. Se si desidera aggiornare solo determinati moduli, è possibile utilizzare il _parametro Module_ per limitare l'ambito del cmdlet. Nell'esempio seguente viene aggiornato solo il modulo Skype for Business.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Se è necessario aggiornare la Guida nei server non connessi a Internet, è possibile utilizzare il cmdlet [Save-Help](/powershell/module/microsoft.powershell.core/save-help) per ottenere la versione più recente della Guida e salvarla in un percorso specificato. È quindi possibile utilizzare il cmdlet **Update-Help** con il _parametro -SourcePath_ nei server non connessi a Internet per ottenere la Guida aggiornata dal percorso selezionato. L'esempio seguente mostra come salvare i file della Guida in una condivisione file di rete e quindi aggiornare la Guida per il modulo Skype for Business dalla condivisione file.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Per informazioni più dettagliate, vedere [Informazioni sulla Guida aggiornabile.](/powershell/module/microsoft.powershell.core/about/about_updatable_help)
    
    > [!NOTE]
    > Se si usa PowerShell in remoto, potrebbe essere necessario consentire la comunicazione tramite un firewall. Per ulteriori informazioni sulle porte usate dalla comunicazione remota di PowerShell, vedere [What Port Does PowerShell Remoting Use?](/archive/blogs/christwe/what-port-does-powershell-remoting-use).
