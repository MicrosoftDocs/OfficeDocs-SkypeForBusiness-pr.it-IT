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
description: Skype for Business Server Management Shell fornisce l'interfaccia della riga di comando per l'amministrazione e la gestione del server. È basato su Windows PowerShell e include un insieme completo di cmdlet per la gestione e l'amministrazione specifici per i prodotti Lync Server legacy e Skype.
ms.openlocfilehash: 0653faa542bc9bc579bd7617e40d3efed030569f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816536"
---
# <a name="skype-for-business-server-management-shell"></a>Skype for Business Server Management Shell
 
Skype for Business Server Management Shell fornisce l'interfaccia della riga di comando per l'amministrazione e la gestione del server. È basato su Windows PowerShell e include un insieme completo di cmdlet per la gestione e l'amministrazione specifici per i prodotti Lync Server legacy e Skype.
  
Windows PowerShell consente di gestire le applicazioni Microsoft dalla riga di comando. Include un ambiente da riga di comando, comandi specifici del prodotto e un linguaggio di script completo. Windows PowerShell è stato introdotto per la prima volta come versione scaricabile per il sistema operativo Windows alla fine del 2006 ed è stato incorporato come interfaccia della riga di comando per la gestibilità di Microsoft Exchange Server 2007. È stato incorporato nella maggior parte dei prodotti Microsoft Server, inclusi i server Lync e Skype che iniziano con Lync Server 2010. Sono disponibili più di 700 cmdlet specifici di Lync e Skype in Skype for Business Server Management Shell.
  
> [!NOTE]
> La Guida di riferimento ai cmdlet di Skype for business è stata spostata in docs.microsoft.com. Facendo clic sui collegamenti riportati di seguito, è possibile utilizzare la nuova pagina di docs.microsoft.com. Il contenuto è ora Open Source e disponibile per i contributi comunitari tramite GitHub. Interessati a contribuire? Consultare il file README nel repo qui: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server viene fornito con più di 700 cmdlet che consentono agli amministratori di gestire Skype for Business Server tramite Skype for Business Server Management Shell. È possibile recuperare la guida per un cmdlet direttamente dalla riga di comando digitando un comando simile al seguente:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

Il comando precedente consente di recuperare le informazioni complete della Guida per il cmdlet **New-CsVoicePolicy**. Per visualizzare le informazioni della Guida per un altro cmdlet, sostituire **New-CsVoicePolicy** con il nome del cmdlet in questione.
  
Per recuperare un elenco completo dei cmdlet disponibili per la gestione di Skype for Business Server, al prompt dei comandi di Shell digitare quanto segue: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Aspetti da sapere su Windows PowerShell in Skype for Business Server:
  
- Per eseguire i cmdlet di Skype for Business Server, aprire la shell di gestione di Skype for Business Server.
    
    > [!CAUTION]
    > Se si apre una finestra di Windows PowerShell anziché Skype for Business Server Management Shell, per impostazione predefinita potrebbe non essere possibile eseguire i cmdlet Skype. Per eseguire i cmdlet di Skype for Business Server dall'interno di Windows PowerShell, digitare il comando seguente al prompt dei comandi di Windows PowerShell: >  `Import-Module SkypeforBusiness`
  
- Skype for Business Server Management Shell viene installato automaticamente in tutti i server Skype for Business Server Enterprise Edition Front End Server o Standard Edition.
    
- È possibile aggiornare il contenuto della Guida di Skype for Business Server Management Shell eseguendo il cmdlet [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) . Il cmdlet Update-Help consente di scaricare e installare i file della guida più recenti disponibili per tutti i moduli installati nel computer, inclusi gli aggiornamenti ai cmdlet di Skype for business.
    
    Per impostazione predefinita, il cmdlet **Update-Help** aggiornerà tutti i moduli installati nel server Skype for business. Se si desidera aggiornare solo alcuni moduli, è possibile utilizzare il parametro _Module_ per limitare l'ambito del cmdlet. Nell'esempio seguente viene aggiornato solo il modulo Skype for business.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Se è necessario aggiornare la guida sui server che non sono connessi a Internet, è possibile utilizzare il cmdlet [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) per ottenere la versione più recente della guida e salvarla in una posizione specificata. È quindi possibile utilizzare il cmdlet **Update-Help** con il parametro _-SourcePath_ nei server non connessi a Internet per ottenere la guida aggiornata dal percorso selezionato. Nell'esempio seguente viene illustrato come salvare i file della Guida in una condivisione file di rete e quindi aggiornare la guida per il modulo Skype for business dalla condivisione file.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Per informazioni più dettagliate, vedere [informazioni sulla guida aggiornabile](https://technet.microsoft.com/library/hh847735.aspx).
    
    > [!NOTE]
    > Se si utilizza PowerShell in remoto, potrebbe essere necessario consentire la comunicazione tramite un firewall. Per ulteriori informazioni sui servizi remoti di PowerShell per le porte, vedere [quale porta utilizza la comunicazione remota di PowerShell?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    

