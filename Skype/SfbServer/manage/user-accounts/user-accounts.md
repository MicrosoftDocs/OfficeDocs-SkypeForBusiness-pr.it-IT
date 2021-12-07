---
title: Gestire gli account utente per Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Nelle sezioni di questo articolo viene descritto come abilitare, disabilitare temporaneamente o rimuovere gli utenti di Active Directory Skype for Business Server.
ms.openlocfilehash: 39016a83c11553cd39448efa34d61ffbba5045e9
ms.sourcegitcommit: 2aae13454178dc2e2cbc8cca967cd181c5f9d044
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2021
ms.locfileid: "61314214"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Gestire gli account utente per Skype for Business Server

Nelle sezioni di questo articolo viene descritto come abilitare, disabilitare temporaneamente o rimuovere gli utenti di Active Directory Skype for Business Server.

Per informazioni su come abilitare un utente di Active Directory, vedere [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)). Per informazioni su come eliminare un utente di Active Directory, vedere [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).

Queste procedure devono essere eseguite durante una finestra di manutenzione, quando l Skype for Business'utilizzo è minimo. L'eventuale esecuzione di questa operazione in base a una pianificazione giornaliera o settimanale dipende dalle esigenze dell'organizzazione.

In questo articolo sono contenute le procedure seguenti:

