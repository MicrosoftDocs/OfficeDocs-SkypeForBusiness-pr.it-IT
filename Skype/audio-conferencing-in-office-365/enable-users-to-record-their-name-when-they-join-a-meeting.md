---
title: "Consentire agli utenti di registrare il proprio nome quando accedono a una riunione"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
description: "Learn how to enable or disable whether your users can record their names when they join a meeting "
---

# Consentire agli utenti di registrare il proprio nome quando accedono a una riunione

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](1d649328-ada7-422d-a074-d6da4da36970.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/1d649328-ada7-422d-a074-d6da4da36970). 
  
Quando si configurano audioconferenza in Office 365, si ricevono i numeri di telefono e quello che viene definito un bridge di conferenza audio. Un bridge di conferenza può contenere uno o più numeri di telefono che possono essere un numero di telefono dedicato o condivise.
  
Il bridge di conferenza risponde a una chiamata per un utente che accedono a una riunione tramite telefono. Il bridge di conferenza vengono fornite le risposte chiamante con istruzioni vocali da un operatore automatico e quindi, a seconda delle impostazioni del proprio, riproducibili notifiche, chiedere ai chiamanti di registrare il proprio nome e impostare la protezione del PIN per organizzatori della riunione. Vengono fornite pin di organizzatori della riunione per consentire loro di avviare una riunione. Tuttavia, è possibile impostare il in modo che non è necessario un PIN per avviare una riunione.
  
## Impostare l'opzione che prevede se i chiamanti devono registrare il proprio nome

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nel **Interfaccia di amministrazione di Skype for Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **Impostazioni bridge Microsoft**.
    
4. In **esperienza utente partecipa alla riunione**, vedere la casella di controllo **Abilita voce relativa alla riunione e chiudere le notifiche per essere attivata**.
    
  - **Selezionata** I chiamanti verranno chiesto di registrare il proprio nome prima di accedere alla riunione. Questa opzione è selezionata per impostazione predefinita.
    
  - **Deselezionata** I chiamanti non viene chiesto di registrare il proprio nome prima di accedere alla riunione.
    
5. Dopo aver apportato le modifiche, fai clic su **Salva**.
    
## Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings ](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
- Windows PowerShell è basato sui gestione di utenti e quali utenti sono autorizzati a eseguire. Con Windows PowerShell, è possibile gestire Office 365 utilizzando un unico punto di amministrazione che consente di semplificare le attività quotidiane quando si dispone di più attività da eseguire. Per iniziare a utilizzare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Perché è necessario utilizzare PowerShell di Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre molti vantaggi velocità, semplicità e produttività rispetto all'uso solo di amministrazione di Office 365, ad esempio quando si effettuano modifiche alle impostazioni per molti utenti contemporaneamente. Informazioni su questi vantaggi negli argomenti seguenti:
    
  - [Introduzione a Windows PowerShell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usare Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usare Windows PowerShell per svolgere comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  
## Vedere anche
<a name="MT_Footer"> </a>

#### 

[Servizi di conferenza telefonica con accesso esterno in Office 365](../misctopics/dial-in-conferencing-in-office-365.md)

