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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: Scaricare, installare e usare Windows PowerShell 5.1 per creare una sessione remota di PowerShell che si connette a Skype for Business online.
ms.openlocfilehash: 227023d5c86b99a66ecdbdabd3b2973d0383a534
ms.sourcegitcommit: ac922addbc1422b5c41273a2e03196efb2ed7770
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41831153"
---
# <a name="download-and-install-windows-powershell-51"></a>Scaricare e installare Windows PowerShell 5.1

Se si usa Aggiornamento dell'anniversario di Windows 10 o Windows Server 2016, Windows PowerShell 5.1 dovrebbe essere già disponibile perché questa applicazione viene preinstallata con tali sistemi operativi.
  
Per determinare la versione di Microsoft PowerShell in uso, eseguire la procedura seguente nel computer Windows 7, Windows Server 2008 R2 o Windows Server 2012 in uso:
  
1. Fai clic su **Start**, fai clic su **Tutti i programmi**, fai clic su **Accessori**, fai clic su **Windows PowerShell** e poi fai clic su **Windows PowerShell**.
    
2. Nella console PowerShell, digita il comando seguente e poi premi INVIO:
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. La finestra della console mostrerà informazioni simili a quelle seguenti:
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    Se il numero di versione indicato è 5.1, l'applicazione in esecuzione è Windows PowerShell 5.1. Se il numero di versione indicato non è 5.1, è necessario installare Windows PowerShell 5.1. È possibile scaricare Windows Management Framework 5.1, che include Windows PowerShell 5.1, dall'[Area download Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=54616).
  
Dopo aver verificato che Windows PowerShell 5.1 è installato, è necessario verificare che PowerShell sia configurato per l'esecuzione di script remoti. Per farlo, avvia PowerShell come amministratore. Su Windows 7, Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2, procedi come segue.
  
1. Fai clic su **Start**, fai clic su **Tutti i programmi**, fai clic su **Accessori**, fai clic su **Windows PowerShell**, fai clic con il pulsante destro su **Windows PowerShell** e poi fai clic su **Esegui come amministratore**.
    
2. Se viene visualizzata la finestra di dialogo **Controllo dell'account utente**, fare clic su **Sì** per verificare che PowerShell venga eseguito con credenziali di amministratore.
    
Se invece usi Windows 8, procedi come segue.
  
1. Accedi alla barra Accessi, fai clic su **Cerca**, quindi fai clic con il pulsante destro su **Windows PowerShell**. Per accedere rapidamente alla barra Accessi su qualsiasi computer con Windows 8 (con o senza touch screen), tieni premuto il tasto Windows e premi C.
    
2. Nella barra degli strumenti nella parte inferiore dello schermo, fai clic su **Esegui come amministratore**.
    
3. Se viene visualizzata la finestra di dialogo **Controllo dell'account utente**, fai clic su **Sì** per confermare che vuoi eseguire PowerShell con credenziali da amministratore.
    
Una volta che PowerShell è in esecuzione, devi modificare il criterio di esecuzione in modo da consentire l'esecuzione di script remoti. Nella console PowerShell, digita il comando seguente e poi premi INVIO:
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> Quando si esegue il comando procedente, potrebbe essere visualizzato il messaggio di errore seguente:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' del Registro di sistema*. Questo messaggio di errore viene in genere visualizzato se non si esegue PowerShell con credenziali di amministratore. Chiudi la sessione di PowerShell e avvia una nuova sessione come amministratore.
 
Per verificare che il criterio di esecuzione sia stato configurato correttamente, digita quanto segue al prompt di PowerShell e premi INVIO:
  
```PowerShell
Get-ExecutionPolicy
```

Se ottieni il valore seguente, tutto è configurato correttamente:
  
`RemoteSigned`

Se al momento non si sta eseguendo Windows PowerShell 5.1, sarà necessario scaricare e installare anche Windows Management Framework 5.1 dall'Area download Microsoft. Si tratta di un pacchetto di installazione che include Windows PowerShell 5.1 e Windows Remote Management (WinRM) 3.0. Questo pacchetto di installazione potrebbe essere necessario, ad esempio, se si esegue Windows 7 SP1e non è ancora stato eseguito l'aggiornamento a Windows PowerShell 5.1. Se si esegue Windows Server 2016 o Aggiornamento dell'anniversario di Windows 10, non dovrebbe essere necessario installare Windows PowerShell 5.1. Windows PowerShell 5.1 viene infatti preinstallato in tali sistemi operativi.
  
Prima di installare Windows Management Framework 5.1:
  
- Assicurarsi di avere scaricato la versione corretta del pacchetto di installazione. Se si esegue la versione a 64 bit di Windows 7 SP1, scaricare il file Win7AndW2K8R2-KB3191566-x64.ZIP. Se si esegue la versione a 32 bit di Windows 7, scaricare il file Win7-KB3191566-x86.ZIP.
    
- Se usi Windows 7 sul tuo computer, accertati di aver installato Windows 7 Service Pack 1.

Se non sei sicuro della versione di Windows in uso o non sei sicuro di aver installato Windows 7 Service Pack 1, fai click su **Start**, fai clic con il pulsante destro su **Computer**, poi fai clic su **Proprietà**. Queste informazioni saranno riportate nella finestra di dialogo Sistema.
  
Per installare Windows Management Framework 5.1, completare la procedura descritta in [Installare e configurare WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure).
  
Una volta riavviato il computer, verifica che Windows PowerShell si avvii e che possa essere eseguito con credenziali di amministratore. Procedi come segue.
  
1. Fai clic su **Start**, fai clic su **Tutti i programmi**, fai clic su **Accessori**, fai clic su **Windows PowerShell**, fai clic con il pulsante destro su **Windows PowerShell** e poi fai clic su **Esegui come amministratore**.
    
2. Se viene visualizzata la finestra di dialogo Controllo dell'account utente, fai clic su **Sì** per confermare che vuoi eseguire PowerShell con credenziali da amministratore.
    
Quando viene visualizzata la console PowerShell, verifica che il servizio WinRM sia in esecuzione e sia stato configurato correttamente. Per verificare che il servizio sia in esecuzione, digita il comando seguente al prompt di PowerShell e poi premi INVIO:
  
```PowerShell
Get-Service winrm
```

Verranno quindi visualizzate sullo schermo informazioni sul servizio WinRM:
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

Se lo Stato del servizio non è "In esecuzione", digita il comando seguente e premi INVIO per avviare il servizio WinRM:
  
```PowerShell
Start-Service winrm
```

Una volta avviato il servizio, esegui il comando seguente per verificare che WinRM stia usando l'Autenticazione di base:
  
```PowerShell
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

Se l'autenticazione di base è stata impostata su true, è possibile usare PowerShell per connettersi a Skype for Business online.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Argomenti correlati
[Configurare il computer per Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 
