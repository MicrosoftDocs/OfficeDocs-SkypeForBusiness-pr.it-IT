---
title: Gestire gli account utente per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: Nelle sezioni di questo articolo viene descritto come abilitare, disabilitare temporaneamente o rimuovere gli utenti di Active Directory Skype for Business Server.
ms.openlocfilehash: 43b48daf7a3ad7242076c29a1372e608130763e8e7add95ac86e97ed9c3a9e97
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/11/2021
ms.locfileid: "57850181"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Gestire gli account utente per Skype for Business Server

Nelle sezioni di questo articolo viene descritto come abilitare, disabilitare temporaneamente o rimuovere gli utenti di Active Directory Skype for Business Server.

Per informazioni su come abilitare un utente di Active Directory, vedere [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)). Per informazioni su come eliminare un utente di Active Directory, vedere [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).

Queste procedure devono essere eseguite durante una finestra di manutenzione, quando l Skype for Business'utilizzo è minimo. L'eventuale esecuzione di questa operazione in base a una pianificazione giornaliera o settimanale dipende dalle esigenze dell'organizzazione.

In questo articolo sono contenute le procedure seguenti:

- [Per ricercare uno o più utenti](user-accounts.md#Search)

- [Aggiungere e abilitare un nuovo Skype for Business Server utente](user-accounts.md#Add)

- [Disabilitare o riattivare un account utente precedentemente abilitato per Skype for Business Server](user-accounts.md#Disable)

- [Disabilitare un utente per VoIP aziendale](user-accounts.md#Disable_EV)

- [Rimuovere un account utente con Skype for Business Server Management Shell](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>Per ricercare uno o più utenti
<a name="Search"> </a>

È possibile utilizzare i risultati di una query di ricerca per configurare gli utenti di Active Directory per Skype for Business Server. È possibile ricercare utenti in base al nome visualizzato, al nome, al cognome, al nome dell'account SAM (Security Accounts Manager), all'indirizzo SIP o all'URI (Uniform Resource Identifier) della linea.

È possibile cercare gli utenti utilizzando il Skype for Business Server o lo snap-in Utenti e computer di Active Directory. Nella procedura seguente viene descritto come utilizzare Skype for Business Server pannello di controllo per cercare utenti.

> [!NOTE]
> In un ambiente con una topologia a foresta centrale, i risultati della ricerca potrebbero non essere accurati quando si cerca un utente in base all'indirizzo di posta elettronica dell'utente. È invece possibile cercare utenti specificando un prefisso di indirizzo SIP, ad esempio sip:name, aggiungere un filtro di ricerca e selezionare un indirizzo SIP contenente un indirizzo di posta elettronica parziale oppure utilizzare il cmdlet **Get-CSUser.**

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello Skype for Business Server di controllo.

3. Nella barra di spostamento sinistra fare clic su **Utenti**.

4. Nella casella **Ricerca utenti** digitare interamente o parzialmente il nome visualizzato, il nome, il cognome, il nome account SAM, l'indirizzo SIP o l'URI linea dell'account utente da ricercare e quindi fare clic su **Trova**.

5. (Facoltativo) Specificare ulteriori criteri di ricerca per circoscrivere i risultati:

   a. Fare clic sul pulsante freccia di espansione nell'angolo in alto a destra della schermata al di sopra di **Risultati della ricerca** e quindi fare clic su **Aggiungi filtro**.

   b. Digitare la proprietà utente oppure selezionarla facendo clic sulla freccia nell'elenco a discesa.

   c. Nell'elenco **Uguale a** selezionare **Uguale a** o **Diverso da**.

   d. Nella casella di testo digitare i criteri di ricerca che si desidera utilizzare per filtrare i risultati della ricerca e quindi fare clic su **Trova**.

6. I risultati della ricerca verranno visualizzati al di sotto di **Risultati della ricerca**. È possibile selezionare uno o tutti gli utenti dell'elenco ed eseguire attività di configurazione sugli utenti selezionati.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Aggiungere e abilitare un nuovo Skype for Business Server utente
<a name="Add"> </a>

Dopo aver abilitato un account utente in Utenti e computer di Active Directory, è possibile utilizzare il Pannello di controllo di Skype for Business Server per creare e abilitare nuovi account utente di Skype for Business Server aggiungendo un utente di Active Directory a Skype for Business Server.

È inoltre possibile utilizzare un cmdlet, in particolare [Enable-CsUser.](/powershell/module/skype/enable-csuser)

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello Skype for Business Server di controllo.

3. Nella barra di spostamento sinistra fare clic su **Utenti**.

4. Fare clic su **Abilita utenti**.

5. Nella finestra di dialogo **Nuovo utente di Lync Server** fare clic su **Aggiungi**.

6. Nella casella **Ricerca utenti** digitare il nome intero o parziale, il nome visualizzato, il nome, il cognome, il nome account del sistema degli account di sicurezza (SAM), l'indirizzo di posta elettronica, il nome dell'entità utente o il numero di telefono dell'account utente di Active Directory desiderato e quindi fare clic su **Trova**.

7. Nella tabella selezionare l'account che si desidera aggiungere Skype for Business Server e quindi fare clic su **OK.**

8. Assegnare l'utente a un pool, specificare eventuali dettagli aggiuntivi, assegnare i criteri all'utente desiderato e quindi fare clic su **Abilita**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Disabilitare o riattivare un account utente precedentemente abilitato per Skype for Business Server
<a name="Disable"> </a>

È possibile utilizzare la procedura seguente per disabilitare un account utente abilitato in precedenza in Skype for Business Server senza perdere le impostazioni Skype for Business Server configurate per l'account utente. Poiché non si perdono le impostazioni Skype for Business Server account utente, è possibile riconfigurare un account utente abilitato in precedenza senza dover riconfigurare l'account utente.

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello Skype for Business Server di controllo.

3. Sulla barra di spostamento sinistra fare clic su **Utenti**.

4. Nella casella **Cerca utenti** digitare tutto o solo la prima parte del nome visualizzato, del nome, del cognome, del nome di account SAM (Security Accounts Manager), dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) linea dell'account utente che si desidera disabilitare o abilitare di nuovo e quindi fare clic su **Trova**.

5. Nella tabella fare clic sull'account utente che si desidera disabilitare o abilitare di nuovo.

6. Dal menu **Azione** scegliere uno dei comandi seguenti:

   - Per disabilitare temporaneamente l'account utente per Skype for Business Server, fare clic su **Disabilita temporaneamente per Lync Server.**

   - Per abilitare l'account utente per Skype for Business Server, fare clic su **Ri-abilita per Lync Server.**

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Utilizzare Windows PowerShell per disabilitare o riattivare gli account utente

Gli account utente possono essere temporaneamente disabilitati e quindi ri abilitati in un secondo momento utilizzando il cmdlet **Set-CsUser.** È possibile eseguire questo cmdlet da Skype for Business Server Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server.

### <a name="to-disable-a-user-account"></a>Per disabilitare un account utente

- Per disabilitare temporaneamente un account utente, impostare il valore della proprietà Enabled su False ($False), ad esempio:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>Per abilitare di nuovo un account utente

- Per riabilitare un account utente, impostare il valore della proprietà Enabled su True ($True), ad esempio:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsUser.](/powershell/module/skype/set-csuser)

## <a name="disable-a-user-for-enterprise-voice"></a>Disabilitare un utente per VoIP aziendale
<a name="Disable_EV"> </a>

Utilizzare la procedura seguente per disabilitare VoIP aziendale per un account utente abilitato per Skype for Business Server.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>Per disabilitare un account utente per VoIP aziendale

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello Skype for Business Server di controllo.

3. Sulla barra di spostamento sinistra fare clic su **Utenti**.

4. Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.

5. Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.

6. Scegliere **Mostra dettagli** dal menu **Modifica**.

7. Nella pagina **Modifica utente Lync Server**, in **Telefonia** fare clic su qualsiasi opzione, ad eccezione di **VoIP aziendale**.

    > [!NOTE]
    > Per impedire a un utente di effettuare chiamate audio o video tramite Lync, in **Telefonia** fare clic **su Audio/video disabilitato.**

8. Fare clic su **Commit**.

L'utente non è ora in grado di usare la VoIP aziendale funzionalità. Informazioni correlate: <br/>[VoIP aziendale e mobilità](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [Abilitare gli utenti per VoIP aziendale in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Skype for Business Server Management Shell](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Rimuovere un account utente con Skype for Business Server Management Shell
<a name="Remove"> </a>

È possibile utilizzare la procedura seguente per rimuovere un account utente aggiunto in precedenza in Skype for Business Server.

> [!NOTE]
> La rimozione di un utente comporterà la perdita delle impostazioni configurate per l'account utente. Se invece si desidera disabilitare temporaneamente un account utente, vedere Disabilitare o [riattivare](user-accounts.md#Disable)un account utente abilitato in precedenza per Skype for Business Server .

1. Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2. Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello Skype for Business Server di controllo.

3. Sulla barra di spostamento sinistra fare clic su **Utenti**.

4. Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, nome, cognome, nome dell'account Gestione account di protezione, indirizzo SIP o URI (Uniform Resource Identifier) di linea dell'account utente da disabilitare o riabilitare e quindi fare clic su **Trova**.

5. Nella tabella fare clic sull'account utente da rimuovere.

6. Nel menu **Azione** selezionare **Rimuovi da Lync Server**. Verrà visualizzata una finestra di dialogo.

7. Dalla finestra di dialogo selezionare **OK** per rimuovere l'utente.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Rimuovere gli account utente con Windows PowerShell

È possibile rimuovere gli account utente utilizzando il cmdlet Disable-CsUser. Questo cmdlet può essere eseguito da Skype for Business Server Management Shell o da una sessione Windows PowerShell. Per informazioni dettagliate sull'Windows PowerShell per connettersi a Skype for Business Server, vedere l'articolo del blog ["Guida introduttiva: Gestione di Microsoft Lync Server 2010 tramite Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Il processo è lo stesso in Skype for Business Server.

### <a name="to-remove-a-user-account"></a>Per rimuovere un account utente
Per rimuovere un account utente, usare il cmdlet Disable-CsUser. Ad esempio:

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

Dopo aver eseguito questo comando, non sarà più possibile riabilitare l'account e le relative impostazioni precedenti. Sarà invece necessario usare il cmdlet Enable-CsUser per creare un account completamente nuovo per Davide Garghentini.

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Disable-CsUser.](/powershell/module/skype/disable-csuser)

## <a name="see-also"></a>Vedere anche
<a name="Remove"> </a>

[Enable-CsUser](/powershell/module/skype/enable-csuser)

[Disable-CsUser](/powershell/module/skype/disable-csusers)
