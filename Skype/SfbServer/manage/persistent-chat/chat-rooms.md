---
title: Gestire le chat room nel server Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Riepilogo: informazioni su come gestire le chat room del server di chat persistenti in Skype for Business Server 2015.'
ms.openlocfilehash: cbced7f62a4684e5541e35b5985b7e93cc7d3e66
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992121"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestire le chat room nel server Chat persistente
 
**Riepilogo:** Informazioni su come gestire le chat room del server di chat persistenti in Skype for Business Server 2015.
  
La creazione e la gestione delle chat room è molto più semplice con l'uso corretto delle categorie. Una categoria definisce chi può creare o partecipare alle chat room. Prima di tentare di gestire le chat room, leggere le categorie di chat [persistenti, le chat room e i ruoli utente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) e [gestire le categorie nel server di chat persistente in Skype for Business Server 2015](categories.md).
  
> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 

È possibile configurare e gestire le chat room usando l'interfaccia della riga di comando di Windows PowerShell oppure usando il client Skype for business se si è membri della chat room. Questo argomento descrive come gestire le chat room usando l'interfaccia della riga di comando di Windows PowerShell. Se si vuole gestire le chat room usando il client Skype for business, vedere la guida del client. 
  
Le chat room possono essere uno dei due tipi seguenti: Normal e Auditorium. Una chat room normale consente a tutti i membri di inserire e leggere i messaggi. Un auditorium è un tipo di chat room in cui possono essere pubblicati solo relatori, ma tutti possono leggere.
  
Chi può accedere e gestire le chat room dipende dai ruoli degli utenti come segue:
  
- Gli utenti devono essere membri di una chat room per poter pubblicare e leggere i messaggi.
    
- I relatori possono inserire le camere in Auditorium.
    
- Gli amministratori possono eliminare il contenuto precedente, ad esempio il contenuto postato prima di una determinata data, da qualsiasi chat room per evitare che il database cresca troppo grande. Gli amministratori possono anche rimuovere o sostituire i messaggi considerati inappropriati per una particolare chat room.
    
- Gli utenti finali, inclusi gli autori dei messaggi, non possono eliminare il contenuto da qualsiasi chat room.
    
- I responsabili delle chat room possono apportare modifiche a tutte le proprietà della chat room, incluse le camere disabilitate. I responsabili non possono tuttavia eliminare una chat room o modificare la categoria di una chat room. 
    
- Solo gli amministratori possono eliminare una chat room dopo che è stata creata.
    
È possibile configurare e gestire le chat room usando i cmdlet di Windows PowerShell seguenti:
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |Creare una nuova chat room  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configurare le impostazioni per una sala esistente; assegnare gli utenti e i gruppi di utenti alla chat room  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recuperare informazioni sulle sale  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Cancellare una chat room o i messaggi da una chat room  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Rimuovere una chat room  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Rimuovere i messaggi da una chat room  <br/> |
   
Puoi usare il cmdlet **New-CsPersistentChatRoom** per creare chat room e il cmdlet **Set-CsPersistentChatRoom** per configurare una chat room esistente, incluso l'aggiunta di utenti alla chat room. È possibile configurare i parametri seguenti per le chat room:
  
- Disabilitato. Consente di disabilitare o abilitare una chat room. 
    
- Inviti. Consente di abilitare o disabilitare gli inviti alle chat room, che vengono usati per avvisare gli utenti quando sono stati aggiunti come membri della chat room. L'impostazione predefinita per gli inviti in Inherit, che ha causato la chat room ad adottare l'impostazione dell'invito configurata nella categoria a cui appartiene. La configurazione degli inviti impostato su false a livello di chat room consente di eseguire l'override dell'impostazione Category. 
    
- Privacy. Consente di specificare se una chat room è aperta, chiusa o segreta. Le sale aperte possono essere cercate e accessibili da chiunque. Le sale chiuse possono essere cercate da chiunque, ma è possibile accedervi solo dai membri. Le camere segrete possono essere cercate e accessibili solo dai membri della chat room. Per impostazione predefinita, ogni nuova sala viene inizialmente configurata come chiusa.
    
- Tipo. Consente di specificare se una chat room è una sala normale, che accetta i messaggi inviati da qualsiasi membro o una sala auditorium, che accetta i messaggi inviati solo da un relatore.
    
- AddIn. Consente di associare un componente aggiuntivo configurato in precedenza con una chat room, che consente di visualizzare il contenuto dell'URL per i membri durante la partecipazione.
    
Oltre ai parametri descritti sopra, il cmdlet **Set-CsPersistentChatRoom** consente di assegnare utenti alla chat room come indicato di seguito:
  
- Membri. Configura l'appartenenza per la chat room. È possibile aggiungere o rimuovere singoli o più membri usando un singolo cmdlet specificando l'indirizzo SIP degli utenti. Per consentire l'aggiunta di utenti in blocco, è anche possibile specificare unità organizzative o gruppi di distribuzione di Active Directory.
    
