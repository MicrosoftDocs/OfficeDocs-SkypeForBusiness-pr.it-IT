---
title: "Configurare la rete per Skype Meeting Broadcast"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
description: "Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees."
---

# Configurare la rete per Skype Meeting Broadcast

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](dfa736b9-4920-4f48-b8c0-b5487ec6086f.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/dfa736b9-4920-4f48-b8c0-b5487ec6086f). 
  
Dopo aver [Abilitare Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, devi configurare la rete. Segui questo passaggio se vuoi tenere webinar e altri eventi in broadcast per persone all'esterno della tua azienda.
  
Se non hai dimestichezza con la configurazione del firewall, può essere utile assumere un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) che se ne occupi al posto tuo.
  
Per ignorare questo passaggio e per aggiungere un'altra business per la federazione in modo che è possibile invitare le persone a trasmissioni, seguire la procedura descritta in [Consentire agli utenti di contattare utenti Skype for Business esterni](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).
  
## Passaggio 1: configurare i domini ammessi

Utilizzare **uno** dei metodi seguenti per configurare i domini consentiti:
  
### 

 **Metodo 1: Utilizzare l'interfaccia di amministrazione di Office 365**
  
1. Accedere all'interfaccia **di amministrazione di Office 365** e quindi nel riquadro di spostamento sinistra, fare clic su **Impostazioni** > **componenti aggiuntivi e servizi** e quindi scegliere **Skype for Business**.
    
2. Nella pagina **la condivisione esterna** in **eccezioni di dominio**, selezionare **tutti i domini bloccati ad eccezione di** e immettere i seguenti domini separati da virgola (,):
    
  - noammeetings.lync.com
    
  - emeameetings.lync.com
    
  - apacmeetings.lync.com
    
  - resources.lync.com
    
3. Fai clic su **Salva**.
    
### 

 **Metodo 2: Utilizzare Windows PowerShell**
  
- Dal **Menu Start** destro **Windows PowerShell** e scegliere **Esegui come amministratore**. Nella finestra di **Windows PowerShell**, digitare ogni riga e premere INVIO.
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## Passaggio 2: Aggiungere domini, URL e indirizzi IP di Skype Meeting Broadcast indirizzi

Il secondo passaggio del processo di installazione è per poter aggiungere i domini sono necessarie e quindi aggiungono gli indirizzi IP e URL necessari per Skype Meeting Broadcast per l'uso.
  
- **Aggiungere i punti finali dominio necessari:**
    
    Per usare Skype Meeting Broadcast, è necessario che gli endpoint seguenti siano accessibili ai computer client.
    
|
|
|**Riga**|**Scopo**|**Origine |Credenziali**|**Destinazione**|**Community BGP di ExpressRoute per Office 365**|**Indirizzo CIDR**|**Porta**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |**Obbligatorio:** endpoint di Skype for Business. <br/> |Vedere [Skype for Business Online](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO) e assicurarsi che tutte le voci etichettate con "obbligatorio" siano accessibili. <br/> ||||
|2  <br/> |**Obbligatorio:** relatore e partecipante di[Skype Meeting Broadcast](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) <br/> |computer client/utente connesso  <br/> |
```
*.broadcast.skype.com
broadcast.skype.com
browser.pipe.aria.microsoft.com

```

|sì  <br/> |[](8548a211-3fe7-47cb-abb1-355ea5aa88a2.md#BKMK_SfB_IP).  <br/> |TCP 443  <br/> |
|3  <br/> |**Obbligatorio:** relatore e partecipante di[Skype Meeting Broadcast](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) <br/> |computer client/utente connesso  <br/> |
```
aka.ms
amp.azure.net

```

|no  <br/> |N/D  <br/> |TCP 443  <br/> |
|4  <br/> |**Obbligatorio:** relatore e partecipante di[Skype Meeting Broadcast](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d) (incluse le reti CDN) <br/> |computer client/utente connesso  <br/> |
```
*.keydelivery.mediaservices.windows.net
*.msecnd.net
*.streaming.mediaservices.windows.net
ajax.aspnetcdn.com
mlccdn.blob.core.windows.net

```

|no  <br/> |N/D  <br/> |TCP 443  <br/> |
   
- **Aggiungere necessari Skype for Business Online endpoint URL e indirizzi IP verificando quali sono necessari**[qui](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).
    
## Configurare Skype Meeting Broadcast in organizzazioni e distribuzioni ibride

Se si dispone di un'organizzazione Skype for Business online e una distribuzione locale di Lync Server 2010, Microsoft Lync Server 2013 e Skype for Business Server 2015 e chiedere agli utenti sia online e in locale, esistono altri passaggi di configurazione che sarà necessario eseguire oltre a quelli sopra riportati per abilitare l'organizzazione locale per comunicare con Skype for Business online e consentire a tutti gli utenti la possibilità di creare e partecipare a una Skype Meeting Broadcast. Per vedere quali sono i requisiti, vedere [configurare la distribuzione locale per Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).
  
## Argomenti correlati

[Abilitare Skype Meeting Broadcast](enable-skype-meeting-broadcast.md)
  
[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