- [Cercare uno o più utenti](#search-for-one-or-more-users)

- [Aggiungere e abilitare un nuovo Skype for Business Server utente](#add-and-enable-a-new-skype-for-business-server-user)

- [Disabilitare o riattivare un account utente per Skype for Business Server](#disable-or-re-enable-a-user-account-for-skype-for-business-server)

- [Disabilitare un utente per VoIP aziendale](#disable-a-user-for-enterprise-voice)

- [Rimuovere un account utente con Skype for Business Server Management Shell](#remove-a-user-account-with-the-skype-for-business-server-management-shell)

## <a name="search-for-one-or-more-users"></a>Cercare uno o più utenti

È possibile utilizzare i risultati di una query di ricerca per configurare gli utenti di Active Directory per Skype for Business Server. È possibile ricercare utenti in base al nome visualizzato, al nome, al cognome, al nome dell'account SAM (Security Accounts Manager), all'indirizzo SIP o all'URI (Uniform Resource Identifier) della linea.

È possibile cercare utenti utilizzando il Skype for Business Server o lo snap-in Utenti e computer di Active Directory. Nella procedura seguente viene descritto come utilizzare il Skype for Business Server di controllo per cercare utenti.

> [!NOTE]
> In un ambiente con una topologia a foresta centrale, i risultati della ricerca potrebbero non essere accurati quando si cerca un utente in base all'indirizzo di posta elettronica dell'utente. È invece possibile cercare utenti specificando un prefisso di indirizzo SIP, ad esempio sip:name, aggiungere un filtro di ricerca e selezionare un indirizzo SIP contenente un indirizzo di posta elettronica parziale oppure utilizzare il cmdlet **Get-CSUser.**

### <a name="search-for-users-using-the-new-control-panel"></a>Cercare utenti usando il nuovo Pannello di controllo 

1. Apri una finestra del browser e immetti l'URL di amministratore per aprire il pannello Skype for Business Server pannello di controllo.
 
2. Accedere utilizzando un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator.

3. Nel riquadro sinistro selezionare **Utenti**.

4. Nella **casella** Cerca della  pagina Utenti digitare tutto o la prima parte del nome visualizzato che si desidera cercare e premere **INVIO.**

5. (Facoltativo) Specificare ulteriori criteri di ricerca per limitare i risultati:

    1. Fare clic sul pulsante filtro accanto alla **casella** Di ricerca.

    2. Nel riquadro **Filtro** visualizzato selezionare la proprietà utente richiesta facendo clic sulla freccia nell'elenco a discesa.

    3. Fare clic sulla freccia nell'elenco a discesa dell'operatore per selezionare l'operatore necessario.

    4. Nella casella di testo digitare i criteri di ricerca che si desidera utilizzare per filtrare i risultati della ricerca e quindi fare clic su **OK.**

6. I risultati della ricerca vengono visualizzati nella **pagina** Utenti. È possibile selezionare uno o tutti gli utenti dell'elenco ed eseguire attività di configurazione sugli utenti selezionati.

> [!NOTE]
> Il nuovo Pannello di controllo non è disponibile per Skype for Business Server 2015.

### <a name="search-for-users-using-the-legacy-control-panel"></a>Cercare utenti usando il Pannello di controllo legacy 

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.

3. Nel riquadro sinistro selezionare **Utenti**.

4. Nella casella **Ricerca utenti** digitare interamente o parzialmente il nome visualizzato, il nome, il cognome, il nome account SAM, l'indirizzo SIP o l'URI linea dell'account utente da ricercare e quindi fare clic su **Trova**.

5. (Facoltativo) Specificare ulteriori criteri di ricerca per circoscrivere i risultati:

    1. Fare clic sul pulsante freccia di espansione nell'angolo in alto a destra della schermata al di sopra di **Risultati della ricerca** e quindi fare clic su **Aggiungi filtro**.

    2. Immettere la proprietà utente digitandolo o facendo clic sulla freccia nell'elenco a discesa per selezionare una proprietà utente.

    3. **Nell'elenco Uguale a** selezionare Uguale **a** o **Diverso da**.

    4. Nella casella di testo digitare i criteri di ricerca che si desidera utilizzare per filtrare i risultati della ricerca e quindi fare clic su **Trova**.

6. I risultati della ricerca verranno visualizzati al di sotto di **Risultati della ricerca**. È possibile selezionare uno o tutti gli utenti dell'elenco ed eseguire attività di configurazione sugli utenti selezionati.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Aggiungere e abilitare un nuovo Skype for Business Server utente

Dopo aver abilitato un account utente in Utenti e computer di Active Directory, è possibile utilizzare il Pannello di controllo di Skype for Business Server per creare e abilitare nuovi account utente di Skype for Business Server aggiungendo un utente di Active Directory a Skype for Business Server.

È inoltre possibile utilizzare un cmdlet, in particolare [Enable-CsUser.](/powershell/module/skype/enable-csuser)

### <a name="add-a-user-using-the-new-control-panel"></a>Aggiungere un utente usando il nuovo Pannello di controllo 

1. Apri una finestra del browser e immetti l'URL di amministratore per aprire il pannello Skype for Business Server pannello di controllo.
 
2. Accedere utilizzando un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator.

3. Passare a **Utenti**  >  **Abilita utenti** e fare clic su **Aggiungi.**

4. Nella casella **Cerca** digitare tutto o la prima parte del nome visualizzato e fare clic su **Trova**.

5. (Facoltativo) Per specificare ulteriori criteri utente, fare **clic su + Aggiungi** filtro, selezionare la proprietà utente richiesta, selezionare l'operatore e immettere il valore. Fare clic su **Trova**.

6. Nella tabella selezionare l'account che si desidera aggiungere Skype for Business Server e quindi fare clic su **OK.**

7. Assegnare l'utente a un pool, specificare eventuali dettagli aggiuntivi e assegnare i criteri necessari all'utente e quindi fare clic su **Abilita**.

> [!NOTE]
> Il nuovo Pannello di controllo non è disponibile per Skype for Business Server 2015.

### <a name="add-a-user-using-the-legacy-control-panel"></a>Aggiungere un utente usando il Pannello di controllo legacy 

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.

3. Passare a **Utenti**  >  **Abilita utenti** Nuovo utente di Lync  >  **Server** e fare clic su **Aggiungi.**

6. Nella casella **Ricerca utenti** digitare il nome intero o parziale, il nome visualizzato, il nome, il cognome, il nome account del sistema degli account di sicurezza (SAM), l'indirizzo di posta elettronica, il nome dell'entità utente o il numero di telefono dell'account utente di Active Directory desiderato e quindi fare clic su **Trova**.

7. Nella tabella selezionare l'account che si desidera aggiungere Skype for Business Server e quindi fare clic su **OK.**

8. Assegnare l'utente a un pool, specificare eventuali dettagli aggiuntivi, assegnare i criteri all'utente desiderato e quindi fare clic su **Abilita**.

## <a name="disable-or-re-enable-a-user-account-for-skype-for-business-server"></a>Disabilitare o riattivare un account utente per Skype for Business Server

È possibile utilizzare la procedura seguente per disabilitare un account utente abilitato in precedenza in Skype for Business Server senza perdere le impostazioni Skype for Business Server configurate per l'account utente. Poiché non si perdono le impostazioni Skype for Business Server account utente, è possibile riconfigurare un account utente abilitato in precedenza senza dover riconfigurare l'account utente.

### <a name="disable-or-re-enable-a-user-account-using-the-new-control-panel"></a>Disabilitare o riattivare un account utente utilizzando il nuovo Pannello di controllo

1. Apri una finestra del browser e immetti l'URL di amministratore per aprire il pannello Skype for Business Server pannello di controllo.
 
2. Accedere utilizzando un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator.

3. Nel riquadro sinistro selezionare **Utenti**.

4. Nella **casella** Cerca della  pagina Utenti digitare tutto o la prima parte del nome visualizzato e premere **INVIO.**

5. Nella tabella fare doppio clic sull'account utente che si desidera disabilitare o riattivare.
    1. Nel riquadro visualizzato, per disabilitare temporaneamente l'account utente per Skype for Business Server, selezionare **Disabilita utente**. Nel riquadro visualizzato fare clic su **Salva.**
    2. Per abilitare nuovamente l'account utente per Skype for Business Server, nel pannello seleziona **Ri-abilita utente.** Nel riquadro successivo visualizzato fare clic su **Salva.**

> [!NOTE]
> Il nuovo Pannello di controllo non è disponibile per Skype for Business Server 2015.

### <a name="disable-or-re-enable-a-user-account-using-the-legacy-control-panel"></a>Disabilitare o riattivare un account utente utilizzando il Pannello di controllo legacy

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.

3. Nel riquadro sinistro selezionare **Utenti**.

4. Nella casella **Cerca utenti** digitare tutto o solo la prima parte del nome visualizzato, del nome, del cognome, del nome di account SAM (Security Accounts Manager), dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) linea dell'account utente che si desidera disabilitare o abilitare di nuovo e quindi fare clic su **Trova**.

5. Nella tabella fare clic sull'account utente che si desidera disabilitare o abilitare di nuovo.

6. Dal menu **Azione** scegliere uno dei comandi seguenti:
   1. Per disabilitare temporaneamente l'account utente per Skype for Business Server, selezionare **Disabilita temporaneamente per Lync Server.**
   2. Per abilitare l'account utente per Skype for Business Server, selezionare **Ri-abilita per Lync Server.**
  
### <a name="disable-or-re-enable-user-accounts-using-windows-powershell"></a>Disabilitare o riattivare gli account utente Windows PowerShell

Gli account utente possono essere temporaneamente disabilitati e quindi ri abilitati in un secondo momento utilizzando il cmdlet **Set-CsUser.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remota per connettersi a Skype for Business Server, vedere Amministrazione remota di PowerShell per [Microsoft Lync.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) Il processo è lo stesso in Skype for Business Server.

### <a name="to-disable-a-user-account-using-windows-powershell"></a>Per disabilitare un account utente tramite Windows PowerShell

- Per disabilitare temporaneamente un account utente, impostare il valore della proprietà enabled su False ($False). Ad esempio:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account-using-windows-powershell"></a>Per abilitare di nuovo un account utente tramite Windows PowerShell

- Per abilitare nuovamente un account utente disabilitato, impostare il valore della proprietà enabled su True ($True). Ad esempio:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsUser.](/powershell/module/skype/set-csuser)

## <a name="disable-a-user-for-enterprise-voice"></a>Disabilitare un utente per VoIP aziendale

Utilizzare la procedura seguente per disabilitare VoIP aziendale per un account utente abilitato per Skype for Business Server.

### <a name="disable-a-user-for-enterprise-voice-using-new-control-panel"></a>Disabilitare un utente per VoIP aziendale nuovo Pannello di controllo

1. Apri una finestra del browser e immetti l'URL di amministratore per aprire il pannello Skype for Business Server pannello di controllo.
 
2. Accedere utilizzando un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator.

3. Nel riquadro sinistro fare clic su **Utenti**.

4. Nella casella **Cerca** digitare tutto o la prima parte del nome visualizzato e fare clic su **Trova**.

5. Nella tabella fare doppio clic sull'account utente che si desidera disabilitare per VoIP aziendale.

6. Nel riquadro visualizzato fare clic sull'icona a forma di matita accanto a **Criteri assegnati.**

7. Nel pannello **Criteri assegnati,** in **Telefonia,** fai clic su qualsiasi opzione **ad VoIP aziendale** nell'elenco a discesa.

8. Fare clic su **Salva**.

    > [!NOTE]
    > Per impedire a un utente di effettuare chiamate audio o video, in **Telefonia** fare clic **su Audio/Video disabilitato.**

L'utente non è ora in grado di usare la VoIP aziendale funzionalità. 

> [!NOTE]
> Il nuovo Pannello di controllo non è disponibile per Skype for Business Server 2015.

### <a name="disable-a-user-account-for-enterprise-voice-using-legacy-control-panel"></a>Disabilitare un account utente per VoIP aziendale pannello di controllo legacy

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.

3. Nel riquadro sinistro fare clic su **Utenti**.

4. Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.

5. Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.

6. Scegliere **Mostra dettagli** dal menu **Modifica**.

7. Nella pagina **Modifica utente Lync Server**, in **Telefonia** fare clic su qualsiasi opzione, ad eccezione di **VoIP aziendale**.

    > [!NOTE]
    > Per impedire a un utente di effettuare chiamate audio o video tramite Lync, in **Telefonia** fare clic **su Audio/video disabilitato.**

8. Fare clic su **Commit**.

L'utente non è ora in grado di usare la VoIP aziendale funzionalità.

Informazioni correlate: <br/>[VoIP aziendale e mobilità](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [Abilitare gli utenti per VoIP aziendale in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server Management Shell](../management-shell.md)

## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Rimuovere un account utente con Skype for Business Server Management Shell

È possibile utilizzare la procedura seguente per rimuovere un account utente aggiunto in precedenza in Skype for Business Server.

> [!NOTE]
> La rimozione di un utente comporterà la perdita delle impostazioni configurate per l'account utente. Se invece si desidera disabilitare temporaneamente un account utente, vedere Disabilitare o [riattivare](#disable-or-re-enable-a-user-account-for-skype-for-business-server)un account utente abilitato in precedenza per Skype for Business Server .

### <a name="remove-a-user-using-the-new-control-panel"></a>Rimuovere un utente tramite il nuovo Pannello di controllo

1. Apri una finestra del browser e immetti l'URL di amministratore per aprire il pannello Skype for Business Server pannello di controllo.
 
2. Accedere utilizzando un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator.

3. Nel riquadro sinistro selezionare **Utenti**.

4. Nella casella **Cerca** digitare tutto o la prima parte del nome visualizzato e fare clic su **Trova**.

5. Nella tabella fare doppio clic sull'account utente che si desidera rimuovere.

6. Nel riquadro visualizzato fare clic su **Rimuovi utente.** Nel riquadro successivo visualizzato fare clic su **OK.**

> [!NOTE]
> Il nuovo Pannello di controllo non è disponibile per Skype for Business Server 2015.

### <a name="remove-a-user-using-the-legacy-control-panel"></a>Rimuovere un utente tramite il Pannello di controllo legacy

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2. Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello Skype for Business Server controllo.

3. Nel riquadro sinistro selezionare **Utenti**.

4. Nella  casella Cerca utenti digitare tutto o la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account SAM (Security Accounts Manager), dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) dell'account utente che si desidera rimuovere e quindi fare clic su **Trova**.

5. Nella tabella fare clic sull'account utente da rimuovere.

6. Nel menu **Azione** selezionare **Rimuovi da Lync Server**. Verrà visualizzata una finestra di dialogo.

7. Dalla finestra di dialogo selezionare **OK** per rimuovere l'utente.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Rimuovere gli account utente con Windows PowerShell cmdlet

È possibile rimuovere gli account utente utilizzando il cmdlet Disable-CsUser. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell remota per connettersi a Skype for Business Server, vedere Amministrazione remota di PowerShell per [Microsoft Lync.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) Il processo è lo stesso in Skype for Business Server.

Per rimuovere un account utente, usare il cmdlet Disable-CsUser. Ad esempio:

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

Dopo aver eseguito questo comando, non sarà più possibile riabilitare l'account e le relative impostazioni precedenti. Sarà invece necessario usare il cmdlet Enable-CsUser per creare un account completamente nuovo per Davide Garghentini.

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Disable-CsUser.](/powershell/module/skype/disable-csuser)

## <a name="see-also"></a>Vedere anche

[Enable-CsUser](/powershell/module/skype/enable-csuser)

[Disable-CsUser](/powershell/module/skype/disable-csuser)
