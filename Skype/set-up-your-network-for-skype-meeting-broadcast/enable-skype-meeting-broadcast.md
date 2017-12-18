---
title: "Abilitare Skype Meeting Broadcast"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
description: "Le persone dell'organizzazione possono usare Skype Meeting Broadcast, è necessario attivarlo. A questo scopo è necessario sapere come usare Windows PowerShell. Se non si conosce Windows PowerShell, è consigliabile rivolgersi a un partner Microsoft per eseguire questo passaggio operazione."
---

# Abilitare Skype Meeting Broadcast

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
Le persone dell'organizzazione possono usare Skype Meeting Broadcast, è necessario attivarlo. A questo scopo è necessario sapere come usare Windows PowerShell. Se non si conosce Windows PowerShell, è consigliabile rivolgersi a un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per eseguire questo passaggio operazione.
  
> [!CAUTION]
> Skype Meeting Broadcast è disattivata per impostazione predefinita quanto nella distribuzione di contenuti di una riunione trasmissione viene utilizzato contenuto rete (CDN del Microsoft Azure) per ottenere scala molto elevata per supportare migliaia di spettatori una trasmissione. Il contenuto multimediale in blocchi attraversa la rete CDN è crittografato e la cache CDN con una durata limitata. Inoltre, il componente di Azure CDN potrebbe non ancora soddisfare tutti gli elementi delle clausole di modello dell'Unione europea derivanti dall'istruzione protezione dei dati dell'Unione europea. Abilitando questa caratteristica, l'utente riconosce questo avviso. 
  
## Abilitare Skype Meeting Broadcast con l'interfaccia di amministrazione di Skype for Business

1. Accedi con l'account di amministratore globale di Office 365 all'indirizzo [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home). 
    
2. Nell'interfaccia di amministrazione di Office 365, passare a **Interfacce di amministrazione** > **Skype for Business**.
    
3. In **Skype for Business admin center**, passare a **riunioni Online** > **trasmettere riunioni** e quindi selezionare **Abilita Skype Meeting Broadcast**.
    
## Abilitare Skype Meeting Broadcast con PowerShell

1. Verifica che sia in esecuzione Windows PowerShell versione 3.0 o successiva.
    
1. Per verificare che sia in esecuzione la versione 3.0 o successive: **Menu Start** > **Windows PowerShell**.
    
2. Controlla la versione digitando  _Get-Host_ nella finestra **Windows PowerShell**.
    
3. Se non si ha la versione 3.0 o versioni successive, è necessario scaricare e installare gli aggiornamenti di Windows PowerShell. Per scaricare e aggiornare Windows PowerShell alla versione 4.0, vedere [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845). Quando richiesto, riavviare il computer.
    
4. Sarà anche necessario installare il modulo di Windows PowerShell per Skype for Business online, che consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo in computer a 64 bit, può essere scaricato dall'Area download Microsoft nella sezione [Modulo di Windows PowerShell per Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se richiesto, riavviare il computer.
    
2. Dal **Menu Start**, scegliere **Windows PowerShell**.
    
3. Nella finestra **Windows PowerShell** connettersi all'organizzazione di Office 365 eseguendo:
    
  ```
  $Credential = get-credential
  ```

  ```
  $O365Session = New-CsOnlineSession -Credential $credential
  ```

  ```
  Import-PSSession $O365Session
  ```

4. Conferma la configurazione corrente di Skype Meeting Broadcast eseguendo:
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    Verifica che il parametro  _EnableBroadcastMeeting_ sia impostato su `False`.
    
     ![Cmdlet per abilitare Skype Meeting Broadcast nell'organizzazione.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. Abilita Skype Meeting Broadcast per la tua organizzazione eseguendo:
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    È possibile verificare che l'impostazione sia abilitata eseguendo nuovamente  `Get-CsBroadcastMeetingConfiguration` .
    
     ![Cmdlet per abilitare Skype Meeting Broadcast nell'organizzazione.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > Dopo aver apportato la modifica, potrebbe essere necessario attendere fino a un'ora perché questa diventi effettiva nel portale Skype Meeting Broadcast. 
  
6. Gli utenti possono contenere ora trasmettere riunioni con altri utenti nell'organizzazione. Per ottenerle avviato, scegliere loro di [Informazioni su Skype Meeting Broadcast](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## Configurare la rete per le riunioni in broadcast con partecipanti esterni

Se hai un firewall e vuoi trasmettere webinar o altre riunioni a partecipanti all'esterno dell'azienda (che non siano aziende federate), devi configurare la rete secondo queste istruzioni: [Configurare la rete per Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Se non hai dimestichezza con la configurazione del firewall, può essere utile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) che se ne occupi al posto tuo.
  
Per ignorare questo passaggio e aggiungere un'altra business per la federazione, vedere [Consentire agli utenti di contattare utenti Skype for Business esterni](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  
## Vedere anche
<a name="MT_Footer"> </a>

#### 

[Introduzione a Windows Powershell e Skype for Business online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

