---
title: Gestire gli account utente per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Le sezioni di questo articolo descrivono come abilitare, disabilitare temporaneamente o rimuovere utenti di Active Directory da Skype for Business Server.
ms.openlocfilehash: 45217593dd010c4daf73d6b5edcbf6f5f4e681a5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992403"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Gestire gli account utente per Skype for Business Server

Le sezioni di questo articolo descrivono come abilitare, disabilitare temporaneamente o rimuovere utenti di Active Directory da Skype for Business Server.

Per informazioni su come abilitare un utente di Active Directory, vedere [creare un nuovo account utente](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx). Per informazioni su come eliminare un utente di Active Directory, vedere [eliminare un account utente](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).

Queste procedure devono essere eseguite durante una finestra di manutenzione, quando l'utilizzo di Skype for business è più basso. Il fatto che venga eseguito in una programmazione giornaliera o settimanale sarà determinato dalle esigenze dell'organizzazione.

Questo articolo contiene le procedure seguenti:

- [Per cercare uno o più utenti](user-accounts.md#Search)

- [Aggiungere e abilitare un nuovo utente di Skype for Business Server](user-accounts.md#Add)

- [Disabilitare o riattivare un account utente abilitato in precedenza per Skype for Business Server](user-accounts.md#Disable)

- [Disabilitare un utente per VoIP aziendale](user-accounts.md#Disable_EV)

- [Rimuovere un account utente con Skype for Business Server Management Shell](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>Per cercare uno o più utenti
<a name="Search"> </a>

È possibile usare i risultati di una query di ricerca per configurare gli utenti di Active Directory per Skype for Business Server. È possibile cercare gli utenti per nome visualizzato, nome, cognome, nome account di gestione account di sicurezza (SAM), indirizzo SIP o URI (Uniform Resource Identifier) linea.

Puoi cercare gli utenti usando il pannello di controllo di Skype for Business Server o lo snap-in utenti e computer di Active Directory. La procedura seguente descrive come usare il pannello di controllo di Skype for Business Server per cercare gli utenti.

> [!NOTE]
> In un ambiente con una topologia di foresta centrale i risultati della ricerca potrebbero non essere precisi quando si cerca un utente tramite l'indirizzo di posta elettronica dell'utente. È invece possibile cercare gli utenti specificando un prefisso di indirizzo SIP, ad esempio SIP: Name, aggiungere un filtro di ricerca e selezionare un indirizzo SIP che contiene un indirizzo di posta elettronica parziale oppure usare il cmdlet **Get-CSUser** .

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3. Sulla barra di spostamento sinistra fare clic su **utenti**.

4. Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome dell'account SAM, indirizzo SIP o URI di linea dell'account utente che si desidera cercare e quindi fare clic su **trova**.

5. Opzionale Specificare altri criteri di ricerca per restringere i risultati:

   un. Fare clic sul pulsante Espandi freccia nell'angolo in alto a destra dello schermo sopra i **Risultati della ricerca**e quindi fare clic su **Aggiungi filtro**.

   b. Immettere la proprietà User digitando o facendo clic sulla freccia nell'elenco a discesa per selezionare una proprietà utente.

   c. Nell'elenco **uguale a** fare clic su **uguale** a o **non uguale a**.

   3D. Nella casella di testo digitare i criteri di ricerca che si desidera utilizzare per filtrare i risultati della ricerca e quindi fare clic su **trova**.

6. I risultati della ricerca vengono visualizzati nei **Risultati della ricerca**. È possibile selezionare uno o tutti gli utenti nell'elenco ed eseguire attività di configurazione per gli utenti selezionati.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Aggiungere e abilitare un nuovo utente di Skype for Business Server
<a name="Add"> </a>

Dopo l'abilitazione di un account utente in utenti e computer di Active Directory, è possibile usare il pannello di controllo di Skype for Business Server per creare e abilitare nuovi account utente di Skype for Business Server aggiungendo un utente di Active Directory a Skype for Business Server.

Puoi anche usare un cmdlet, in particolare [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3. Sulla barra di spostamento sinistra fare clic su **utenti**.

4. Fare clic su **Abilita utenti**.

5. Nella finestra di dialogo **nuovo utente di Lync Server** fare clic su **Aggiungi**.

6. Nella casella **Cerca utenti** digitare tutto o la prima parte del nome, il nome visualizzato, il nome, il cognome, il nome dell'account SAM (Security Accounts Manager), l'indirizzo di posta elettronica, il nome dell'entità utente (UPN) o il numero di telefono dell'account utente di Active Directory desiderato e quindi fare clic su **trova**.

7. Nella tabella selezionare l'account che si vuole aggiungere a Skype for Business Server e quindi fare clic su **OK**.

8. Assegnare l'utente a un pool, specificare eventuali dettagli aggiuntivi e assegnare i criteri all'utente desiderato e quindi fare clic su **Abilita**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Disabilitare o riattivare un account utente abilitato in precedenza per Skype for Business Server
<a name="Disable"> </a>

È possibile usare la procedura seguente per disabilitare un account utente abilitato in precedenza in Skype for Business Server senza perdere le impostazioni di Skype for Business Server configurate per l'account utente. Dato che le impostazioni dell'account utente di Skype for Business Server non vengono perse, è possibile riattivare nuovamente un account utente abilitato in precedenza senza dover riconfigurare l'account utente.

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3. Sulla barra di spostamento sinistra fare clic su **utenti**.

4. Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si desidera disabilitare o riabilitare e quindi fare clic su **trova**.

5. Nella tabella fare clic sull'account utente che si vuole disabilitare o riattivare.

6. Nel menu **azione** eseguire una delle operazioni seguenti:

   - Per disabilitare temporaneamente l'account utente per Skype for Business Server, fare clic su **Disabilita temporaneamente per Lync Server**.

   - Per abilitare l'account utente per Skype for Business Server, fare clic su **riattiva per Lync Server**.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Usare Windows PowerShell per disabilitare o riattivare gli account utente

Gli account utente possono essere temporaneamente disabilitati e quindi riattivati in seguito usando il cmdlet **Set-CsUser** . Puoi eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.

### <a name="to-disable-a-user-account"></a>Per disabilitare un account utente

- Per disabilitare temporaneamente un account utente, imposta il valore della proprietà Enabled su false ($False). Ad esempio:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>Per riattivare un account utente

- Per riattivare un account utente disabilitato, imposta il valore della proprietà Enabled su true ($True). Ad esempio:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .

## <a name="disable-a-user-for-enterprise-voice"></a>Disabilitare un utente per VoIP aziendale
<a name="Disable_EV"> </a>

Usare la procedura seguente per disabilitare VoIP aziendale per un account utente abilitato per Skype for Business Server.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>Per disabilitare un account utente per VoIP aziendale

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3. Sulla barra di spostamento sinistra fare clic su **utenti**.

4. Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si vuole abilitare e quindi fare clic su **trova**.

5. Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.

6. Nel menu **modifica** fare clic su **Mostra dettagli**.

7. Nella pagina **modifica utente di Lync Server** , in **telefonia**, fare clic su qualsiasi opzione eccetto **VoIP aziendale**.

    > [!NOTE]
    > Per impedire a un utente di effettuare chiamate audio o video tramite Lync, in **telefonia**fare clic su **disabilitato audio/video**.

8. Fare clic su **Commit**.

Ora l'utente non è in grado di usare la caratteristica VoIP aziendale. Informazioni correlate: <br/>[VoIP aziendale e mobilità](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Consentire agli utenti di VoIP aziendale in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server Management Shell](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Rimuovere un account utente con Skype for Business Server Management Shell
<a name="Remove"> </a>

È possibile usare la procedura seguente per rimuovere un account utente aggiunto in precedenza in Skype for Business Server.

> [!NOTE]
> La rimozione di un utente causerà la perdita di tutte le impostazioni configurate per l'account utente. Se invece si vuole disabilitare temporaneamente un account utente, vedere [disabilitare o riabilitare un account utente abilitato in precedenza per Skype for Business Server](user-accounts.md#Disable).

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.

3. Sulla barra di spostamento sinistra fare clic su **utenti**.

4. Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si desidera disabilitare o riabilitare e quindi fare clic su **trova**.

5. Nella tabella fare clic sull'account utente che si vuole rimuovere.

6. Nel menu **azione** selezionare **Rimuovi da Lync Server**e viene visualizzata una finestra di dialogo.

7. Nella finestra di dialogo selezionare **OK** per rimuovere l'utente.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Rimuovere gli account utente con i cmdlet di Windows PowerShell

Puoi rimuovere gli account utente usando il cmdlet Disable-CsUser. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Skype for Business Server, vedere l'articolo di Blog ["Guida introduttiva: gestione di Microsoft Lync Server 2010 con Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Il processo è lo stesso in Skype for Business Server.

### <a name="to-remove-a-user-account"></a>Per rimuovere un account utente
Per rimuovere un account utente, usare il cmdlet Disable-CsUser. Ad esempio:

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .

## <a name="see-also"></a>Vedere anche
<a name="Remove"> </a>

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
