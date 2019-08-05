---
title: Gestire le categorie nel server Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 'Riepilogo: informazioni su come gestire le categorie di server di chat persistenti in Skype for Business Server 2015.'
ms.openlocfilehash: 8a8e8060db896a272293df3259091d4f7667a7d3
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36195929"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestire le categorie nel server Chat persistente
 
**Riepilogo:** Informazioni su come gestire le categorie di server di chat persistenti in Skype for Business Server 2015.
  
Una categoria è una struttura logica per l'organizzazione di chat room. Una categoria definisce un set predefinito di elenchi di controllo di accesso (ACL) per il controllo degli utenti e dei gruppi utente che possono creare o partecipare alle chat room. Le categorie di chat room contengono chat room, ma non altre categorie. Ogni categoria descrive il relativo contenuto con metadati, come Name e Description. La categoria contiene proprietà che possono essere impostate per controllare il comportamento delle chat room che lo appartengono; ad esempio, che le chat room consentano inviti o upload di file o contengano la cronologia chat. 
  
La creazione e la gestione delle chat room è molto più semplice con l'uso corretto delle categorie. Come amministratore del server di chat persistente, puoi definire AllowedMembers e creatori per ogni categoria e definire anche le impostazioni e i comportamenti predefiniti della chat room che verranno applicati a tutte le chat room create nella categoria. Se ad esempio si imposta la AllowedMembers della categoria su contoso.com, è possibile aggiungere un gruppo o un utente a Contoso come membro delle chat room della categoria. Se si impostano i membri consentiti per una categoria alle vendite, solo i gruppi e gli utenti della lista di distribuzione possono essere aggiunti come membri alle chat room della categoria. La proprietà Creators consente di controllare chi può creare chat room in quella categoria. Dopo la creazione della chat room, tutti i membri del gruppo AllowedMembers possono essere designati come Manager per le operazioni di gestione in corso nelle sale (ad esempio, le modifiche apportate all'appartenenza e l'approvazione).
  
La definizione di AllowedMembers e Creators per una categoria ha i vantaggi seguenti:
  
- Tutte le chat room di questa categoria sono associate alle restrizioni impostate a livello di categoria. Puoi usare questa funzione per separare le chat room in base alle esigenze aziendali e ai criteri di accesso.
    
- Un utente nell'elenco Creators può creare nuove chat room in quella categoria. Se si vuole implementare un sistema in cui un numero limitato di personale dell'organizzazione può creare chat room, questo controllo può essere usato per soddisfare tali requisiti. 
    
Gli utenti, le unità organizzative e i gruppi di utenti identificati come creatori della categoria sono gli unici singoli e gruppi autorizzati a creare sale nella categoria. Dopo aver creato la categoria, è possibile scegliere utenti, unità organizzative e gruppi di utenti dall'elenco di AllowedMembers della categoria come Manager e membri della chat room per gestire e partecipare alla sala. 
  
Prima di configurare le categorie, assicurati di leggere [categorie di chat persistenti, chat room e ruoli utente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).
  
È possibile configurare e gestire le categorie usando il pannello di controllo o usando i cmdlet di Windows PowerShell.

> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>Configurare le categorie tramite il pannello di controllo

1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.
    
2. Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.
    
3. Nella barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Categoria**.
    
    Per più distribuzioni di pool di server di chat persistenti, selezionare il pool appropriato nell'elenco a discesa.
    
4. Nella pagina **Categoria** fare clic su **Nuovo** o **Modifica**.
    
5. In **Seleziona un servizio**selezionare il servizio corrispondente al pool del server di chat persistente in cui deve essere creata la categoria. Il servizio è il pool di server di chat persistente usato dal client di chat persistente per identificare a quale pool appartiene la categoria. Una categoria può appartenere a un solo pool di server di chat persistente e non può essere spostata o condivisa con un altro pool.
    
