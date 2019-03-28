---
title: Scaricare e installare Windows PowerShell 5.1
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Scaricare, installare e quindi utilizzare Windows PowerShell 5.1 per creare una sessione di remote PowerShell che si connette a Skype Business online.
ms.openlocfilehash: 63f4924a30bfc910679f23a617cc5252ecc5b6aa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2019
ms.locfileid: "30926701"
---
# <a name="download-and-install-windows-powershell-51"></a>Scaricare e installare Windows PowerShell 5.1

Se si utilizza Windows 10 anniversario Update o Windows Server 2016, è necessario disporre già 5.1 di Windows PowerShell. Ciò avviene perché questa applicazione preinstallato con tali sistemi operativi.
  
Per determinare quale versione di Microsoft PowerShelll in uso, eseguire le operazioni seguenti nel computer Windows Server 2008 R2 o Windows Server 2012 o Windows 7:
  
1. Fai clic su **Start**, fai clic su **Tutti i programmi**, fai clic su **Accessori**, fai clic su **Windows PowerShell** e poi fai clic su **Windows PowerShell**.
    
2. Nella console PowerShell, digita il comando seguente e poi premi INVIO:
    
   ```
   Get-Host | Select-Object Version
   ```

3. La finestra della console mostrerà informazioni simili a quelle seguenti:
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    Se il numero di versione restituito è 5.1, sono in esecuzione Windows PowerShell 5.1. Se il numero di versione restituito non è 5.1, sarà necessario installare Windows PowerShell 5.1. È possibile scaricare Windows Management Framework 5.1, che include Windows PowerShell 5.1, dall' [Area Download Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=54616).
  
Dopo aver verificato che sia installato Windows PowerShell 5.1, è necessario assicurarsi che PowerShell sia stato configurato per l'esecuzione di script remoto. Per farlo, avvia PowerShell come amministratore. Su Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2, procedi come segue.
  
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
> Quando si esegue il comando precedente, potrebbe essere visualizzato il seguente errore messaggio: gt _ *Set-ExecutionPolicy: accesso alla chiave del Registro di sistema ' HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' viene negata.* Questo messaggio di errore si verifica in genere se non si esegue PowerShell con credenziali di amministratore. Chiudi la sessione di PowerShell e avvia una nuova sessione come amministratore.
 
Per verificare che il criterio di esecuzione sia stato configurato correttamente, digita quanto segue al prompt di PowerShell e premi INVIO:
  
```
Get-ExecutionPolicy
```

Se ottieni il valore seguente, tutto è configurato correttamente:
  
`RemoteSigned`

Se non in esecuzione Windows PowerShell 5.1, sarà inoltre necessario scaricare e installare Windows Management Framework 5.1 da Microsoft Download Center. Si tratta di un pacchetto di installazione che include 5.1 di Windows PowerShell e gestione remota Windows (WinRM) 3.0. Il pacchetto di installazione può essere necessario se, ad esempio, si eseguono Windows 7 SP1 e non sono ancora aggiornate su Windows PowerShell 5,1. Se si esegue Windows Server 2016 o Windows Update anniversario 10, non vi sarà necessario installare Windows PowerShell 5.1. Windows PowerShell 5.1 preinstallato nei sistemi operativi indicati.
  
Prima di installare Windows Management Framework 5.1:
  
- Accertati di aver scaricato la versione corretta del pacchetto di installazione. Se si esegue la versione a 64 bit di Windows 7 SP1, scaricare il file Win7AndW2K8R2-KB3191566-x64.ZIP. Se si esegue la versione a 32 bit di Windows 7, scaricare il file Win7-KB3191566-x86.ZIP.
    
- Se usi Windows 7 sul tuo computer, accertati di aver installato Windows 7 Service Pack 1.

Se non sei sicuro della versione di Windows in uso o non sei sicuro di aver installato Windows 7 Service Pack 1, fai click su **Start**, fai clic con il pulsante destro su **Computer**, poi fai clic su **Proprietà**. Queste informazioni saranno riportate nella finestra di dialogo Sistema.
  
Per installare Windows Management Framework 5.1, eseguire la procedura descritta in [Install and Configure WMF 5.1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)
  
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
   
## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 