- Manager. Consente di assegnare i responsabili alla chat room. I manager hanno le autorizzazioni per definire l'appartenenza a una chat room insieme ad altre impostazioni.
    
- Relatori. Consente di assegnare relatori a una chat room dell'Auditorium. 
    
  Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri, vedere [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
## <a name="create-a-new-room"></a>Creare una nuova sala

È possibile creare una nuova sala usando il cmdlet **New-CsPersistentChatRoom** . Ad esempio, il comando seguente crea una nuova chat room denominata room ITChatRoom nel pool atl-cs-001.contoso.com. In questo esempio, la chat room viene aggiunta alla categoria IT:
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**Nota:** PersistentChatPoolFqdn non è necessario se una delle operazioni seguenti è vera: 
  
- Esiste un solo pool di server di chat persistente.
    
- Fornisci un nome di dominio completo del pool alla categoria.
    
- Puoi specificare un nome di dominio completo del pool per l'aggiunta della chat room.
    
## <a name="configure-an-existing-room"></a>Configurare una sala esistente

È possibile configurare una sala esistente usando il cmdlet **Set-CsPersistentChatRoom** . Ad esempio, il comando seguente assegna User1 come membro e relatore e User2 come Manager della sala testCat Auditorium:
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 Nell'esempio seguente vengono aggiunti tutti gli utenti dell'unità organizzativa NorthAmericaUsers in Active Directory alla chat room di NorthAmerica:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

Nell'esempio seguente vengono aggiunti tutti i membri del gruppo di distribuzione Finance alla stessa chat room:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>Disabilitare o abilitare una chat room

Se l'argomento di una chat room persistente non è più pertinente, è possibile rendere la chat room non disponibile per gli utenti disabilitando il problema. Quando una chat room è disabilitata, tutti i membri vengono immediatamente disconnessi dalla sala. Dopo la disattivazione di una chat room, gli utenti non possono raggiungerla o trovarla nelle ricerche in chat room.
  
Se la cronologia della chat room persiste, il contenuto viene mantenuto quando la chat room è disabilitata. Tuttavia, tale contenuto non verrà visualizzato nelle ricerche durante il periodo di permanenza della chat room in uno stato disabilitato. Se in seguito si Abilita la chat room, gli utenti possono cercare i messaggi inviati prima della disattivazione della chat room. Per informazioni sulla configurazione della cronologia delle chat room, vedere [gestire le categorie nel server di chat persistente in Skype for Business server 2015](categories.md). 
  
Se una chat room è disabilitata, viene mantenuta l'elenco di appartenenza e altre impostazioni. Come amministratore, puoi abilitare una chat room disattivata e non devi ricreare manualmente le impostazioni.
  
È possibile disabilitare una chat room usando il cmdlet **Set-CsPersistentChatRoom** e impostando il parametro disabled su true:
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

Per abilitare una chat room, imposta il parametro disabled su false:
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>Ottenere informazioni sulle sale

Per ottenere informazioni sulle sale configurate per l'uso nell'organizzazione, è possibile usare il cmdlet **Get-CsPersistentChatRoom** .
  
Il comando seguente restituisce informazioni su tutte le chat room configurate per l'uso nell'organizzazione:
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>Rimuovere tutto il contenuto da una chat room

È possibile rimuovere il contenuto da una chat room usando il cmdlet **Clear-CsPersistentChatRoom** . Ad esempio, con il comando seguente viene rimosso tutto il contenuto della chat room room ITChatRoom che è stato aggiunto alla sala prima o prima del 1 ° marzo 2015:
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>Rimuovere un messaggio da una chat room

È possibile rimuovere uno o più messaggi nel database della chat persistente e, facoltativamente, sostituire il messaggio con un messaggio predefinito o con un messaggio fornito dall'amministratore usando il cmdlet **Remove-CsPersistentChatMessage** . Ad esempio, il comando seguente rimuove tutti i messaggi della chat room di room ITChatRoom inviati dall'utente kenmyer@contoso.com:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

L'esempio seguente sostituisce i messaggi rimossi con la nota che il messaggio non è più disponibile:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>Rimuovere una chat room

Per rimuovere una chat room, è possibile usare il cmdlet **Remove-CsPersistentChatRoom** .
  
Ad esempio, il comando seguente rimuove la chat room RedmondChatRoom:
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>Trasferire una sala da una categoria a un'altra

Se un Manager di chat room ha privilegi di **autore** in un'altra categoria, può trasferire la sala da una categoria a un'altra. La sala non viene eliminata e ricreata. Si tratta di un cambiamento di associazione all'interno del database.
  
La modifica di una categoria di chat room deve essere eseguita raramente e con cautela. Una categoria determina l'appartenenza consentita per la chat room, quindi quando una chat room viene spostata in un'altra categoria, tutti gli elenchi di controllo di accesso di sistema (SACL) che non sono più supportati dalla nuova categoria vengono eliminati. Ad esempio, se un utente è stato un membro della chat room e non è più un membro consentito nella nuova categoria, l'appartenenza alla sala verrà modificata e l'utente verrà rimosso dalla sala.
  

