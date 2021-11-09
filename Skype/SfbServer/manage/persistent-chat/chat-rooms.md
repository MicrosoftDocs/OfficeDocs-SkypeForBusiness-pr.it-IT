---
title: Gestire chat room nel server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Riepilogo: informazioni su come gestire le chat room del server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 63566d897901be32b7d0f33ea099bac202e61515
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830850"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestire chat room nel server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come gestire le chat room del server Chat persistente in Skype for Business Server 2015.
  
La creazione e la gestione delle chat room è molto più semplice con l'uso corretto delle categorie. Una categoria definisce gli utenti che possono creare o partecipare alle chat room. Prima di tentare di gestire le chat room, leggere Categorie di chat persistente, chat room e ruoli utente [in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) e Gestire le categorie nel server Chat persistente [in Skype for Business Server 2015](categories.md).
  
> [!NOTE]
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento.](/microsoftteams/upgrade-start-here) Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015. 

È possibile configurare e gestire chat room utilizzando l'interfaccia della riga di comando di Windows PowerShell oppure il client Skype for Business se si è membri della chat room. In questo argomento viene descritto come gestire le chat room tramite l'Windows PowerShell della riga di comando. Se si desidera gestire le chat room utilizzando il client Skype for Business, vedere la Guida del client. 
  
Le chat room possono essere di due tipi: Normale e Auditorium. Una chat room normale consente a tutti i membri di pubblicare e leggere messaggi. Un auditorium è un tipo di chat room in cui solo i relatori possono pubblicare, ma tutti possono leggere.
  
Who accesso e gestione delle chat room dipende dai ruoli utente, come indicato di seguito:
  
- Gli utenti devono essere membri di una chat room per poter pubblicare e leggere messaggi.
    
- I relatori possono pubblicare post nelle sale Auditorium.
    
- Gli amministratori possono eliminare dalla chat room il contenuto meno recente, ad esempio il contenuto pubblicato prima di una certa data, affinché il database non raggiunga dimensioni troppo elevate. Gli amministratori possono anche rimuovere o sostituire i messaggi considerati inappropriati per una determinata chat room.
    
- Gli utenti finali, compresi gli autori dei messaggi, non possono eliminare il contenuto da una chat room.
    
- I responsabili delle chat possono apportare modifiche a tutte le proprietà delle chat room, inclusa la disabilitazione delle chat room. I manager non possono tuttavia eliminare una sala o modificare la categoria di una sala. 
    
- Solo gli amministratori possono eliminare una chat room dopo che è stata creata.
    
È possibile configurare e gestire chat room utilizzando i cmdlet Windows PowerShell seguenti:
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |Creare una nuova chat room  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configurare le impostazioni per una sala esistente; assegnare utenti e gruppi di utenti alla chat room  <br/> |
|Get-CsPersistentChatRoom  <br/> |Recuperare informazioni sulle chat room  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Cancellare una o più chat room o messaggi da una sala  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Rimuovere una sala  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Rimuovere messaggi da una chat room  <br/> |
   
Utilizzare il cmdlet **New-CsPersistentChatRoom** per creare chat room e il cmdlet **Set-CsPersistentChatRoom** per configurare una chat esistente, inclusa l'aggiunta di utenti alla chat room. È possibile configurare i parametri seguenti per le chat room:
  
- Disabilitato. Consente di disabilitare o abilitare una chat room. 
    
- Inviti. Consente di abilitare o disabilitare gli inviti alle chat room, che vengono utilizzati per notificare agli utenti quando sono stati aggiunti come membri della chat. L'impostazione predefinita per gli inviti in ereditarietà, che ha determinato l'adozione da parte della chat room dell'impostazione di invito configurata per la categoria a cui appartiene. La configurazione dell'impostazione degli inviti su false a livello di chat room consente di eseguire l'override dell'impostazione della categoria. 
    
- Privacy. Consente di specificare se una chat room è aperta, chiusa o segreta. Le sale aperte possono essere ricercate e accessibili da chiunque. Le sale chiuse possono essere ricercate da chiunque, ma possono essere accessibili solo dai membri. Le chat room segrete possono essere ricercate e accessibili solo dai membri della chat room. Per impostazione predefinita, ogni nuova sala è inizialmente configurata come Chiusa.
    
- Digitare. Consente di specificare se una chat room è una sala normale, che accetta i messaggi inviati da qualsiasi membro, o una sala Auditorium, che accetta i messaggi inviati solo da un relatore.
    
- Componente aggiuntivo. Consente di associare un componente aggiuntivo configurato in precedenza a una chat room, che consente la visualizzazione del contenuto url da parte dei membri durante la partecipazione.
    
Oltre ai parametri precedenti, il cmdlet **Set-CsPersistentChatRoom** consente di assegnare gli utenti alla chat room nel modo seguente:
  
