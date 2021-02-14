---
title: Gestire chat room nel server Chat persistente in Skype for Business Server
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
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestire chat room nel server Chat persistente in Skype for Business Server
 
**Riepilogo:** Informazioni su come gestire le chat room del server Chat persistente in Skype for Business Server 2015.
  
La creazione e la gestione delle chat room è molto più semplice con l'uso corretto delle categorie. Una categoria definisce gli utenti che possono creare o partecipare alle chat room. Prima di tentare di gestire le chat room, leggere le categorie di Chat persistente, le chat room e i ruoli utente [in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) e Gestire le categorie nel server Chat persistente in Skype for Business Server [2015.](categories.md)
  
> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. Le stesse funzionalità sono disponibili in Teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here) Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015. 

È possibile configurare e gestire le chat room utilizzando l'interfaccia della riga di comando di Windows PowerShell o il client Skype for Business se si è membri della chat room. In questo argomento viene descritto come gestire le chat room utilizzando l'Windows PowerShell della riga di comando. Se si desidera gestire le chat room utilizzando il client Skype for Business, vedere la Guida del client. 
  
Le chat room possono essere di due tipi: Normale e Auditorium. Una chat room normale consente a tutti i membri di pubblicare e leggere messaggi. Un auditorium è un tipo di chat room in cui solo i relatori possono inserire post, ma tutti possono leggere.
  
Gli utenti autorizzati ad accedere e gestire le chat room dipendono dai ruoli utente, come indicato di seguito:
  
- Gli utenti devono essere membri di una chat room per poter pubblicare e leggere messaggi.
    
- Ai relatori è consentito inserire post nelle sale auditorium.
    
- Gli amministratori possono eliminare dalla chat room il contenuto meno recente, ad esempio il contenuto pubblicato prima di una certa data, affinché il database non raggiunga dimensioni troppo elevate. Gli amministratori possono inoltre rimuovere o sostituire i messaggi considerati inappropriati per una chat room specifica.
    
- Gli utenti finali, compresi gli autori dei messaggi, non possono eliminare il contenuto da una chat room.
    
- I responsabili delle chat room possono apportare modifiche a tutte le proprietà delle chat room, inclusa la disabilitazione delle chat room. I responsabili non possono tuttavia eliminare una chat room o modificare la categoria di una chat room. 
    
- Solo gli amministratori possono eliminare una chat room dopo che è stata creata.
    
È possibile configurare e gestire le chat room utilizzando i cmdlet Windows PowerShell seguenti:
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |Creare una nuova chat room  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configurare le impostazioni per una chat room esistente; assegnare utenti e gruppi di utenti alla chat room  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recuperare informazioni sulle chat room  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Cancellare uno o più messaggi da una chat room  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Rimuovere una chat room  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Rimuovere messaggi da una chat room  <br/> |
   
Utilizzare il cmdlet **New-CsPersistentChatRoom** per creare chat room e il cmdlet **Set-CsPersistentChatRoom** per configurare una chat esistente, inclusa l'aggiunta di utenti alla chat room. È possibile configurare i parametri seguenti per le chat room:
  
- Disabilitato. Consente di disabilitare o abilitare una chat room. 
    
- Inviti. Consente di abilitare o disabilitare gli inviti di chat room, utilizzati per notificare agli utenti quando sono stati aggiunti come membri della chat. Impostazione predefinita per gli inviti in ereditarietà, che ha determinato l'adozione da parte della chat room dell'impostazione di invito configurata per la categoria a cui appartiene. La configurazione dell'impostazione degli inviti su false a livello di chat room consente di eseguire l'override dell'impostazione della categoria. 
    
- Privacy. Consente di specificare se una chat room è aperta, chiusa o segreta. Le sale aperte possono essere cercate e accessibili da chiunque. Le sale chiuse possono essere cercate da chiunque, ma possono essere accessibili solo dai membri. Le chat room segrete possono essere cercate e accessibili solo dai membri della sala. Per impostazione predefinita, ogni nuova chat room è inizialmente configurata come Chiusa.
    
- Tipo. Consente di specificare se una chat room è una chat room Normale, che accetta i messaggi inseriti da qualsiasi membro, o una sala auditorium, che accetta i messaggi inseriti solo da un relatore.
    
- Componente aggiuntivo. Consente di associare un componente aggiuntivo precedentemente configurato a una chat room, che consente ai membri di visualizzare il contenuto dell'URL mentre partecipano.
    
Oltre ai parametri precedenti, il cmdlet **Set-CsPersistentChatRoom** consente di assegnare gli utenti alla chat room nel modo seguente:
  
- Membri. Configura l'appartenenza alla chat room. È possibile aggiungere o rimuovere uno o più membri utilizzando un singolo cmdlet specificando l'indirizzo SIP degli utenti. Per consentire l'aggiunta in blocco degli utenti, è possibile specificare anche le unità organizzative o i gruppi di distribuzione di Active Directory.
    
- Responsabili. Consente di assegnare responsabili alla chat room. I responsabili dispongono delle autorizzazioni per definire l'appartenenza a una chat room insieme ad altre impostazioni.
    
