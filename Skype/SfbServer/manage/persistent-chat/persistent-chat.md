---
title: Gestire il server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Riepilogo: informazioni su come gestire il server di chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 97cce8adedbb4dea932084497006e3c17bfdd7d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817322"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestire il server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come gestire il server di chat persistente in Skype for Business Server 2015.
  
Quando si configura il server di chat persistente per l'organizzazione, è necessario specificare la configurazione iniziale durante la distribuzione. In alcuni casi, tuttavia, può essere necessario cambiare la modalità di implementazione del supporto del server di chat persistente. Ad esempio, potrebbe essere necessario configurare il supporto e i controlli del server di chat persistente in modo diverso per un team o un gruppo specifico all'interno dell'organizzazione. Questa sezione fornisce informazioni e procedure utili per personalizzare la distribuzione del server di chat persistente. Per informazioni dettagliate sulle caratteristiche e le funzionalità che è possibile configurare per il server di chat persistente, vedere [pianificare il server di chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Per informazioni dettagliate sulla distribuzione di un server di chat persistente, vedere [distribuire il server di chat persistente in Skype for Business server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 
  
È possibile gestire il server di chat persistente usando il pannello di controllo o usando i cmdlet di Windows PowerShell. 
  
Per usare il pannello di controllo:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.
    
2. Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **chat persistente**.
    
La tabella seguente riepiloga i cmdlet di Windows PowerShell disponibili per gestire il server di chat persistente. Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, Vedi [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Crea una nuova categoria  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configura le impostazioni per una categoria esistente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recupera informazioni sulle categorie  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Rimuove una categoria  <br/> |
|New-CsPersistentChatRoom  <br/> |Crea una nuova chat room  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configura le impostazioni per una sala esistente; assegnare gli utenti e i gruppi di utenti alla chat room  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recupera informazioni sulle sale  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Cancella una chat room o i messaggi da una chat room  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Rimuove una sala  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Rimuove i messaggi da una chat room  <br/> |
|New-CsPersistentChatAddin  <br/> |Crea un nuovo componente aggiuntivo  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configura le impostazioni per un componente aggiuntivo esistente  <br/> |
|Get-CsPersistentChatAddin  <br/> |Recupera informazioni sui componenti aggiuntivi  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Rimuove un componente aggiuntivo  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |Modifica una raccolta esistente di impostazioni di configurazione della conformità  <br/> |
|Export-CsPersistentChatData  <br/> |Esporta dati da un database di chat persistente  <br/> |
|Import-CsPersistentChatData  <br/> |Importa dati esportati da una versione precedente di Lync Server  <br/> |
   

