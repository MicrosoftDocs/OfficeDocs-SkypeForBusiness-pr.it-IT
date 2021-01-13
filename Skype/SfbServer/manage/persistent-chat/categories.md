---
title: Gestire le categorie nel server Chat persistente in Skype for Business Server 2015
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
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 'Riepilogo: informazioni su come gestire le categorie di server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 648629e42994c59f5d6ba5ee5592729f4dff0bbe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815126"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestire le categorie nel server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come gestire le categorie del server Chat persistente in Skype for Business Server 2015.
  
Una categoria è una struttura logica per l'organizzazione delle chat room. Una categoria definisce un set predefinito di elenchi di controllo di accesso (ACL, Access Control List) per il controllo degli utenti e dei gruppi di utenti che possono creare o partecipare alle chat room. Le categorie delle chat room contengono chat, ma non altre categorie. Ogni categoria descrive il relativo contenuto con metadati, come Nome e Descrizione. La categoria contiene proprietà che possono essere impostate per controllare il comportamento delle chat room che lo appartengono. ad esempio, se le chat room consentono inviti o caricamenti di file oppure contengono cronologia chat. 
  
La creazione e la gestione delle chat room è molto più semplice con il corretto utilizzo delle categorie. Come amministratore del server Chat persistente, è possibile definire AllowedMembers e creatori per ogni categoria e definire anche le impostazioni e i comportamenti predefiniti della chat room che verranno applicati a tutte le chat room create nella categoria. Ad esempio, se si imposta la categoria AllowedMembers su contoso.com, è possibile aggiungere qualsiasi gruppo o utente a Contoso come membro delle chat room della categoria. Se si impostano i membri consentiti di una categoria per le vendite, solo i gruppi e gli utenti della lista di distribuzione possono essere aggiunti come membri alle chat room della categoria. La proprietà Creators consente di controllare gli utenti che possono creare chat room in quella categoria. Dopo aver creato la chat room, tutti i membri del gruppo AllowedMembers possono essere designati come Manager per le operazioni di gestione in uscita nelle sale (ad esempio, modifiche e approvazione dell'appartenenza).
  
La definizione di AllowedMembers e Creators per una categoria ha i vantaggi seguenti:
  
- Tutte le chat room nella categoria sono vincolate da restrizioni impostate a livello di categoria. È possibile usare questo aspetto per isolare le chat room in base ai criteri di accesso e alle esigenze aziendali.
    
- Un utente incluso nell'elenco Creator può creare nuove chat room nella categoria. Se si desidera implementare un sistema in cui un numero limitato di personale nell'organizzazione possa creare chat room, è possibile utilizzare questo controllo per soddisfare i requisiti. 
    
Gli utenti, le unità organizzative (OU) e i gruppi di utenti identificati come creatori della categoria sono gli unici singoli e gruppi autorizzati a creare sale nella categoria. Dopo aver creato la categoria, è possibile scegliere gli utenti, le unità organizzative e i gruppi di utenti dall'elenco AllowedMembers della categoria come Manager e membri della chat room per gestire e partecipare all'ambiente. 
  
Prima di configurare le categorie, leggere categorie di chat [persistente, chat room e ruoli utente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).
  
È possibile configurare e gestire le categorie utilizzando il pannello di controllo o i cmdlet di Windows PowerShell.

> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>Configurare le categorie utilizzando il pannello di controllo

1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Categoria**.
    
    Per più distribuzioni di pool di server Chat persistente, selezionare il pool appropriato dall'elenco a discesa.
    
4. Nella pagina **Categoria** fare clic su **Nuovo** o **Modifica**.
    
5. In **Seleziona un servizio** selezionare il servizio corrispondente al pool di server Chat persistente in cui deve essere creata la categoria. Il servizio è il pool di server Chat persistente utilizzato dal client di chat persistente per identificare il pool a cui appartiene la categoria. Una categoria può appartenere a un solo pool di server Chat persistente e non può essere spostata o condivisa con un altro pool.
    
6. In **Nuova categoria** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per la nuova categoria di chat.
    
   - In **Descrizione** fornire una descrizione dettagliata della categoria di chat, ad esempio una categoria di chat per Contoso.
    
   - Per controllare l'abilitazione di inviti nelle chat room appartenenti a questa categoria, selezionare o deselezionare la casella di controllo **Abilita inviti**. Se l'opzione viene selezionata, le chat di questa categoria possono avere inviti attivati o disattivati; se invece viene deselezionata, alle chat di questa categoria non è consentito avere inviti. Se una chat room contiene inviti, quando un nuovo membro viene aggiunto a una sala, riceve una notifica della nuova sala nel client di chat persistente.
    
   - Per controllare i caricamenti file nelle chat room che appartengono a questa categoria, selezionare o deselezionare la casella di controllo **Abilita caricamento file**. Se selezionata, per le chat di questa categoria è possibile abilitare o disabilitare i caricamenti file. Se deselezionata, per le chat di questa categoria non sono consentiti caricamenti file.
    
   - Per controllare la cronologia della chat, seleziona o deseleziona la casella di controllo **Abilita cronologia chat** . Se la casella è selezionata, le chat room diventano persistenti, in caso contrario i messaggi delle chat non diventano persistenti. Se è abilitata la conformità, le chat room verranno salvate nella conformità, ma gli utenti non potranno accedere ai messaggi datati. Questa opzione può essere utilizzata per le sale designate per le collaborazioni ad hoc in tempo reale che non necessitano di una cronologia chat.
    
7. In **Modifica categoria** eseguire le operazioni seguenti:
    
   - In **appartenenza**, nella sezione **consentito membri** , aggiungere o rimuovere utenti e altre entità di servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che possono essere aggiunti come membri delle chat room appartenenti alla categoria. Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).
    
   - In **appartenenza**, nella sezione **membri negati** , aggiungere o rimuovere utenti e altre entità Active Directory associate ai membri che vengono negati dalla sala.
    
   - In **appartenenza**, nella sezione **creatori** , aggiungere o rimuovere utenti e altre entità Active Directory associate ai creatori per la categoria. Per creatore si intende un utente con autorizzazioni per la creazione di chat room e l'assegnazione di membri e responsabili delle chat.
    
