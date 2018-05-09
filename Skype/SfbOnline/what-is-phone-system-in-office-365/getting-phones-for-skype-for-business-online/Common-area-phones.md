---
title: Distribuzione dei telefoni per Skype for Business Online
description: Informazioni sulle procedure di distribuzione per ottenere il firmware corretto, aggiornare, se necessario, assegnare licenze e configurare le impostazioni per i telefoni delle aree comuni.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
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
- Strat_SB_PSTN
ms.openlocfilehash: 453f9db6a022e924406594c567ea564b10f58694
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/09/2018
---
## <a name="common-area-phones"></a>Telefoni delle aree comuni
Un telefono di area comune o maiuscola, è in genere in un'area condivisa e non associato a un singolo utente. Ad esempio, un telefono di area di ricezione, porta telefono o sale riunioni telefono, estremità sono impostati come dispositivi piuttosto che gli utenti ed eseguito automaticamente l'accesso alla rete. Nella procedura seguente è sarà consentono di configurare un account per il sistema telefonico Microsoft con la chiamata dei piani e quindi distribuire un Capolettera.

## <a name="prerequisites-for-common-area-phones"></a>Prerequisiti per i telefoni delle aree comuni

Verificare di disporre di quanto segue:

    - Acquistato Common Area Phone SKU 
    - Firmware aggiornato (vedere supportati Firmware nell'argomentohttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)
    - Telefoni approvati (consente di visualizzare l'elenco nellahttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones) 


## <a name="check-the-firmware-for-your-phone"></a>Verificare il firmware per il telefono
- **Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.
- i **telefoni Yealink**, accedi a **Status** (Stato) sulla schermata principale del telefono.
- **AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen. 
- I **telefoni Lync Phone Edition (LPE)**, accedi a **Menu** > **System Information** (Informazioni sul sistema) dalla schermata iniziale.

Gli upgrade del firmware sono gestiti dal servizio Skype for Business Service. Ogni firmware del telefono certificato Skype for Business viene caricato sul server Skype for Business Update e gli aggiornamenti dispositivo sono attivati su tutti i telefoni per impostazione predefinita. 

A seconda del tempo di inattività sul telefono e degli intervalli di polling, i telefoni scaricano e installano automaticamente l'ultima build certificata. È possibile disabilitare le impostazioni di aggiornamento dispositivo utilizzando il cmdlet [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) e l'impostazione del parametro _EnableDeviceUpdate_ `false`.

## <a name="create-cap"></a>Creare remoto
Per creare la Terminazione, configurare le impostazioni prima di impostare l'apparecchio telefonico.

#### <a name="purchase-the-common-area-phone-sku"></a>Il telefono Area comune SKU di acquisto. 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a>Impostare il telefono area comune<!-- this section could use a screen shot-->

**Creare utente** 
1. Assegnare Common Area Phone SKU
2. Assegnare la chiamata a pianificare (se si utilizza Microsoft Phone System con la chiamata dei piani). 
3. Assegna un numero di telefono disponibili in Skype per Business Admin Center o richiedere un nuovo numero di telefono.

**Crea nuovo utente**

1. Nel riquadro di provisioning si ha la possibilità di immettere un nome e cognome (ad esempio, ricezione principale).
2. Immettere un nome visualizzato (obbligatorio), ad esempio, "ricezione Main".
3. Immettere un nome utente (obbligatorio), ad esempio "MainReception" @"domain" (nome della società o dell'organizzazione)
4. Immettere il percorso (paese).

**Assegnare Common Area Phone SKU** Nell'interfaccia di amministrazione di Office 365 andare a **fatturazione > servizi di acquisto** e aggiungere **Telefono di Area comune**

**Assegnare Plan chiamate nelle SKU CAP**

1. Selezionare una chiamata prevede di abilitare il telefono. 
2. Aggiungere la Terminazione per abilitare il sistema telefonico e Skype per Business Online piano 2 in SKU Capolettera. <!-- odd order for step -->

**Assegnare un numero di telefono**
1. Controllare i numeri di telefono disponibili in **vocali > numeri di telefono**.
2. Selezionare un numero dall'elenco disponibile i numeri del numero di telefono.
3. Conferma selezioni selezionando **vocali** e **I numeri di telefono**.

    >[Nota] Gli utenti vocali vengono visualizzate solo se dispongono della licenza di sistema telefonico applicata, anche se anche dopo aver applicato, potrebbe richiedere tempo per l'aggiornamento. Talvolta riapertura Skype per Business Admin center consente.
    
## <a name="configure-phone"></a>Configurare telefono

**Preparare i telefoni fisici** 

Il telefono selezionato deve avere la modalità di telefono di Area comune. 

***Telefono Polycom VVX di esempio***

Attivare la modalità di telefono Area comune in Polycom VVX eseguendo la procedura seguente:
1. Nel browser, utilizzare l'interfaccia web per attivare la modalità di limitare il VVX
2. Passare **all'impostazione** e Skype per l'opzione Impostazioni Business, selezionare **Telefono di Area comune**.
3. Fare clic su **Salva** per salvare le impostazioni di configurazione.

Ora che la modalità telefonica CAP è attivata, impostare il telefono con display del telefono.

1. In impostazioni, selezionare **Avanzate**.
2. Immettere la password.
3. Nella sezione Impostazioni di amministrazione, selezionare **Impostazioni del telefono Area comune**.
4. Abilitare Common Area Phone and Admin CAP
5. Selezionare **Salva file Config**.

Il telefono è pronto per essere eseguito il provisioning, che verranno eseguite quando si accede nella schermata principale.

1. Eseguire l'accesso tramite la selezione di **Impostazioni > funzionalità > Skype per le aziende.**
2. Selezionare le credenziali dell'utente, quindi selezionare selezionare **sign-in web (CAP)** per generare un codice di..
3. Accedere al portale di provisioning http://aka.ms/skypecaped eseguire l'accesso come **amministratore**.
4. Immettere il nome visualizzato (ad esempio Main ricezione) per visualizzare il Capolettera.

>[Nota] Se "Cercare solo i telefoni delle aree comuni" è selezionata, deselezionare la casella di controllo e ripetere la ricerca.

5. Nella finestra codice abbinamento, immettere il codice visualizzato sul telefono e fare clic su **per il provisioning**.

WHT quest'ultimo passaggio, il telefono deve accedere automaticamente.

Ulteriori informazioni sui telefoni disponibili in [ ](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).


