---
title: "Download e installazione del modulo Skype for Business Online Connector"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
description: "Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online.
"
---

# Download e installazione del modulo Skype for Business Online Connector

Modulo del connettore di Skype for Business Online include il cmdlet **New-CsOnlineSession**, che consente di creare una sessione Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo sui computer a 64 bit (vedere[Configurare il computer per Skype per Business Online gestione usando Windows PowerShell](set-up-your-computer-for-skype-for-business-online-management-using-windows-powe.md) per maggiori informazioni), può essere scaricato dall'Area download Microsoft all'indirizzo[https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Scarica il file SkypeOnlinePowershell.exe, poi procedi come segue.
  
1. Fai doppio clic sul file **SkypeOnlinePowershell.exe**.
    
2. Nell'installazione guidata di Skype for Business online, Windows PowerShell, nella pagina **Condizioni di licenza software Microsoft**, seleziona **Accetto i termini del Contratto di licenza**, poi fai clic su **Installa**. Se viene visualizzata la finestra di dialogo **Controllo dell'account utente**, fai clic su **Sì** per continuare l'installazione.
    
3. Nella pagina **Skype for Business Online, modulo Windows PowerShell completato**, fai clic su **Fine**.
    
Il programma di installazione copia Modulo del connettore di Skype for Business Online (e il cmdlet **New-CsOnlineSession** ) sul tuo computer. Per accedere al modulo, avvia una sessione di Windows PowerShell con credenziali di amministratore ed esegui il comando seguente:
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

Se non vuoi digitare questo comando ogni volta che avvii Windows PowerShell, puoi aggiungere il comando al profilo di Windows PowerShell. Per farlo, digita il comando seguente al prompt di Windows PowerShell e premi INVIO:
  
```
notepad.exe $profile
```

 Quando viene visualizzato Blocco note, aggiungi la riga seguente dopo i comandi già presenti nel profilo (se ce ne sono):
  
```
Import-Module SkypeOnlineConnector
```

Salva il file. La prossima volta che avvierai Windows PowerShell, Modulo del connettore di Skype for Business Online verrà importato automaticamente. Ricorda che riceverai un messaggio d'errore, e il modulo non verrà caricato, se non stai eseguendo Windows PowerShell con credenziali di amministratore.
  
Oltre a installare Modulo del connettore di Skype for Business Online, SkypeOnlinePowershell.exe installa anche tre componenti aggiuntivi: 1) la libreria IDCRL (Identity Service Client Runtime Library), che gestisce l'autenticazione del client con Skype for Business online; 2) .NET Framework 4.5; e 3) pacchetto Microsoft Visual C++ 2012 Redistributable (x64) Package (versione 11.0.50727). .NET Framework 4.5 offre l'infrastruttura necessaria per compilare ed eseguire le applicazioni .NET, compresa Windows PowerShell. Visual C++ Redistributable Package installa i componenti di runtime di Visual C++ per i computer in cui non è installato Microsoft Visual Studio 2012.
  
Per verificare il numero di versione del modulo Connector attualmente installato sul computer, apri Pannello di controllo, apri **Programmi e funzionalità** e verifica il numero di versione di **Skype for Business Online, modulo Windows PowerShell**.
  