8. Fare clic su **Commit**.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Configurare le categorie tramite Windows PowerShell

È possibile configurare le categorie utilizzando i cmdlet di Windows PowerShell seguenti:
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Creare una nuova categoria  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configurare le impostazioni per una categoria esistente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recuperare le informazioni sulle categorie  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Rimuovere una categoria  <br/> |
   
È possibile configurare i seguenti parametri per le categorie:
  
- EnableFileUpload. Consente i caricamenti di file nelle chat room della categoria.
    
- EnableInvitations. Attiva gli inviti per la categoria. Gli utenti nell'elenco AllowedMembers riceveranno automaticamente un invito a partecipare a una nuova chat room nel momento in cui viene creata la nuova sala.
    
- ChatHistory. Attiva o disattiva la funzionalità cronologia chat.
    
- Creators. Specifica gli utenti autorizzati a creare chat room all'interno della categoria.
    
- AllowedMembers. Specifica gli utenti autorizzati ad accedere alle chat room all'interno della categoria.
    
- DeniedMembers. Elenca gli utenti non autorizzati ad accedere alle chat room incluse nella categoria.
    
Per informazioni complete sulla sintassi dei cmdlet, inclusi tutti i parametri, vedere [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
### <a name="create-a-new-category"></a>Creare una nuova categoria

È possibile creare una nuova categoria utilizzando il cmdlet **New-CsPersistentChatCategory** . Ad esempio, il comando seguente crea una nuova categoria denominata HelpDesk nel pool atl-cs-001.contoso.com. In questo esempio viene abilitato il caricamento del file:
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Configurare una categoria esistente

È possibile configurare una categoria esistente utilizzando il cmdlet **set-CsPersistentCategory** .
  
Ad esempio, il comando seguente specifica che User1 è un AllowedMember e un creatore, mentre a User2 è negato l'accesso alle sale della categoria:
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Ottenere informazioni sulle categorie

È possibile ottenere informazioni sulle categorie utilizzando il cmdlet **Get-CsPersistentChatCategory** . Ad esempio, il comando seguente restituisce informazioni su tutte le categorie di Persistent Chat nell'organizzazione:
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Rimuovere una categoria

È possibile rimuovere una categoria utilizzando il cmdlet **Remove-CsPersistentChatCategory** . Prima di rimuovere una categoria, è necessario prima eliminare tutte le chat room o spostare le chat room in una nuova categoria. Ad esempio, il comando seguente consente di rimuovere la categoria con identità "atl-cs-001. contoso. com\helpdesk":
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
