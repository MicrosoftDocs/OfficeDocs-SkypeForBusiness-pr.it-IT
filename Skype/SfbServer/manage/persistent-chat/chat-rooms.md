---
title: Gestire le chat room nel server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Riepilogo: informazioni su come gestire le chat room del server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 2b1b2e3bdc3411a4bacae5f1dc81b626abb92a91
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815106"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestire le chat room nel server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come gestire le chat room del server Chat persistente in Skype for Business Server 2015.
  
La creazione e la gestione delle chat room è molto più semplice con il corretto utilizzo delle categorie. Una categoria definisce gli utenti che possono creare o partecipare alle chat room. Prima di tentare di gestire le chat room, leggere categorie di chat [persistente, chat room e ruoli utente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) e [gestire le categorie nel server Chat persistente in Skype for Business Server 2015](categories.md).
  
> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015. 

È possibile configurare e gestire le chat room utilizzando l'interfaccia della riga di comando di Windows PowerShell oppure utilizzando il client Skype for business, se si è membri della chat room. In questo argomento viene descritto come gestire le chat room utilizzando l'interfaccia della riga di comando di Windows PowerShell. Se si desidera gestire le chat room utilizzando il client Skype for business, vedere la guida del client. 
  
Le chat room possono essere tra due tipi: Normal e Auditorium. Una chat room normale consente a tutti i membri di inserire e leggere i messaggi. Un auditorium è un tipo di chat room in cui possono essere pubblicati solo i relatori, ma ognuno può leggere.
  
Gli utenti che possono accedere e gestire le chat room dipendono dai ruoli degli utenti, come indicato di seguito:
  
- Gli utenti devono essere membri di una chat room per poter postare e leggere i messaggi.
    
- I relatori sono autorizzati a pubblicare nelle sale Auditorium.
    
- Gli amministratori possono eliminare dalla chat room il contenuto meno recente, ad esempio il contenuto pubblicato prima di una certa data, affinché il database non raggiunga dimensioni troppo elevate. Gli amministratori possono anche rimuovere o sostituire i messaggi considerati inadeguati per una chat room specifica.
    
- Gli utenti finali, compresi gli autori dei messaggi, non possono eliminare il contenuto da una chat room.
    
- I responsabili delle chat room possono apportare modifiche a tutte le proprietà delle chat room, tra cui la disattivazione delle sale. Tuttavia, i Manager non possono eliminare una chat room o modificare la categoria di una chat room. 
    
- Solo gli amministratori possono eliminare una chat room dopo che è stata creata.
    
È possibile configurare e gestire le chat room utilizzando i cmdlet di Windows PowerShell seguenti:
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |Creare una nuova chat room  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configurare le impostazioni per una sala esistente. assegnare gli utenti e i gruppi di utenti alla sala  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recuperare informazioni sulle sale  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Cancellare una chat room o i messaggi da una chat room  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Rimuovere una chat room  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Rimuovere i messaggi da una chat room  <br/> |
   
È possibile utilizzare il cmdlet **New-CsPersistentChatRoom** per creare chat room e il cmdlet **Set-CsPersistentChatRoom** per configurare una chat room esistente, inclusa l'aggiunta di utenti alla chat room. È possibile configurare i seguenti parametri per le chat room:
  
- Disabili. Consente di disabilitare o abilitare una chat room. 
    
- Inviti. Consente di abilitare o disabilitare gli inviti delle chat room, che vengono utilizzati per informare gli utenti quando sono stati aggiunti come membri della chat room. L'impostazione predefinita per gli inviti in Inherit, che ha causato l'impostazione dell'invito configurata dalla chat room per la categoria a cui appartiene. Configurando l'impostazione inviti su false a livello di chat room è possibile ignorare l'impostazione di categoria. 
    
- Privacy. Consente di specificare se una chat room è aperta, chiusa o segreta. Le sale aperte possono essere cercate e accessibili da chiunque. Le sale chiuse possono essere cercate da chiunque, ma possono essere accessibili solo dai membri. Le sale segrete possono essere ricercate e accessibili solo dai membri della chat room. Per impostazione predefinita, ogni nuova sala viene inizialmente configurata come chiusa.
    
- Tipo. Consente di specificare se una chat room è una sala normale, che accetta i messaggi inviati da qualsiasi membro o una sala auditorium, che accetta i messaggi inviati solo da un relatore.
    
- AddIn. Consente di associare un componente aggiuntivo configurato in precedenza a una chat room, che consente ai membri di visualizzare il contenuto degli URL durante la partecipazione.
    
Oltre ai parametri sopra riportati, il cmdlet **Set-CsPersistentChatRoom** consente di assegnare gli utenti alla chat come indicato di seguito:
  
- Membri. Configura l'appartenenza per la chat room. È possibile aggiungere o rimuovere singoli o più membri utilizzando un singolo cmdlet specificando l'indirizzo SIP degli utenti. Per consentire l'aggiunta di utenti in blocco, è possibile specificare anche le unità organizzative o i gruppi di distribuzione di Active Directory.
    