- Relatori. Consente di assegnare relatori a una chat room auditorium. 
    
  Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri, vedere [Skype for Business Server 2015 Management Shell.](../management-shell.md)
  
## <a name="create-a-new-room"></a>Creare una nuova chat room

È possibile creare una nuova chat room utilizzando il cmdlet **New-CsPersistentChatRoom.** Ad esempio, il comando seguente crea una nuova chat room denominata ITChatRoom nel pool atl-cs-001.contoso.com. In questo esempio la chat room viene aggiunta alla categoria IT:
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**Nota:** PersistentChatPoolFqdn non è necessario se si verifica una delle condizioni seguenti: 
  
- Esiste un solo pool di server Chat persistente.
    
- Si specifica l'FQDN di un pool per la categoria.
    
- Si specifica l'FQDN di un pool per l'aggiunta della chat room.
    
## <a name="configure-an-existing-room"></a>Configurare una chat room esistente

È possibile configurare una chat room esistente utilizzando il cmdlet **Set-CsPersistentChatRoom.** Ad esempio, il comando seguente assegna user1 come membro e relatore e user2 come manager della sala testCat Auditorium:
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 Nell'esempio seguente vengono aggiunti tutti gli utenti dell'unità organizzativa NorthAmericaUsers in Active Directory alla chat room NorthAmerica:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

Nell'esempio seguente vengono aggiunti tutti i membri del gruppo di distribuzione Finance alla stessa chat room:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>Disabilitare o abilitare una chat room

Se l'argomento di una chat room di Persistent Chat non è più pertinente, è possibile renderla non disponibile agli utenti disabilitandolo. Quando si disabilita una chat room, tutti i membri vengono disconnessi immediatamente. Dopo la disabilitazione di una chat room, gli utenti non possono più parteciparvi né trovarla eseguendo ricerche di chat room.
  
Se la cronologia della chat viene mantenuta, il contenuto viene conservato quando la chat room è disabilitata. Tuttavia, tale contenuto non verrà visualizzato nelle ricerche durante il periodo in cui la chat room rimane in uno stato disabilitato. Se successivamente si abilita la chat room, gli utenti possono cercare i messaggi inseriti prima che la chat room fosse disabilitata. Per informazioni sulla configurazione della cronologia delle chat room, vedere Gestire le categorie [nel server Chat persistente in Skype for Business Server 2015.](categories.md) 
  
Se una chat è disabilitata, il relativo elenco dei membri e le altre impostazioni vengono mantenuti. Gli amministratori possono abilitare una chat room disabilitata e non è necessario creare di nuovo manualmente le impostazioni.
  
È possibile disabilitare una chat room utilizzando il cmdlet **Set-CsPersistentChatRoom** e impostando il parametro Disabled su True:
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

Per abilitare una chat room, impostare il parametro Disabled su False:
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>Ottenere informazioni sulle chat room

Per ottenere informazioni sulle chat room configurate per l'utilizzo nell'organizzazione, è possibile utilizzare il cmdlet **Get-CsPersistentChatRoom.**
  
Il comando seguente restituisce informazioni su tutte le chat room configurate per l'utilizzo nell'organizzazione:
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>Rimuovere tutto il contenuto da una chat room

È possibile rimuovere contenuto da una chat room utilizzando il cmdlet **Clear-CsPersistentChatRoom.** Ad esempio, il comando seguente rimuove tutto il contenuto dalla chat room di Persistent Chat ITChatRoom aggiunta alla chat room il 1° marzo 2015 o prima di marzo 2015:
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>Rimuovere un messaggio da una chat room

È possibile rimuovere uno o più messaggi dal database di Persistent Chat e facoltativamente sostituire il messaggio con un messaggio predefinito o con un messaggio fornito dall'amministratore, utilizzando il cmdlet **Remove-CsPersistentChatMessage.** Ad esempio, il comando seguente rimuove tutti i messaggi dalla chat room ITChatRoom inseriti dall'utente kenmyer@contoso.com:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

Nell'esempio seguente i messaggi rimossi vengono sostituiti con la nota che il messaggio non è più disponibile:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>Rimuovere una chat room

È possibile rimuovere una chat room utilizzando il cmdlet **Remove-CsPersistentChatRoom.**
  
Ad esempio, il comando seguente rimuove la chat room RedmondChatRoom:
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>Spostare una chat room da una categoria a un'altra

Se un responsabile di chat room dispone **di** privilegi di creatore in un'altra categoria, può spostare la chat room da una categoria a un'altra. La chat room non viene eliminata e ricreata. Si tratta di una modifica dell'associazione all'interno del database.
  
La modifica di una categoria di chat room deve essere eseguita raramente e con cautela. Una categoria determina i membri a cui è consentito accedere alla chat room; se questa viene spostata in un'altra categoria, tutti gli elenchi di controllo di accesso del sistema (SACL) non supportati dalla nuova categoria vengono eliminati. Ad esempio, se un utente era un membro della chat room e non è più un membro consentito nella nuova categoria, l'appartenenza alla chat room verrà modificata e l'utente verrà rimosso dalla chat room.
  

