---
title: "Attivare o disattivare gli annunci di tipo Entrata o Uscita per le riunioni"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/22/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
description: "Learn how to turn entry and exit announcements on or off in a Skype for Business Online meeting using the Skype for Business admin center. "
---

# Attivare o disattivare gli annunci di tipo Entrata o Uscita per le riunioni

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la [dichiarazione di non responsabilità](f2c7b5ea-07b6-4b77-8023-bec9596fcc32.md#MT_Footer). Per visualizzare la versione inglese dell'articolo, [fare clic qui](https://support.office.com/en-us/article/f2c7b5ea-07b6-4b77-8023-bec9596fcc32). 
  
Quando si configurano audioconferenza in Office 365, verrà visualizzato un bridge di conferenza audio. Un bridge di conferenza può contenere uno o più numeri di telefono che persone verranno usato per accedere a Skype for Business o Teams Microsoft per la riunione.
  
Il bridge di conferenza risponde a una chiamata per un utente che accedono a una riunione tramite telefono. Il bridge di conferenza vengono fornite le risposte chiamante con istruzioni vocali da un operatore automatico di servizi di conferenza e quindi, a seconda delle impostazioni riproducibili notifiche, chiedere ai chiamanti di registrare il proprio nome e impostare la protezione PIN. Il PIN è assegnato a una Skype for Business o Microsoft Teams organizzatore della riunione e consente di avviare una riunione se non è possibile avviare alla riunione tramite un Skype per Business o Microsoft Teams app. È tuttavia possibile, impostarlo in modo che non è necessario un PIN per avviare una riunione.
  
## Impostazione delle opzioni di partecipazione a una riunione

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nel **Interfaccia di amministrazione di Skype for Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **Impostazioni bridge Microsoft**.
    
4. In **esperienza utente partecipa alla riunione**, selezionare o deselezionare **Abilita voce relativa alla riunione e chiudere le notifiche per essere attivata**. Questa opzione è selezionata per impostazione predefinita. Se si deseleziona il campo, gli utenti che hanno già eseguito l'accesso alla riunione non è possibile sapere quando un utente attiva o disattiva la riunione.
    
5. In **tipo di annuncio di ingresso/uscita**, selezionare **i nomi o i numeri di telefono** o **toni**.
    
6. Selezionare o deselezionare **Chiedi ai chiamanti di registrare il proprio nome prima di partecipare alla riunione**.
    
7. Dopo aver apportato le modifiche, fai clic su **Salva**.
    
## Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .
    
- Quando si tratta di Windows PowerShell, Skype for Business online è basato sui gestione di utenti e quali utenti sono consentite o non consentite. Con Windows PowerShell, è possibile gestire Office 365 utilizzando un unico punto di amministrazione che consente di semplificare le attività quotidiane quando si dispone di più attività da eseguire. Per iniziare a utilizzare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Perché è necessario utilizzare PowerShell di Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Gestire Office 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre molti vantaggi velocità, semplicità e produttività rispetto all'uso solo di amministrazione di Office 365, ad esempio quando si eseguono modifiche alle impostazioni per molti utenti contemporaneamente. Informazioni su questi vantaggi negli argomenti seguenti:
    
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