6. In **Nuova categoria** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per la nuova categoria di chat.
    
   - In **Descrizione** fornire una descrizione dettagliata della categoria di chat, ad esempio una categoria di chat per Contoso.
    
   - Per controllare se gli inviti possono essere abilitati per le chat room appartenenti a questa categoria, selezionare o deselezionare la casella di controllo **Abilita invito** . Se selezionata, le camere di questa categoria possono avere inviti o disattivarli; Se deselezionata, le camere di questa categoria non possono avere inviti. Se una sala contiene inviti, quando un nuovo membro viene aggiunto a una sala, riceve una notifica della nuova sala nel client di chat persistente.
    
   - Per controllare i caricamenti file nelle chat room che appartengono a questa categoria, selezionare o deselezionare la casella di controllo **Abilita caricamento file**. Se selezionata, per le chat di questa categoria è possibile abilitare o disabilitare i caricamenti file. Se deselezionata, per le chat di questa categoria non sono consentiti caricamenti file.
    
   - Per controllare la cronologia chat, selezionare o deselezionare la casella di controllo **Abilita cronologia chat** . Se selezionata, le chat room diventano permanenti; in caso contrario, i messaggi di chat non vengono mantenuti. Se è abilitata la conformità, le chat room verranno salvate in conformità, ma gli utenti non potranno accedere ai messaggi meno recenti. Questa opzione può essere usata per le sale designate per le collaborazioni ad hoc in tempo reale che non richiedono la cronologia della chat per essere rese persistenti.
    
7. In **Modifica categoria** eseguire le operazioni seguenti:
    
   - In **appartenenza**, nella sezione **consentiti membri** , aggiungere o rimuovere utenti e altre entità di servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che sono autorizzati ad essere aggiunti come membri delle chat room appartenenza alla categoria. Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).
    
   - In **appartenenza**, nella sezione **membri negati** , aggiungere o rimuovere utenti e altre entità Active Directory associate ai membri negati dalla sala.
    
   - In **appartenenza**, nella sezione **Creators** , aggiungere o rimuovere utenti e altre entità Active Directory associate agli autori per la categoria. Per creatore si intende un utente con autorizzazioni per la creazione di chat room e l'assegnazione di membri e responsabili delle chat.
    
8. Fare clic su **Commit**.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Configurare le categorie tramite Windows PowerShell

Puoi configurare le categorie usando i cmdlet di Windows PowerShell seguenti:
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Creare una nuova categoria  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configurare le impostazioni per una categoria esistente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recuperare informazioni sulle categorie  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Rimuovere una categoria  <br/> |
   
È possibile configurare i parametri seguenti per le categorie:
  
- EnableFileUpload. Consente l'upload di file nelle chat room della categoria.
    
- EnableInvitations. Abilita gli inviti per la categoria. Gli utenti presenti nell'elenco AllowedMembers riceveranno automaticamente un invito a partecipare a una nuova chat room al momento della creazione della nuova sala.
    
- ChatHistory. Abilita o Disabilita la caratteristica cronologia chat.
    
- Creators. Specifica gli utenti autorizzati a creare chat room all'interno della categoria.
    
- AllowedMembers. Specifica gli utenti autorizzati ad accedere alle chat room all'interno della categoria.
    
- DeniedMembers. Elenca gli utenti che non sono autorizzati ad accedere alle chat room all'interno della categoria.
    
Per informazioni complete sulla sintassi dei cmdlet, inclusi tutti i parametri, vedere [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
### <a name="create-a-new-category"></a>Creare una nuova categoria

Puoi creare una nuova categoria usando il cmdlet **New-CsPersistentChatCategory** . Ad esempio, il comando seguente crea una nuova categoria denominata HelpDesk nel pool atl-cs-001.contoso.com. In questo esempio, il caricamento di file è abilitato:
  
```
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Configurare una categoria esistente

Puoi configurare una categoria esistente usando il cmdlet **set-CsPersistentCategory** .
  
Ad esempio, il comando seguente specifica che User1 è un AllowedMember e un creatore, mentre a User2 viene negato l'accesso alle camere nella categoria:
  
```
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Ottenere informazioni sulle categorie

Puoi ottenere informazioni sulle categorie usando il cmdlet **Get-CsPersistentChatCategory** . Ad esempio, il comando seguente restituisce informazioni per tutte le categorie di chat persistenti dell'organizzazione:
  
```
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Rimuovere una categoria

Puoi rimuovere una categoria usando il cmdlet **Remove-CsPersistentChatCategory** . Prima di rimuovere una categoria, è prima necessario eliminare tutte le chat room o spostarle in una nuova categoria. Ad esempio, con il comando seguente viene rimossa la categoria che contiene l'identità "atl-cs-001. contoso. com\helpdesk":
  
```
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
