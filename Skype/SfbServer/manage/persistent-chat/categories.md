---
title: Gestire le categorie nel server Chat persistente in Skype for Business Server 2015
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
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 'Riepilogo: informazioni su come gestire le categorie del server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 86a90143bad43f4bb8a96434885eec741c01f4a4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853010"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestire le categorie nel server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come gestire le categorie del server Chat persistente in Skype for Business Server 2015.
  
Una categoria è una struttura logica per l'organizzazione delle chat room. Una categoria definisce un set predefinito di elenchi di controllo di accesso (ACL) per il controllo degli utenti e dei gruppi di utenti che possono creare o partecipare alle chat room. Le categorie di chat contengono chat room, ma non altre categorie. Ogni categoria descrive il relativo contenuto con metadati, come Nome e Descrizione. La categoria dispone di proprietà che possono essere impostate per controllare il comportamento delle chat room ad essa appartenenti; ad esempio se le chat room consentono inviti o caricamenti di file o contengono Cronologia chat. 
  
La creazione e la gestione delle chat room è molto più semplice con l'uso corretto delle categorie. In quanto amministratore del server Chat persistente, è possibile definire AllowedMembers e Creators per ogni categoria, nonché definire le impostazioni e i comportamenti predefiniti delle chat room che verranno applicati a tutte le chat room create nella categoria. Ad esempio, se si imposta allowedMembers della categoria su contoso.com, è possibile aggiungere qualsiasi gruppo o utente in Contoso come membro alle chat room di tale categoria. Se si imposta l'opzione Membri consentiti per una categoria su Vendite, solo i gruppi e gli utenti della lista di distribuzione possono essere aggiunti come membri alle chat room di tale categoria. La proprietà Creators consente di controllare chi può creare chat room in tale categoria. Dopo la creazione della chat room, tutti gli utenti del gruppo AllowedMembers possono essere designati come manager per le operazioni di gestione in corso sulle chat room (ad esempio, modifiche all'appartenenza e approvazione).
  
La definizione di AllowedMembers e Creators per una categoria ha i vantaggi seguenti:
  
- Tutte le chat room nella categoria sono vincolate da restrizioni impostate a livello di categoria. È possibile usare questo aspetto per isolare le chat room in base ai criteri di accesso e alle esigenze aziendali.
    
- Un utente incluso nell'elenco Creator può creare nuove chat room nella categoria. Se si desidera implementare un sistema in cui un numero limitato di persone nell'organizzazione può creare chat room, questo controllo può essere utilizzato per soddisfare tali requisiti. 
    
Gli utenti, le unità organizzative (OU) e i gruppi di utenti identificati come creatori della categoria sono gli unici utenti e gruppi a cui è consentito creare chat room nella categoria. Dopo aver creato la categoria, è possibile scegliere utenti, unità organizzative e gruppi di utenti nell'elenco AllowedMembers della categoria come responsabili e membri della chat room per gestire e partecipare alla chat room. 
  
Prima di configurare le categorie, leggere Categorie di Chat persistente, chat room e ruoli utente [in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).
  
È possibile configurare e gestire le categorie utilizzando il Pannello di controllo o Windows PowerShell cmdlet.

> [!NOTE]
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento.](/microsoftteams/upgrade-start-here) Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>Configurare le categorie tramite il Pannello di controllo

1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il pannello Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Categoria**.
    
    Per più distribuzioni di pool di server Chat persistente, selezionare il pool appropriato nell'elenco a discesa.
    
4. Nella pagina **Categoria** fare clic su **Nuovo** o **Modifica**.
    
5. In **Selezionare un servizio** selezionare il servizio corrispondente al pool di server Chat persistente in cui deve essere creata la categoria. Il servizio è il pool di server Chat persistente utilizzato dal client Chat persistente per identificare il pool a cui appartiene la categoria. Una categoria può appartenere a un solo pool di server Chat persistente e non può essere spostata o condivisa con un altro pool.
    
