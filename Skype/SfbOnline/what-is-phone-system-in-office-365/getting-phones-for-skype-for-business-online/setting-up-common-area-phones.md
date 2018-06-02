---
title: Configurare i telefoni di aree comuni
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
description: Scopri i passaggi di distribuzione per ottenere il firmware corretto, aggiornarlo se necessario, assegnare le licenze e configurare le impostazioni per i telefoni delle aree comuni.
ms.openlocfilehash: 25605e7538792080213eebb898e612be6ce5bfab
ms.sourcegitcommit: bdf9946b7c65ef7985d6b03a1479ea3a5c17a304
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/23/2018
ms.locfileid: "19426802"
---
# <a name="set-up-common-area-phones"></a>Configurare i telefoni di aree comuni
Un telefono di area comune (CAP) è in genere collocato in un'area come un atrio o un'altra area a disposizione di molte persone. Ad esempio, un telefono nella reception, un citofono o un telefono per sala riunioni, i CAP vengono configurati come dispositivi anziché come utenti e si collegano automaticamente ad una rete. Nei seguenti passaggi, ti aiuteremo a configurare un account per Sistema telefonico con piani tariffari in modo da poter distribuire questi tipi di telefoni nella tua azienda.

## <a name="prerequisites-for-common-area-phones"></a>Prerequisiti per i telefoni delle aree comuni

