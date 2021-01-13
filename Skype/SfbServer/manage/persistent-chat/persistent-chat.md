---
title: Gestire il server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Riepilogo: informazioni su come gestire il server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 9a97511f9b4c2adae7ead816e86876f05dd39790
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832886"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestire il server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come gestire il server Chat persistente in Skype for Business Server 2015.
  
Quando si configura il server Chat persistente per l'organizzazione, è necessario specificare la configurazione iniziale durante la distribuzione. Tuttavia, è possibile che si verifichino momenti in cui si desidera modificare la modalità di implementazione del supporto del server Chat persistente. Ad esempio, potrebbe essere necessario configurare il supporto e i controlli del server Chat persistente in modo diverso per un team o un gruppo specifico all'interno dell'organizzazione. In questa sezione vengono fornite informazioni e procedure che consentono di personalizzare la distribuzione del server Chat persistente. Per informazioni dettagliate sulle caratteristiche e le funzionalità che è possibile configurare per il server Chat persistente, vedere [Plan for Persistent Chat Server in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Per informazioni dettagliate sulla distribuzione del server Chat persistente, vedere [deploy Persistent Chat Server in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015. 
  
È possibile gestire il server Chat persistente utilizzando il pannello di controllo o i cmdlet di Windows PowerShell. 
  
Per utilizzare il pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat**.
    
Nella tabella seguente sono riepilogati i cmdlet di Windows PowerShell disponibili per la gestione del server Chat persistente. Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, vedere [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Crea una nuova categoria  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configura le impostazioni per una categoria esistente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recupera informazioni sulle categorie  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Rimuove una categoria  <br/> |
|New-CsPersistentChatRoom  <br/> |Crea una nuova chat room  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configura le impostazioni per una sala esistente. assegnare gli utenti e i gruppi di utenti alla sala  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recupera informazioni sulle sale  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Cancellazione di una chat room o di un messaggio da una chat room  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Rimuove una chat room  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Rimuove i messaggi da una chat room  <br/> |
|New-CsPersistentChatAddin  <br/> |Crea un nuovo componente aggiuntivo  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configura le impostazioni per un componente aggiuntivo esistente  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recupera le informazioni sui componenti aggiuntivi  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Rimuove un componente aggiuntivo  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |Modifica una raccolta esistente di impostazioni di configurazione della conformità  <br/> |
|Export-CsPersistentChatData  <br/> |Esporta i dati da un database di chat persistente  <br/> |
|Import-CsPersistentChatData  <br/> |Importa i dati esportati da una versione precedente di Lync Server  <br/> |
   