6. In **Nuova categoria** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per la nuova categoria di chat.
    
   - In **Descrizione** fornire una descrizione dettagliata della categoria di chat, ad esempio una categoria di chat per Contoso.
    
   - Per controllare l'abilitazione di inviti nelle chat room appartenenti a questa categoria, selezionare o deselezionare la casella di controllo **Abilita inviti**. Se l'opzione viene selezionata, le chat di questa categoria possono avere inviti attivati o disattivati; se invece viene deselezionata, alle chat di questa categoria non è consentito avere inviti. Se una sala dispone di inviti, quando un nuovo membro viene aggiunto a una sala, riceve una notifica della nuova chat nel client Persistent Chat.
    
   - Per controllare i caricamenti file nelle chat room che appartengono a questa categoria, selezionare o deselezionare la casella di controllo **Abilita caricamento file**. Se selezionata, per le chat di questa categoria è possibile abilitare o disabilitare i caricamenti file. Se deselezionata, per le chat di questa categoria non sono consentiti caricamenti file.
    
   - Per controllare la cronologia delle chat, selezionare o deselezionare la casella di controllo **Abilita cronologia chat.** Se la casella è selezionata, le chat room diventano persistenti, in caso contrario i messaggi delle chat non diventano persistenti. Se è abilitata la conformità, le chat room verranno salvate nella conformità, ma gli utenti non potranno accedere ai messaggi datati. Questa opzione può essere utilizzata per le sale designate per le collaborazioni ad hoc in tempo reale che non necessitano di salvare in modo permanente la cronologia delle chat.
    
7. In **Modifica categoria** eseguire le operazioni seguenti:
    
   - In Appartenenza,  nella sezione Membri consentiti, aggiungere o rimuovere utenti e altre entità di Servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che possono essere aggiunte come membri delle chat room appartenenti alla categoria. Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).
    
   - In **Appartenenza**, nella **sezione Membri** negati aggiungere o rimuovere utenti e altre entità di Active Directory associate ai membri negati dalla chat room.
    
   - In **Appartenenza,** nella **sezione Creatori,** aggiungere o rimuovere utenti e altre entità di Active Directory associate ai creatori per la categoria. Per creatore si intende un utente con autorizzazioni per la creazione di chat room e l'assegnazione di membri e responsabili delle chat.
    
8. Fare clic su **Commit**.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Configurare le categorie tramite Windows PowerShell

È possibile configurare le categorie utilizzando i cmdlet Windows PowerShell seguenti:
  

|**Cmdlet**|**Descrizione**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Creare una nuova categoria  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configurare le impostazioni per una categoria esistente  <br/> |
|Get-CsPersistentChatCategory  <br/> |Recuperare informazioni sulle categorie  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Rimuovere una categoria  <br/> |
   
È possibile configurare i parametri seguenti per le categorie:
  
- EnableFileUpload. Consente il caricamento di file nelle chat room della categoria.
    
- EnableInvitations. Abilita gli inviti per la categoria. Gli utenti nell'elenco AllowedMembers riceveranno automaticamente un invito a partecipare a una nuova chat room al momento della creazione della nuova chat room.
    
- ChatHistory. Abilita o disabilita la funzionalità cronologia chat.
    
- Creatori. Specifica gli utenti a cui è consentito creare chat room all'interno della categoria.
    
- AllowedMembers. Specifica gli utenti a cui è consentito accedere alle chat room all'interno della categoria.
    
- DeniedMembers. Elenca gli utenti non autorizzati ad accedere alle chat room incluse nella categoria.
    
Per informazioni complete sulla sintassi dei cmdlet, inclusi tutti i parametri, [vedere Skype for Business Server 2015 Management Shell.](../management-shell.md)
  
### <a name="create-a-new-category"></a>Creare una nuova categoria

È possibile creare una nuova categoria utilizzando il cmdlet **New-CsPersistentChatCategory.** Ad esempio, il comando seguente crea una nuova categoria denominata HelpDesk nel pool atl-cs-001.contoso.com. In questo esempio il caricamento dei file è abilitato:
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Configurare una categoria esistente

È possibile configurare una categoria esistente utilizzando il cmdlet **Set-CsPersistentCategory.**
  
Ad esempio, il comando seguente specifica che user1 è allowedMember e Creator, mentre a user2 viene negato l'accesso alle chat room della categoria:
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Ottenere informazioni sulle categorie

È possibile ottenere informazioni sulle categorie utilizzando il cmdlet **Get-CsPersistentChatCategory.** Ad esempio, il comando seguente restituisce informazioni per tutte le categorie di Persistent Chat nell'organizzazione:
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Rimuovere una categoria

È possibile rimuovere una categoria utilizzando il cmdlet **Remove-CsPersistentChatCategory.** Prima di rimuovere una categoria, è innanzitutto necessario eliminare tutte le chat room al di sotto di essa o spostare le chat room in una nuova categoria. Ad esempio, il comando seguente rimuove la categoria con identità "atl-cs-001.contoso.com\helpdesk":
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
