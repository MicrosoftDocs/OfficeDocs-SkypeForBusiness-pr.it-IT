---
title: Download e installazione di Windows PowerShell 3.0
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Download, install, and then use Windows PowerShell 3.0 to create a remote PowerShell session that connects to Skype for Business Online.
ms.openlocfilehash: 9c2b0f02d9da7e44cdb5585314c13a6bafbe58c6
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568323"
---
# <a name="download-and-install-windows-powershell-30"></a>Download e installazione di Windows PowerShell 3.0

[] Se usi Windows 8.1, Windows 8, Windows Server 2012 R2 o Windows Server 2012, dovresti già avere Windows PowerShell 3.0, perché è un'applicazione preinstallata in quei sistemi operativi. 
  
Se usi Windows 7 o Windows Server 2008 R2, è possibile che tu stia già usando Windows PowerShell 3.0. Tuttavia, è anche possibile che tu abbia invece la versione 2.0, cioè la versione originariamente in dotazione con quei sistemi operativi. Per sapere quale versione di Microsoft PowerShell stai usando, procedi come segue sul tuo computer con Windows 7 o Windows Server 2008 R2.
  
1. Fai clic su **Start**, fai clic su **Tutti i programmi**, fai clic su **Accessori**, fai clic su **Windows PowerShell** e poi fai clic su **Windows PowerShell**.
    
2. Nella console PowerShell, digita il comando seguente e poi premi INVIO:
    
   ```
   Get-Host | Select-Object Version
   ```

3. La finestra della console mostrerà informazioni simili a quelle seguenti:
    
    <pre>
    Version <BR>
    ------- <BR>
    3.0
    </pre>

    Se il numero di versione indicato è 3.0, allora stai usando Windows PowerShell 3.0. Se il numero di versione indicato non è 3.0, allora dovrai installare Windows PowerShell 3.0. Puoi scaricare Windows Management Framework 3.0, che include Windows PowerShell 3.0, dall'[Area download Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
Dopo aver verificato che Windows PowerShell 3.0 è installato, dovrai assicurarti che PowerShell sia configurato per eseguire script remoti. Per farlo, avvia PowerShell come amministratore. Su Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2, procedi come segue.
  
1. Fai clic su **Start**, fai clic su **Tutti i programmi**, fai clic su **Accessori**, fai clic su **Windows PowerShell**, fai clic con il pulsante destro su **Windows PowerShell** e poi fai clic su **Esegui come amministratore**.
    
2. Se viene visualizzata la finestra di dialogo **Controllo dell'account utente**, fai clic su **Sì** per confermare che vuoi eseguire PowerShell con credenziali da amministratore.
    
Se invece usi Windows 8, procedi come segue.
  
1. Accedi alla barra Accessi, fai clic su **Cerca**, quindi fai clic con il pulsante destro su **Windows PowerShell**. Per accedere rapidamente alla barra Accessi su qualsiasi computer con Windows 8 (con o senza touch screen), tieni premuto il tasto Windows e premi C.
    
2. Nella barra degli strumenti nella parte inferiore dello schermo, fai clic su **Esegui come amministratore**.
    
3. Se viene visualizzata la finestra di dialogo **Controllo dell'account utente**, fai clic su **Sì** per confermare che vuoi eseguire PowerShell con credenziali da amministratore.
    
Una volta che PowerShell è in esecuzione, devi modificare il criterio di esecuzione in modo da consentire l'esecuzione di script remoti. Nella console PowerShell, digita il comando seguente e poi premi INVIO:
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> Quando si esegue il comando precedente, potrebbe essere visualizzato il messaggio di errore: > *Set-ExecutionPolicy: accesso alla chiave del Registro di sistema ' HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' viene negata.* Questo messaggio di errore si verifica in genere se non si esegue PowerShell con credenziali di amministratore. Chiudi la sessione di PowerShell e avvia una nuova sessione come amministratore.
 
Per verificare che il criterio di esecuzione sia stato configurato correttamente, digita quanto segue al prompt di PowerShell e premi INVIO:
  
```
Get-ExecutionPolicy
```

Se ottieni il valore seguente, tutto è configurato correttamente:
  
`RemoteSigned`

Se al momento non stai usando Windows PowerShell 3.0, dovrai anche scaricare e installare Windows Management Framework 3.0 dall'Area download Microsoft. Si tratta di un pacchetto di installazione che include Windows PowerShell 3.0 e Windows Remote Management (WinRM) 3.0. Questo pacchetto di installazione potrebbe essere necessario se stai usando Windows 7 e non hai ancora aggiornato a Windows PowerShell 3.0. Se stai usando Windows Server 2012, Windows Server 2012 R2, Windows 8 o Windows 8.1, non dovrebbe essere necessario installare Windows PowerShell 3.0. Windows PowerShell 3.0 è preinstallato su quei sistemi operativi.
  
Prima di installare Windows Management Framework 3.0:
  
- Accertati di aver scaricato la versione corretta del pacchetto di installazione. Se stai usando la versione a 64 bit di Windows 7, scarica il file Windows6.1-KB2506143-x64.msu. Se stai usando la versione a 32 bit di Windows 7, scarica il file Windows6.1-KB2506143-x86.msu.
    
- Se usi Windows 7 sul tuo computer, accertati di aver installato Windows 7 Service Pack 1.
    
Se non sei sicuro della versione di Windows in uso o non sei sicuro di aver installato Windows 7 Service Pack 1, fai click su **Start**, fai clic con il pulsante destro su **Computer**, poi fai clic su **Proprietà**. Queste informazioni saranno riportate nella finestra di dialogo Sistema.
  
Per installare Windows Management Framework 3.0, procedi come segue.
  
1. Fai doppio clic sul file di installazione .MSU ( **Windows6.1-KB2506143-x64.msu** oppure **Windows6.1-KB2506143-x86.msu**).
    
2. Nella procedura guidata Scarica e installa aggiornamenti, nella pagina **Leggere le condizioni di licenza (1 di 1)**, fai clic su **Accetto**.
    
3. Una volta completata l'installazione, fai clic su **Riavvia ora** per riavviare il computer.
    
Una volta riavviato il computer, verifica che Windows PowerShell si avvii e che possa essere eseguito con credenziali di amministratore. Procedi come segue.
  
1. Fai clic su **Start**, fai clic su **Tutti i programmi**, fai clic su **Accessori**, fai clic su **Windows PowerShell**, fai clic con il pulsante destro su **Windows PowerShell** e poi fai clic su **Esegui come amministratore**.
    
2. Se viene visualizzata la finestra di dialogo Controllo dell'account utente, fai clic su **Sì** per confermare che vuoi eseguire PowerShell con credenziali da amministratore.
    
Quando viene visualizzata la console PowerShell, verifica che il servizio WinRM sia in esecuzione e sia stato configurato correttamente. Per verificare che il servizio sia in esecuzione, digita il comando seguente al prompt di PowerShell e poi premi INVIO:
  
```
Get-Service winrm
```

Verranno quindi visualizzate sullo schermo informazioni sul servizio WinRM:
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

Se lo Stato del servizio non è "In esecuzione", digita il comando seguente e premi INVIO per avviare il servizio WinRM:
  
```
Start-Service winrm
```

Una volta avviato il servizio, esegui il comando seguente per verificare che WinRM stia usando l'Autenticazione di base:
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Lo schermo mostrerà informazioni simili a quelle seguenti:
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

Se l'autenticazione di base è stata impostata su true, quindi si è pronti per utilizzare PowerShell per connettersi a Skype Business online.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>See also
[Configurare il computer per Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 