- Membri. Configura l'appartenenza alla chat room. È possibile aggiungere o rimuovere singoli o più membri utilizzando un singolo cmdlet specificando l'indirizzo SIP degli utenti. Per consentire l'aggiunta in blocco degli utenti, è possibile specificare anche unità organizzative o gruppi di distribuzione di Active Directory.
    
- Responsabili. Consente di assegnare responsabili alla chat room. I manager dispongono delle autorizzazioni per definire l'appartenenza a una chat room insieme ad altre impostazioni.
    
- Relatori. Consente di assegnare relatori a una chat room Auditorium. 
    
  Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri, [vedere Skype for Business Server 2015 Management Shell](../management-shell.md).
  
## <a name="create-a-new-room"></a>Creare una nuova chat room

È possibile creare una nuova sala utilizzando il cmdlet **New-CsPersistentChatRoom.** Ad esempio, il comando seguente crea una nuova chat room denominata ITChatRoom nel pool atl-cs-001.contoso.com. In questo esempio la chat room viene aggiunta alla categoria IT:
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**Nota:** PersistentChatPoolFqdn non è necessario se si verifica una delle condizioni seguenti: 
  
- Esiste un solo pool di server Chat persistente.
    
- Si specifica l'FQDN di un pool per la categoria.
    
- Si specifica l'FQDN di un pool per l'aggiunta della chat room.
    
## <a name="configure-an-existing-room"></a>Configurare una chat room esistente

È possibile configurare una sala esistente utilizzando il cmdlet **Set-CsPersistentChatRoom.** Ad esempio, il comando seguente assegna user1 come membro e relatore e utente2 come manager della sala auditorium testCat:
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 Nell'esempio seguente tutti gli utenti dell'unità organizzativa NorthAmericaUsers in Active Directory vengono aggiunti alla chat room NorthAmerica:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

Nell'esempio seguente vengono aggiunti tutti i membri del gruppo di distribuzione Finance alla stessa chat room:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>Disabilitare o abilitare una sala

Se l'argomento di una chat room persistente non è più rilevante, è possibile renderla non disponibile per gli utenti disabilitandolo. Quando si disabilita una chat room, tutti i membri vengono disconnessi immediatamente. Dopo la disabilitazione di una chat room, gli utenti non possono più parteciparvi né trovarla eseguendo ricerche di chat room.
  
Se la cronologia della chat room persiste, il contenuto viene conservato quando la chat room è disabilitata. Tuttavia, tale contenuto non verrà visualizzato nelle ricerche durante il periodo in cui la chat rimane in stato disabilitato. Se successivamente si abilita la chat room, gli utenti possono cercare i messaggi che sono stati pubblicati prima che la chat fosse disabilitata. Per informazioni sulla configurazione della cronologia delle chat room, vedere [Manage categories in Persistent Chat Server in Skype for Business Server 2015.](categories.md) 
  
Se una chat è disabilitata, il relativo elenco dei membri e le altre impostazioni vengono mantenuti. Gli amministratori possono abilitare una sala disabilitata e non è necessario creare di nuovo manualmente le impostazioni.
  
È possibile disabilitare una sala utilizzando il cmdlet **Set-CsPersistentChatRoom** e impostando il parametro Disabled su True:
  
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

È possibile rimuovere contenuto da una sala utilizzando il cmdlet **Clear-CsPersistentChatRoom.** Ad esempio, il comando seguente rimuove tutto il contenuto dalla chat room persistente ITChatRoom aggiunta alla chat room il 1° marzo 2015 o prima:
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>Rimuovere un messaggio da una sala

È possibile rimuovere uno o più messaggi nel database di Persistent Chat e facoltativamente sostituire il messaggio con un messaggio predefinito o con un messaggio fornito dall'amministratore utilizzando il cmdlet **Remove-CsPersistentChatMessage.** Ad esempio, il comando seguente rimuove tutti i messaggi dalla chat room ITChatRoom che sono stati pubblicati dall'kenmyer@contoso.com:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

Nell'esempio seguente i messaggi rimossi vengono sostituiti con la nota che il messaggio non è più disponibile:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>Rimuovere una sala

È possibile rimuovere una sala utilizzando il cmdlet **Remove-CsPersistentChatRoom.**
  
Ad esempio, il comando seguente rimuove la chat room RedmondChatRoom:
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>Spostare una sala da una categoria a un'altra

Se un responsabile della chat room dispone **dei privilegi creator** in un'altra categoria, può spostare la chat room da una categoria a un'altra. La sala non viene eliminata e ricreata. Si tratta di un cambiamento di associazione all'interno del database.
  
La modifica di una categoria di chat room deve essere eseguita raramente e con cautela. Una categoria determina i membri a cui è consentito accedere alla chat room; se questa viene spostata in un'altra categoria, tutti gli elenchi di controllo di accesso del sistema (SACL) non supportati dalla nuova categoria vengono eliminati. Ad esempio, se un utente era un membro della chat room e non è più un membro consentito nella nuova categoria, l'appartenenza alla chat room verrà modificata e l'utente verrà rimosso dalla chat room.
  