La prima cosa che devi fare è confermare di aver fatto quanto segue:

 - Acquistato la licenza per telefono di area comune e un piano tariffario.
 - Cercato e acquistato telefoni approvati (visualizza l'elenco [Qui](deploying-skype-for-business-online-phones.md)).         
 - Aggiornato il firmware sui tuoi telefoni (vedi firmware supportato [in questo argomento](getting-phones-for-skype-for-business-online.md)).  Puoi controllare il firmware sul tuo telefono in questo modo:       
    - **Telefoni Polycom VVX**: vai a **Impostazioni** > **Stato** > **Piattaforma** > **Applicazione** > **Principale**.
    - **Telefoni Yealink**: vai a**Stato**sulla schermata principale del telefono.
    - **Telefoni AudioCodes**: vai a **Menu** > **Stato Dispositivo** > **Versione Firmware** dalla schermata principale. 
    - **Telefoni Lync Phone Edition (LPE)**: vai a **Menu** > **Informazioni sul sistema** dalla schermata iniziale.

    Gli upgrade del firmware sono gestiti dal servizio Skype for Business Service. Ogni firmware del telefono certificato Skype for Business viene caricato sul server Skype for Business Update e gli aggiornamenti dispositivo sono attivati su tutti i telefoni per impostazione predefinita. 

    A seconda del tempo di inattività sul telefono e degli intervalli di polling, i telefoni scaricano e installano automaticamente l'ultima versione certificata. Puoi disabilitare le impostazioni di aggiornamento del dispositivo utilizzando il cmdlet [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) e impostando il parametro *EnableDeviceUpdate* a `false`.

## <a name="setting-up-a-common-area-phone"></a>Impostazione di un telefono di area comune
Dovrai seguire questi passaggi:

### <a name="step-1---buy-the-licenses"></a>Passaggio 1: acquista le licenze
1. Nel centro di amministrazione di Office 365, vai a **Fatturazione** > **Servizi di acquisto**, e aggiungi **Altri piani**.

    ![CAP-license.png](../../images/cap-license.png)
2. Clicca su **Telefono di area comune** > **Acquista ora** > sulla pagina di **Check-out** clicca su **Acquista ora**.
3. Clicca per espandere **Abbonamenti aggiuntivi** e quindi clicca per acquistare un piano di chiamata. Scegli **Piano di chiamata domestico** o **Piano di chiamata nazionale e internazionale**.

> [!Note]
> Non hai bisogno di una licenza per il sistema telefonico. È inclusa con la licenza per il **Telefono di area comune.**

Per maggiori informazioni sulle licenze, vedi [Licenze aggiuntive per Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Passaggio 2: crea un nuovo account utente per il telefono e assegna le licenze
1. Nel centro di amministrazione di Office 365, vai a **Utenti** > **Utenti attivi** > **Aggiungi un utente**.
2. Inserisci come **Nome utente** "Reception" per il nome e "Principale" per il cognome.
3. Inserisci un **Nome da visualizzare** se non si genera automaticamente uno come "Reception Principale".
4. Inserisci un **Nome utente** come "ReceptionPrincipale" o "IngressoPrincipale".
5. Per i telefoni delle aree comuni, è possibile impostare manualmente una password o avere la stessa password per tutti i telefoni delle aree comuni. Inoltre, potresti deselezionare **Fai in modo che questo utente modifichi la password al primo accesso**.

    > [!Tip]
    > Aspetta! Non cliccare su **Aggiungere**! Ups, se hai cliccato su **Aggiungere** allora fai in questo modo: Centro di amministrazione di Office 365> **Utenti** > **Utenti attivi** e poi trova l'utente. Quindi, nella pagina delle proprietà dell'utente, clicca su **Licenze di prodotto** e poi su **Modificare**. Sulla pagina delle **Licenze di prodotto**, abilita **Telefono di area comune** e scegli un **Piano di chiamata domestico** o un Piano di chiamata domestico e **internazionale**.

6. Se sei ancora lì, assegna le licenze a questo utente. Nella stessa pagina, fai clic per espandere **Licenze di prodotto**. Abilita quanto segue:
    - Telefono di area comune
    - Quindi devi scegliere un **Piano di chiamata domestico** o un Piano di chiamata domestico e **internazionale**.
     
    L'assegnazione delle licenze apparirà così:

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > Per tua informazione, il piano 2 di Skype for Business è incluso con la licenza per il **Telefono di area comune**.

Per maggiori dettagli, vedi [Aggiungere un utente](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Passaggio 3: assegna un numero di telefono all'account utente del telefono di area comune

![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assegna un numero di telefono all'utente utilizzando il **Centro di amministrazione Skype for Business**.

1. Nell'interfaccia di amministrazione di Office 365, passa a **Interfacce di amministrazione** > **Skype for Business**.
2. Nell' **Interfaccia di amministrazione Skype for Business** >  **Voce** > **Numeri di telefono**.
3. Seleziona un numero dall'elenco di numeri di telefono e fai clic su **Assegnare**.
4. Sulla pagina relativa all'**Assegnazione**, nella casella **Utente vocale** immetti il nome dell'utente che viene utilizzato per il telefono, quindi seleziona l'utente nel menù a tendina **Seleziona un utente vocale**. 
5. Mentre sei lì, dovrai aggiungere un indirizzo di emergenza. Una volta effettuata la ricerca, controlla **Seleziona l'indirizzo di emergenza** e scegli quello giusto per te.
6. Clicca su **Salvare** e il tuo utente dovrebbe apparire così:

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Gli utenti verranno visualizzati solo se vi è stata applicata una licenza di **Sistema telefonico**. Se lo hai appena fatto, a volte ci vuole un po' perché l'utente venga visualizzato nell'elenco.

Per ulteriori informazioni, vedi [Ottenere numeri di telefono per i tuoi utenti](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).

Nel cado te lo stessi chiedendo, puoi anche prendere il tuo numero di telefono che hai con un altro operatore e "*portarlo*"o trasferirlo su Office 365. Vedi, [Trasferire numeri di telefono verso Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).

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
    3. Vai al [portale di provisioning](http://aka.ms/skypecap)e accedi come **Amministratore**.
    4. Immetti il nome visualizzato (ad esempio, Reception Principale).

       > [!Note]
       > Se **Cerca solo telefoni di area comune** è spuntato, deseleziona la casella di controllo e cerca di nuovo.

    5. Nella finestra del codice di accoppiamento, inserisci il codice visualizzato sul telefono e clicca su **Fornitura**.

        Dopo questo ultimo passaggio, il telefono dovrebbe accedere automaticamente.

### <a name="related-topics"></a>Argomenti correlati

- Trovi ulteriori informazioni sui telefoni disponibili su [Distribuzione di telefoni Skype for Business online](deploying-skype-for-business-online-phones.md).
- [Ottenere telefoni per Skype for Business online](getting-phones-for-skype-for-business-online.md)


