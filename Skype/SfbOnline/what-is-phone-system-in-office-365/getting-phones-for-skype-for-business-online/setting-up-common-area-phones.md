---
title: Impostare i telefoni delle aree comuni
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Informazioni sulle procedure di distribuzione per ottenere il firmware corretto, aggiornare, se necessario, assegnare licenze e configurare le impostazioni per i telefoni delle aree comuni.
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2018
---
# <a name="set-up-common-area-phones"></a>Impostare i telefoni delle aree comuni
Un telefono di area comune (CAP) solito si trova in un'area come una sala di attesa o un'altra area disponibili per molti utenti. Ad esempio, un telefono di area di ricezione, porta telefono o sale riunioni telefono, estremità sono impostati come dispositivi piuttosto che gli utenti e Accedi automaticamente in una rete. Nella procedura riportata di seguito, si verrà consentono di configurare un account per il sistema telefonico con la chiamata dei piani in modo che è possibile distribuire i tipi di telefoni per l'organizzazione.

## <a name="prerequisites-for-common-area-phones"></a>Prerequisiti per i telefoni delle aree comuni

Come prima cosa che è necessario eseguire consiste nel verificare di disporre di quanto segue:

 - Acquistare licenze di telefono di Area comune e un piano di chiamata.
 - Cercare e acquistare telefoni approvati (consente di visualizzare l'elenco [di seguito](deploying-skype-for-business-online-phones.md)).         
 - Aggiornare il firmware per i telefoni (vedere supportati del firmware [in questo argomento](getting-phones-for-skype-for-business-online.md).  In questo modo è possibile controllare il firmware del telefono:       
    - **I telefoni Polycom VVX**: passare a **Impostazioni** > **stato** > **piattaforma** > **applicazione** > **principale**.
    - **Telefoni Yealink**: passare allo **stato** sullo schermo del telefono principale.
    - **Telefoni AudioCodes**: passare al **Menu** > **Stato dispositivo** > **versione del Firmware** nella schermata start. 
    - **Telefoni Lync Phone Edition (LPE)**: passare al **Menu** > **System Information** nella schermata start.

    Gli upgrade del firmware sono gestiti dal servizio Skype for Business Service. Ogni firmware del telefono certificato Skype for Business viene caricato sul server Skype for Business Update e gli aggiornamenti dispositivo sono attivati su tutti i telefoni per impostazione predefinita. 

    A seconda del tempo di inattività sul telefono e degli intervalli di polling, i telefoni scaricano e installano automaticamente l'ultima build certificata. È possibile disabilitare le impostazioni di aggiornamento dispositivo utilizzando il cmdlet [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) e l'impostazione del parametro *EnableDeviceUpdate* `false`.

## <a name="setting-up-a-common-area-phone"></a>Impostazione di un telefono di Area comune
È necessario eseguire la procedura seguente:

### <a name="set-up-your-user-account-for-the-phone"></a>Configurazione dell'account utente per il telefono

#### <a name="step-1---buy-the-licenses"></a>Passaggio 1 - acquistare le licenze
1. Nell'interfaccia di amministrazione di Office 365, passare alla **fatturazione** > **servizi di acquisto**e aggiungere **altri piani**.

    ![CAP license.png](../../images/cap-license.png)
2. Fare clic sul **Telefono di Area comune** > **Acquista** > al clic pagina **estrazione** su **Acquista**.
3. Fare clic su per espandere **le sottoscrizioni di componente aggiuntivo** e fare clic su acquistare un piano di chiamata. Scegliere il metodo **nazionale Plan la chiamata** o **chiamate nazionali e internazionali pianificare**.

> [!Note]
> Non è necessario una licenza di sistema telefonico. Ha incluso con licenza di **Telefono di Area comune** .

Per ulteriori informazioni sulle licenze, vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Passaggio 2: creare un nuovo account utente per il telefono e assegnare le licenze
1. Nell'interfaccia di amministrazione di Office 365 accedere agli **utenti** > **Utenti attivi** > **Add user**.
2. Inserire un **nome utente** , ad esempio "Main" per il nome e "Ricezione" per il secondo nome.
3. Inserire un **nome visualizzato** in caso contrario genera automaticamente una like "Main ricezione".
4. Inserire un **nome utente** come "MainReception" o "Mainlobby".
5. Per i telefoni delle aree comuni, è possibile impostare manualmente una password o avere la stessa password per tutti i telefoni delle aree comuni è. Inoltre, si pensi su deselezionando la casella **che l'utente di modificare la password quando accedono prima**.

    > [!Tip]
    > ATTENDERE. Non fare clic su **Aggiungi**. Ugh, se è fare clic su **Aggiungi** eseguire questo: interfaccia di amministrazione di Office 365 > **utenti** > **utenti attivi** e individuare l'utente. Nella pagina proprietà dell'utente, fare clic su **licenze per i prodotti** e quindi fare clic su **Modifica**. Nella pagina **licenze per i prodotti** , attivare il **Telefono di Area comune** e selezionare sia una **Chiamata a pianificare le** o nazionali e **Internazionali la chiamata a pianificare**.

6. Se si è ancora presente, assegnare le licenze per l'utente. Nella stessa pagina, fare clic per espandere **le licenze**. Attivare le operazioni seguenti:
    - Telefono di Area comune
    - È necessario selezionare sia una **Chiamata a pianificare le** o nazionali e **Internazionali la chiamata a pianificare**.
     
    Assegnazione di licenze sarà simile:

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > Solo in modo che si è certi, Skype per Business piano 2 è incluso con licenza di **Telefono di Area comune** .

Per ulteriori informazioni, vedere [aggiungere un utente](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

#### <a name="step-3---assign-a-phone-number-to-the-user"></a>Passaggio 3: assegnare un numero di telefono all'utente
![30x30.png di logo sfb](../../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**
1. Nell'interfaccia di amministrazione di Office 365 > **Admin Center** > **Skype per le aziende**.
2. In **Skype per Business admin center** >  **vocale** > **i numeri di telefono**.
3. Selezionare un numero dall'elenco dei numeri di telefono, quindi fare clic su **Assegna**.
4. Nella pagina **assegnazione** nella casella **vocale utente** immettere il nome dell'utente utilizzato per il telefono, quindi selezionare l'utente di **Selezionare un utente voce di** menu a discesa. 
5. Ci sarà necessario aggiungere un indirizzo di emergenza. Una volta che la ricerca, cercare nella casella **Selezionare l'indirizzo di emergenza** per selezionare quella corretta automaticamente.
6. Fare clic su **Salva** e l'utente deve essere simile al seguente:

    ![number.png di utente CAP](../../images/cap-user-number.png)

   > [!Note]
   > Gli utenti verranno visualizzati solo se dispongono di una licenza di **Sistema telefonico** applicata. Se è stato appena questo, quindi talvolta necessario un po' per l'utente possa essere visualizzata nell'elenco.

Per ulteriori informazioni, vedere [Getting i numeri di telefono per gli utenti](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).

Se si desidera sapere per, è possibile eseguire anche il numero di telefono con un altro gestore di telefonia e "*porta*" o trasferiti a Office 365. Vedere, [trasferire i numeri di telefono a Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).

## <a name="step-4---setting-up-your-phone"></a>Passaggio 4: configurazione del telefono

**Impostazione della modalità di un telefono**

Il telefono o si dispone di telefoni devono disporre attivata la modalità di telefono di Area comune. È possibile verificare che per assicurarsi che sono analoghi. 

**Di seguito è riportato un esempio di come impostare un telefono Polycom VVX**

- Abilitare la modalità di telefono di Area comune per VVX Polycom eseguendo la procedura seguente:
    1. Nel browser, connettersi all'interfaccia web in modo che è possibile abilitare mode Capolettera.
    2. Quindi passare **all'impostazione** e nell'opzione **Skype per impostazione Business** , selezionare **Telefono di Area comune**.
    3. Fare clic su **Sì** per salvare le impostazioni.

- Ora che la modalità CAP è attivata, impostare il telefono con display del telefono. La visualizzazione dovrebbe essere visualizzato **CaAP è abilitata**. Quindi eseguire le operazioni seguenti:

    1. Fare clic su **Impostazioni**.
    2. Selezionare **Avanzate**.
    3. Immettere la password.
    4. In **impostazioni di amministrazione**, selezionare **Impostazioni del telefono Area comune**.
    5. Abilitare la **modalità di amministrazione CAP**e **semplice** .
    6. Fare clic su **Salva file Config**.

- In realtà, il telefono è pronto in modo che è possibile accedere nella schermata principale.

    1. Accedere selezionando **Impostazioni** > **funzionalità** > **Skype per le aziende.**
    2. Selezionare **Le credenziali utente**e selezionare **sign-in web (CAP)** per generare un codice.
    3. Accedere al [portale di provisioning](http://aka.ms/skypecap)e accedere come **amministratore**.
    4. Immettere il nome visualizzato (ad esempio, ricezione principale).

       > [!Note]
       > Se viene controllato **cercare solo i telefoni delle aree comuni** , deselezionare la casella di controllo e ripetere la ricerca. "

    5. Nella finestra codice abbinamento, immettere il codice visualizzato sul telefono e fare clic su **per il provisioning**.

        In seguito quest'ultimo passaggio, il telefono deve accedere automaticamente.

### <a name="related-topics"></a>See also

- Ulteriori informazioni sui telefoni disponibili nella [Distribuzione Skype per i telefoni aziendali in linea](deploying-skype-for-business-online-phones.md).
- [Ottenere telefoni per Skype for Business online](getting-phones-for-skype-for-business-online.md)