- Manager. Consente di assegnare Manager alla chat room. I Manager dispongono delle autorizzazioni per definire l'appartenenza di una chat room insieme ad altre impostazioni.
    
- Relatori. Consente di assegnare i relatori a una chat room dell'Auditorium. 
    
  Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri, vedere [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
## <a name="create-a-new-room"></a>Creare una nuova sala

È possibile creare una nuova sala utilizzando il cmdlet **New-CsPersistentChatRoom** . Ad esempio, il comando seguente crea una nuova chat room denominata room ITChatRoom nel pool atl-cs-001.contoso.com. In questo esempio viene aggiunta la chat room alla categoria IT:
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**Nota:** PersistentChatPoolFqdn non è necessario se si verifica una delle condizioni seguenti: 
  
- È presente un solo pool di server Chat persistente.
    
- Si specifica l'FQDN di un pool per la categoria.
    
- Si specifica l'FQDN di un pool per l'aggiunta della chat room.
    
## <a name="configure-an-existing-room"></a>Configurare una sala esistente

È possibile configurare una sala esistente utilizzando il cmdlet **Set-CsPersistentChatRoom** . Ad esempio, il comando seguente assegna User1 come membro e relatore e User2 come Manager della sala testCat Auditorium:
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 Nell'esempio seguente vengono aggiunti tutti gli utenti dall'unità organizzativa NorthAmericaUsers in Active Directory alla chat room di NorthAmerica:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

Nell'esempio seguente vengono aggiunti tutti i membri del gruppo di distribuzione Finance alla stessa chat room:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>Disabilitazione o abilitazione di una chat room

Se l'argomento di una chat room persistente non è più pertinente, è possibile rendere la chat room non disponibile per gli utenti disabilitarla. Quando si disabilita una chat room, tutti i membri vengono disconnessi immediatamente. Dopo la disabilitazione di una chat room, gli utenti non possono più parteciparvi né trovarla eseguendo ricerche di chat room.
  
Se la cronologia della chat persiste, il contenuto viene mantenuto quando la chat room è disattivata. Tuttavia, tale contenuto non verrà visualizzato nelle ricerche durante il periodo in cui la chat rimane in uno stato disabilitato. Se in seguito si attiva la chat room, gli utenti possono cercare i messaggi che sono stati inviati prima che la chat room fosse disattivata. Per informazioni sulla configurazione della cronologia delle chat room, vedere [Manage Categories in Persistent Chat Server in Skype for Business server 2015](categories.md). 
  
Se una chat è disabilitata, il relativo elenco dei membri e le altre impostazioni vengono mantenuti. Come amministratore, è possibile abilitare una sala disattivata e non è necessario ricreare le impostazioni manualmente.
  
È possibile disabilitare una chat room utilizzando il cmdlet **Set-CsPersistentChatRoom** e impostando il parametro disabled su true:
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

Per abilitare una chat room, impostare il parametro disabled su false:
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>Ottenere informazioni sulle sale

Per ottenere informazioni sulle sale configurate per l'utilizzo nell'organizzazione, è possibile utilizzare il cmdlet **Get-CsPersistentChatRoom** .
  
Il comando seguente restituisce informazioni su tutte le chat room configurate per l'utilizzo nell'organizzazione:
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>Rimuovere tutto il contenuto da una chat room

È possibile rimuovere il contenuto da una sala utilizzando il cmdlet **Clear-CsPersistentChatRoom** . Ad esempio, il comando seguente consente di rimuovere tutto il contenuto dalla chat room room ITChatRoom persistente che è stato aggiunto alla sala entro il 1 ° marzo 2015:
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>Rimozione di un messaggio da una chat room

È possibile rimuovere uno o più messaggi nel database di Persistent Chat e, facoltativamente, sostituire il messaggio con un messaggio predefinito o con un messaggio fornito dall'amministratore, utilizzando il cmdlet **Remove-CsPersistentChatMessage** . Ad esempio, il comando seguente consente di rimuovere tutti i messaggi dalla chat room di room ITChatRoom che sono stati pubblicati dall'utente kenmyer@contoso.com:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

Nell'esempio seguente vengono sostituiti tutti i messaggi rimossi con la nota che il messaggio non è più disponibile:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>Rimuovere una chat room

È possibile rimuovere una sala utilizzando il cmdlet **Remove-CsPersistentChatRoom** .
  
Ad esempio, il comando seguente consente di rimuovere la chat room RedmondChatRoom:
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>Spostare una chat room da una categoria all'altra

Se un responsabile della chat room ha privilegi di **creatore** in un'altra categoria, può spostare la sala da una categoria all'altra. La sala non viene eliminata e ricreata. Si tratta di un cambiamento di associazione all'interno del database.
  
La modifica di una categoria di chat room deve essere svolta raramente e con cautela. Una categoria determina i membri a cui è consentito accedere alla chat room; se questa viene spostata in un'altra categoria, tutti gli elenchi di controllo di accesso del sistema (SACL) non supportati dalla nuova categoria vengono eliminati. Ad esempio, se un utente è membro della chat room e non è più un membro consentito nella nuova categoria, l'appartenenza alla sala verrà modificata e l'utente verrà rimosso dalla sala.
  

