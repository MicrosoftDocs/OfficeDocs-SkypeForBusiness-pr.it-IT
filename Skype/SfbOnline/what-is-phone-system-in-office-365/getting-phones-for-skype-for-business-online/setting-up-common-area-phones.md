---
title: Configurare i telefoni di aree comuni
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Informazioni sui passaggi di distribuzione per ottenere il firmware corretto, aggiornarlo se necessario, assegnare licenze e configurare le impostazioni per i telefoni delle aree comuni.
ms.openlocfilehash: 9f84b8ebbdd9bfab6b146d3f748715a5e0602047
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792456"
---
# <a name="set-up-common-area-phones"></a>Configurare i telefoni di aree comuni
A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.

## <a name="prerequisites-for-common-area-phones"></a>Prerequisiti per i telefoni delle aree comuni

La prima cosa che devi fare è confermare di aver fatto quanto segue:

- Acquistato la licenza per telefono di area comune e un piano tariffario.
- Cercato e acquistato telefoni approvati (visualizza l'elenco [Qui](deploying-skype-for-business-online-phones.md)).
- Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:
  - **Polycom VVX Phones**: accedere alla**piattaforma** > di**stato** >  **delle impostazioni** > **Main****Application** > .
  - **Yealink Phones**: passa a **stato** nella schermata principale del telefono.
  - **AudioCodes Phones**: accedere alla**versione del firmware** **dello stato** > del dispositivo di **menu** > dalla schermata Start.
  - **Telefoni di Lync Phone Edition (LPE)**: accedere alle**informazioni di sistema** del **menu** > dalla schermata Start.

    Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.

    Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.

## <a name="setting-up-a-common-area-phone"></a>Impostazione di un telefono di area comune
Dovrai seguire questi passaggi:

### <a name="step-1---buy-the-licenses"></a>Passaggio 1: acquista le licenze
1. Nell'interfaccia di amministrazione accedere a**servizi di acquisto** **fatturazione** > e aggiungere **altri piani**.

    ![CAP-license.png](../../images/cap-license.png)
2. Clicca su **Telefono di area comune** > **Acquista ora** > sulla pagina di **Check-out** clicca su **Acquista ora**.
3. Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.

> [!Note]
> You don't need a Phone System license. It's included with the **Common Area Phone** license.

Per maggiori informazioni sulle licenze, vedi [Licenze aggiuntive per Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Passaggio 2: crea un nuovo account utente per il telefono e assegna le licenze
1. Nell'interfaccia di amministrazione, passa a **** > utenti**attivi** > gli utenti che**aggiungono un utente**.
2. Inserisci come **Nome utente** "Reception" per il nome e "Principale" per il cognome.
3. Inserisci un **Nome da visualizzare** se non si genera automaticamente uno come "Reception Principale".
4. Inserisci un **Nome utente** come "ReceptionPrincipale" o "IngressoPrincipale".
5. For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.
6. Se sei ancora lì, assegna le licenze a questo utente. Nella stessa pagina, fai clic per espandere **Licenze di prodotto**. Abilita quanto segue:
   - Telefono di area comune
   - Quindi devi scegliere un **Piano di chiamata domestico** o un Piano di chiamata domestico e **internazionale**.

     L'assegnazione delle licenze apparirà così:

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > Per tua informazione, il piano 2 di Skype for Business è incluso con la licenza per il **Telefono di area comune**.

Per maggiori dettagli, vedi [Aggiungere un utente](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Passaggio 3: assegna un numero di telefono all'account utente del telefono di area comune

![Icona che mostra il logo](../../images/sfb-logo-30x30.png) di Skype for business assegnare un numero di telefono all'utente usando l'interfaccia di amministrazione di **Skype for business**

1. Nell'interfaccia di amministrazione > interfaccia di **Amministrazione** > di**Skype for business**.
2. Nell' **Interfaccia di amministrazione Skype for Business** >  **Voce** > **Numeri di telefono**.
3. Seleziona un numero dall'elenco di numeri di telefono e fai clic su **Assegnare**.
4. Sulla pagina relativa all'**Assegnazione**, nella casella **Utente vocale** immetti il nome dell'utente che viene utilizzato per il telefono, quindi seleziona l'utente nel menù a tendina **Seleziona un utente vocale**.
5. Mentre sei lì, dovrai aggiungere un indirizzo di emergenza. Una volta effettuata la ricerca, controlla **Seleziona l'indirizzo di emergenza** e scegli quello giusto per te.
6. Clicca su **Salvare** e il tuo utente dovrebbe apparire così:

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Gli utenti verranno visualizzati solo se vi è stata applicata una licenza di **Sistema telefonico**. Se lo hai appena fatto, a volte ci vuole un po' perché l'utente venga visualizzato nell'elenco.

Per ulteriori informazioni, vedi [Ottenere numeri di telefono per i tuoi utenti](/microsoftteams/getting-phone-numbers-for-your-users).

Nel cado te lo stessi chiedendo, puoi anche prendere il tuo numero di telefono che hai con un altro operatore e "*portarlo*"o trasferirlo su Office 365. Vedere [trasferire i numeri di telefono in Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).

### <a name="step-4---setting-up-your-phone"></a>Passaggio 4: configurazione del telefono

**Impostazione della modalità su un telefono**

Il telefono o i telefoni in dotazione devono avere la modalità **Telefono di area comune** attiva. Si prega di controllare per assicurarsi che sia attiva.

**Ecco un esempio su come configurare un telefono Polycom VVX**

- Abilita la modalità Telefono di area comune per Polycom VVX seguendo questi passaggi:
    1. Nel browser, collegati all'interfaccia web in modo da poter abilitare la modalità CAP.
    2. Quindi vai a **Impostazioni** e nell'opzione **Impostazioni Skype for Business**, seleziona **Telefono di area comune**.
    3. Clicca su **OK** per salvare le impostazioni.

- Ora che la modalità CAP è abilitata, configura il telefono utilizzando il suo schermo. Lo schermo dovrebbe visualizzare **CaAP è abilitato**. Procedi nel seguente modo:

    1. Clicca su **Impostazioni**.
    2. Seleziona **Avanzate**.
    3. Inserisci la password.
    4. Su **Impostazioni di amministrazione**seleziona **Impostazioni del telefono di area comune**.
    5. Abilita **CAP** e **Modalità di amministrazione CAP**.
    6. Clicca su **Salva config**.

- Ok, ora il tuo telefono è pronto per poter accedere alla schermata principale.

    1. Accedi selezionando **Impostazioni** > **Caratteristiche** > **Skype for Business.**
    2. Seleziona **Credenziali dell'utente**e **accesso Web (CAP)** per generare un codice.
    3. Vai al [portale di provisioning](https://aka.ms/skypecap)e accedi come **Amministratore**.
    4. Immetti il nome visualizzato (ad esempio, Reception Principale).

       > [!Note]
       > Se **Cerca solo telefoni di area comune** è spuntato, deseleziona la casella di controllo e cerca di nuovo.

    5. Nella finestra del codice di accoppiamento, inserisci il codice visualizzato sul telefono e clicca su **Fornitura**.

        Dopo questo ultimo passaggio, il telefono dovrebbe accedere automaticamente.


> [!NOTE]
> Il sito di provisioning CAP afferma che ripristinerà la password dell'account CAP ad una password casuale. Prendere nota che l'account a cui fa riferimento il CAP è l'account Azure Active Directory (AAD). Se hai creato l'account solo in AAD, la procedura è semplice. Se è stata eseguita la sincronizzazione di un sito Active Directory locale con AAD e si usa un IDP o ADFS di terze parti, il provisioning del CAP non riesce. In questo caso, è necessario usare solo un account di Office 365/Azure Active Directory (ad esempio, un account con dominio **onmicrosoft.com** ) per il provisioning del Cap per il lavoro.


### <a name="related-topics"></a>Argomenti correlati

- Trovi ulteriori informazioni sui telefoni disponibili su [Distribuzione di telefoni Skype for Business online](deploying-skype-for-business-online-phones.md).
- [Ottenere telefoni per Skype for Business Online](getting-phones-for-skype-for-business-online.md)


