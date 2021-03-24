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
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: Informazioni sui passaggi di distribuzione per ottenere il firmware corretto, aggiornarlo se necessario, assegnare licenze e configurare le impostazioni per i telefoni dell'area comune.
ms.openlocfilehash: 16490c10418928f875d4513c509f17e09ac4359d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106432"
---
# <a name="set-up-common-area-phones"></a>Configurare i telefoni di aree comuni
Un telefono di area comune (CAP) è in genere collocato in un'area come un atrio o un'altra area a disposizione di molte persone. Ad esempio, un telefono nella reception, un citofono o un telefono per sala riunioni, i CAP vengono configurati come dispositivi anziché come utenti e si collegano automaticamente ad una rete. Nei seguenti passaggi, ti aiuteremo a configurare un account per Sistema telefonico con piani tariffari in modo da poter distribuire questi tipi di telefoni nella tua azienda.

## <a name="prerequisites-for-common-area-phones"></a>Prerequisiti per i telefoni delle aree comuni

La prima cosa che devi fare è confermare di aver fatto quanto segue:

- Acquistato la licenza per telefono di area comune e un piano tariffario.
- Cercato e acquistato telefoni approvati (visualizza l'elenco [Qui](deploying-skype-for-business-online-phones.md)).
- Aggiornato il firmware sui tuoi telefoni (vedi firmware supportato [in questo argomento](getting-phones-for-skype-for-business-online.md)).  Puoi controllare il firmware sul tuo telefono in questo modo:
  - **Telefoni Polycom VVX**: Passare a **Impostazioni**  >  **Stato**  >  **Piattaforma Applicazione**  >    >  **Principale**.
  - **Telefoni Yealink:** passare a **Stato** nella schermata principale del telefono.
  - **AudioCodes phones**: Passare alla **versione firmware** dello stato del dispositivo menu  >    >   dalla schermata start.
  - **Telefoni Lync Phone Edition (LPE):** passare a **Menu**  >  **System Information** dalla schermata start.

    Gli upgrade del firmware sono gestiti dal servizio Skype for Business Service. Ogni firmware del telefono certificato Skype for Business viene caricato sul server Skype for Business Update e gli aggiornamenti dispositivo sono attivati su tutti i telefoni per impostazione predefinita.

    A seconda del tempo di inattività sul telefono e degli intervalli di polling, i telefoni scaricano e installano automaticamente l'ultima build certificata. È possibile disabilitare le impostazioni di aggiornamento del dispositivo usando il cmdlet  [Set-CsIPPhonePolicy](/powershell/module/skype/set-csipphonepolicy) e impostando il *parametro EnableDeviceUpdate* su `false` .

## <a name="setting-up-a-common-area-phone"></a>Impostazione di un telefono di area comune
Dovrai seguire questi passaggi:

### <a name="step-1---buy-the-licenses"></a>Passaggio 1: acquista le licenze
1. Nell'interfaccia di amministrazione passare a **Servizi**  >  **di acquisto fatturazione** e aggiungere Altri **piani.**

    ![Screenshot della licenza Common Area Phone](../../images/cap-license.png)
2. Clicca su **Telefono di area comune** > **Acquista ora** > sulla pagina di **Check-out** clicca su **Acquista ora**.
3. Clicca per espandere **Abbonamenti aggiuntivi** e quindi clicca per acquistare un piano di chiamata. Scegli **Piano di chiamata domestico** o **Piano di chiamata nazionale e internazionale**.

> [!Note]
> Non hai bisogno di una licenza per il sistema telefonico. È inclusa con la licenza per il **Telefono di area comune.**

Per maggiori informazioni sulle licenze, vedi [Licenze aggiuntive per Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Passaggio 2: crea un nuovo account utente per il telefono e assegna le licenze
1. Nell'interfaccia di amministrazione passare a **Utenti**  >  **utenti attivi Aggiungere** un  >  **utente**.
2. Inserisci come **Nome utente** "Reception" per il nome e "Principale" per il cognome.
3. Inserisci un **Nome da visualizzare** se non si genera automaticamente uno come "Reception Principale".
4. Inserisci un **Nome utente** come "ReceptionPrincipale" o "IngressoPrincipale".
5. Per i telefoni delle aree comuni, è possibile impostare manualmente una password o avere la stessa password per tutti i telefoni delle aree comuni. Inoltre, potresti deselezionare **Fai in modo che questo utente modifichi la password al primo accesso**.
6. Se sei ancora lì, assegna le licenze a questo utente. Nella stessa pagina, fai clic per espandere **Licenze di prodotto**. Abilita quanto segue:
   - Telefono di area comune
   - Quindi devi scegliere un **Piano di chiamata domestico** o un Piano di chiamata domestico e **internazionale**.

     L'assegnazione delle licenze apparirà così:

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > Per tua informazione, il piano 2 di Skype for Business è incluso con la licenza per il **Telefono di area comune**.

Per maggiori dettagli, vedi [Aggiungere un utente](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Passaggio 3: assegna un numero di telefono all'account utente del telefono di area comune

![Icona che mostra il logo di Skype for Business Assegnare un numero di telefono all'utente usando ](../../images/sfb-logo-30x30.png) **l'interfaccia di amministrazione di Skype for Business**

1. Nell'interfaccia di amministrazione > **di amministrazione** Skype  >  **for Business**.
2. Nell' **Interfaccia di amministrazione Skype for Business** >  **Voce** > **Numeri di telefono**.
3. Seleziona un numero dall'elenco di numeri di telefono e fai clic su **Assegnare**.
4. Sulla pagina relativa all'**Assegnazione**, nella casella **Utente vocale** immetti il nome dell'utente che viene utilizzato per il telefono, quindi seleziona l'utente nel menù a tendina **Seleziona un utente vocale**.
5. Mentre sei lì, dovrai aggiungere un indirizzo di emergenza. Una volta effettuata la ricerca, controlla **Seleziona l'indirizzo di emergenza** e scegli quello giusto per te.
6. Clicca su **Salvare** e il tuo utente dovrebbe apparire così:

    ![Screenshot del numero di telefono dell'utente](../../images/cap-user-number.png)

   > [!Note]
   > Gli utenti verranno visualizzati solo se vi è stata applicata una licenza di **Sistema telefonico**. Se lo hai appena fatto, a volte ci vuole un po' perché l'utente venga visualizzato nell'elenco.

Per ulteriori informazioni, vedi [Ottenere numeri di telefono per i tuoi utenti](/microsoftteams/getting-phone-numbers-for-your-users).

Se vuoi, puoi anche prendere il tuo numero di telefono che hai con un altro gestore e "*porta*" o trasferirlo a Microsoft 365 o Office 365. Vedere Trasferire [numeri di telefono in Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams).

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
    4. Su **Impostazioni di amministrazione** seleziona **Impostazioni del telefono di area comune**.
    5. Abilita **CAP** e **Modalità di amministrazione CAP**.
    6. Clicca su **Salva config**.

- Ok, ora il tuo telefono è pronto per poter accedere alla schermata principale.

    1. Accedi selezionando **Impostazioni** > **Caratteristiche** > **Skype for Business.**
    2. Seleziona **Credenziali dell'utente** e **accesso Web (CAP)** per generare un codice.
    3. Vai al [portale di provisioning](https://aka.ms/skypecap)e accedi come **Amministratore**.
    4. Immetti il nome visualizzato (ad esempio, Reception Principale).

       > [!Note]
       > Se **Cerca solo telefoni di area comune** è spuntato, deseleziona la casella di controllo e cerca di nuovo.

    5. Nella finestra del codice di accoppiamento, inserisci il codice visualizzato sul telefono e clicca su **Fornitura**.

        Dopo questo ultimo passaggio, il telefono dovrebbe accedere automaticamente.


> [!NOTE]
> Il sito di provisioning CAP afferma che ripristinerà la password dell'account CAP ad una password casuale. Prendere nota che l'account a cui fa riferimento il CAP è l'account Azure Active Directory (AAD). Se hai creato l'account solo in AAD, la procedura è semplice. Se è stata sincronizzata una versione locale di Active Directory con AAD e si usa un IDP o ADFS di terze parti, il provisioning cap non riuscirà. In questo caso, è necessario usare solo un account di Microsoft 365 o Office 365/Azure Active Directory (ad esempio un account con un dominio **onmicrosoft.com)** per il provisioning di CAP.


### <a name="related-topics"></a>Argomenti correlati

- Trovi ulteriori informazioni sui telefoni disponibili su [Distribuzione di telefoni Skype for Business online](deploying-skype-for-business-online-phones.md).
- [Ottenere telefoni per Skype for Business Online](getting-phones-for-skype-for-business-online.md)
