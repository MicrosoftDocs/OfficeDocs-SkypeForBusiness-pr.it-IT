---
title: Provisioning remoto e accesso per dispositivi Teams Android
author: cazawideh
ms.author: czawideh
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Scopri come eseguire il provisioning remoto e l'accesso per i dispositivi Teams Android
ms.openlocfilehash: 4b3831bc42da92939c7aa61ff52a15266dc4a940
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674338"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Provisioning remoto e accesso per dispositivi Teams Android

Gli amministratori IT possono eseguire il provisioning e l'accesso remoto a un dispositivo Teams Android. Per eseguire il provisioning remoto di un dispositivo, l'amministratore deve caricare gli ID MAC dei dispositivi di cui viene eseguito il provisioning e creare un codice di verifica. L'intero processo può essere completato in remoto dall'interfaccia di amministrazione Teams.

## <a name="review-the-supported-devices"></a>Controlla i dispositivi supportati

L'elenco seguente mostra i requisiti del firmware del dispositivo Android.

|Categoria dispositivo|Modello di dispositivo|Versione firmware|
|---|---|---|
|Teams telefoni|Yealink T55/T56/T58|58.15.0.124|
|Teams telefoni|Yealink VP59|91.15.0.58|
|Teams telefoni|Yealink CP960|73.15.0.117|
|Teams telefoni|Yealink MP56/MP54/MP58|122.15.0.36|
|Teams telefoni|Crestron UC-2|1.0.3.52|
|Teams telefoni|Poly Trio C60|7.0.2.1071|
|Teams telefoni|CCX400/CCX500/CCX600 |7.0.2.1072|
|Teams telefoni|Codici audio C448HD/C450HD/C470HD|1.10.120|
|Teams pannelli|Crestron 770/1070|1.004.0115|
|Teams Rooms Android|Logitech Rally Bar Mini|1.2.982|
|Teams Rooms Android|Logitech Rally Bar|1.2.982|
|Teams Rooms Android|AudioCodes RXV80|1.13.361|
|Teams Rooms Android|EPOS ESPANDI Vision 3T|1.2.2.21182.10|
|Teams Rooms Android|Yealink MeetingBar A30|133.15.0.60|
|Teams Rooms Android|Yealink MeetingBar A20|133.15.0.60|
|Teams Rooms Android|Console touch Yealink CTP18|137.15.0.37|
|Teams Rooms Android|Poly Studio X30|3.5.0.344025|
|Teams Rooms Android|Poly Studio X50|3.5.0.344025|
|Teams Rooms Android|Console touch Poly TC8 |3.5.0.210489|
|Teams Rooms Android|Yealink VC210|118.15.0.54|

## <a name="add-a-device-mac-address"></a>Aggiungere un indirizzo MAC del dispositivo

Completa i passaggi seguenti per eseguire il provisioning di un nuovo dispositivo.

1. Passare all'interfaccia di amministrazione di Teams.
2. Espandi **Teams Dispositivi**.
3. Seleziona **Provisioning di un nuovo dispositivo** nella scheda **Azioni** .

Nella finestra **Provisioning di nuovi dispositivi** è possibile aggiungere manualmente l'indirizzo MAC o caricare un file.

### <a name="manually-add-a-device-mac-address"></a>Aggiungere manualmente un indirizzo MAC del dispositivo

1. Nella scheda **In attesa di attivazione** seleziona **Aggiungi ID MAC**.

   ![aggiungere manualmente un indirizzo mac del dispositivo.](../media/remote-provision-6-new.png)

1. Immettere l'ID MAC.
1. Immetti una posizione, che consente ai tecnici di identificare dove installare i dispositivi.
1. Al termine, selezionare **Applica** .

### <a name="upload-a-file-to-add-a-device-mac-address"></a>Upload un file per aggiungere un indirizzo MAC del dispositivo

1. Nella scheda **In attesa di attivazione** seleziona **Upload ID MAC**.
2. Scaricare il modello di file.
3. Immettere l'ID MAC e il percorso, quindi salvare il file.
4. **Selezionare file** e quindi **selezionare Upload**.

## <a name="generate-a-verification-code"></a>Generare un codice di verifica

È necessario un codice di verifica per i dispositivi. Il codice di verifica viene generato in blocco o a livello di dispositivo ed è valido per 24 ore.

1. Nella scheda **In attesa di attivazione** seleziona un ID MAC esistente.
   Viene creata una password per l'indirizzo MAC e viene visualizzata nella colonna **Codice di verifica** .

2. Fornisci l'elenco degli ID MAC e i codici di verifica ai tecnici sul campo. È possibile esportare i dettagli direttamente in un file e condividere il file con il tecnico che sta eseguendo il lavoro di installazione effettivo.

## <a name="provision-the-device"></a>Eseguire il provisioning del dispositivo

Quando il dispositivo è acceso e connesso alla rete, il tecnico lo esegue. Questi passaggi vengono completati nel dispositivo Teams.

1. Il tecnico seleziona **Provisioning dispositivo** dal **Impostazioni**.  

   ![Opzione Provisioning di un nuovo dispositivo dalla scheda Azioni.](../media/provision-device1.png)
  
2. Il tecnico immette il codice di verifica specifico del dispositivo nel campo di input fornito.

   ![Esegui il provisioning della nuova verifica del dispositivo.](../media/provision-device-verification1.png)

   Una volta completato il provisioning del dispositivo, il nome del tenant viene visualizzato nella pagina di accesso.

   ![Nome tenant nella pagina di accesso.](../media/provision-code.png)

## <a name="first-time-remote-sign-in"></a>Primo accesso remoto

Il dispositivo di cui è stato eseguito il provisioning viene visualizzato nella scheda **In attesa dell'accesso** . Avvia la procedura di accesso remoto selezionando il singolo dispositivo.

1. Seleziona un dispositivo dalla scheda **In attesa dell'accesso** .

   ![La finestra con un elenco di dispositivi pronti per l'accesso.](../media/remote-device1.png)

2. Segui le istruzioni **in Accedi a un utente** e quindi seleziona **Chiudi**.

   ![nella finestra Accedi a un utente per un singolo dispositivo.](../media/sign-in-user.png)

## <a name="related-articles"></a>Articoli correlati

- [Gestire i dispositivi in Teams](device-management.md)
- [Accesso remoto e disconnessione](remote-sign-in-and-sign-out.md)
- [Aggiornare Teams dispositivi in remoto](remote-update.md)
