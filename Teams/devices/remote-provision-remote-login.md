---
title: Provisioning remoto e accesso per i dispositivi Android di Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
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
localization_priority: Normal
search.appverid: MET150
description: Scopri come eseguire il provisioning remoto e accedere per i dispositivi Android di Teams
ms.openlocfilehash: f39b93a048cee84cf6890d063e272edbef5edb4e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059190"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Provisioning remoto e accesso per i dispositivi Android di Teams

Gli amministratori IT possono eseguire il provisioning in remoto e accedere a un dispositivo Android di Teams. Per eseguire il provisioning di un dispositivo in remoto, l'amministratore deve caricare gli ID MAC dei dispositivi di cui viene eseguito il provisioning e creare un codice di verifica. L'intero processo può essere completato in remoto dall'interfaccia di amministrazione di Teams.

## <a name="review-the-supported-devices"></a>Esaminare i dispositivi supportati

L'elenco seguente mostra i requisiti del firmware del dispositivo Android.

|Categoria dispositivo|Modello di dispositivo|Versione firmware|
|-|-|-|
|Telefoni di Teams|Yealink T55/T56/T58|58.15.0.124|
|Telefoni di Teams|Yealink VP59|91.15.0.58|
|Telefoni di Teams|Yealink CP960|73.15.0.117|
|Telefoni di Teams|Yealink MP56/MP54/MP58|122.15.0.36|
|Telefoni di Teams|Crestron UC-2|1.0.3.52|
|Telefoni di Teams|  Poly Trio C60|  7.0.2.1071|
|Telefoni di Teams|  CCX400/CCX500/CCX600    |7.0.2.1072|
|Telefoni di Teams|  Codici audio C448HD/C450HD/C470HD|   1.10.120|

## <a name="add-a-device-mac-address"></a>Aggiungere un indirizzo MAC del dispositivo

Completare la procedura seguente per eseguire il provisioning di un nuovo dispositivo.

1. Passare all'interfaccia di amministrazione di Teams.
2. Espandere **Dispositivi**.
3. Selezionare **Provisioning nuovo dispositivo** nella **scheda** Azioni.

Nella finestra **Provisioning nuovi dispositivi** è possibile aggiungere manualmente l'indirizzo MAC o caricare un file.

### <a name="manually-add-a-device-mac-address"></a>Aggiungere manualmente un indirizzo MAC del dispositivo

1. Nella scheda **In attesa di attivazione** selezionare Aggiungi ID **MAC.**

   ![aggiungere manualmente un indirizzo Mac del dispositivo](../media/remote-provision-6.png)

1. Immettere l'ID MAC.
1. Immettere una posizione che consente ai tecnici di identificare la posizione in cui installare i dispositivi.
1. Al **termine, selezionare** Applica.

### <a name="upload-a-file-to-add-a-device-mac-address"></a>Caricare un file per aggiungere un indirizzo MAC del dispositivo

1. Nella scheda **In attesa di attivazione** selezionare Carica ID **MAC.**
2. Scaricare il modello di file.
3. Immettere l'ID MAC e il percorso e quindi salvare il file.
4. **Selezionare file** e quindi **carica**.

## <a name="generate-a-verification-code"></a>Generare un codice di verifica

È necessario un codice di verifica per i dispositivi. Il codice di verifica viene generato in blocco o a livello di dispositivo ed è valido per 24 ore.

1. Nella scheda **In attesa di attivazione** selezionare un ID MAC esistente.
   Viene creata una password per l'indirizzo MAC e visualizzata nella **colonna Codice di** verifica.

2. Fornire l'elenco di ID MAC e codici di verifica ai tecnici del campo. È possibile esportare i dettagli direttamente in un file e condividerlo con il tecnico che sta eseguendo il lavoro di installazione effettivo.

## <a name="provision-the-device"></a>Eseguire il provisioning del dispositivo

Quando il dispositivo è acceso e connesso alla rete, il tecnico esegue il provisioning del dispositivo. Questi passaggi vengono completati nel dispositivo Teams.

1. Il tecnico seleziona **Provisioning dispositivo** in **Impostazioni**.  

   ![Opzione Effettua il provisioning di un nuovo dispositivo dalla scheda Azioni](../media/provision-device1.png)
  
2. Il tecnico immette il codice di verifica specifico del dispositivo nel campo di input fornito.

   ![Eseguire il provisioning della verifica del nuovo dispositivo](../media/provision-device-verification1.png)

   Dopo il provisioning del dispositivo, il nome del tenant viene visualizzato nella pagina di accesso.

   ![Nome tenant nella pagina di accesso](../media/provision-code.png)

## <a name="sign-in-remotely"></a>Accedere in remoto

Il dispositivo di cui è stato eseguito il provisioning viene visualizzato nella **scheda In** attesa di accesso. Avviare il processo di accesso remoto selezionando il singolo dispositivo.

1. Selezionare un dispositivo nella scheda In attesa **di** accesso.

   ![Finestra con un elenco di dispositivi pronti per l'accesso.](../media/remote-device1.png)

2. Seguire le istruzioni in **Accedere a un utente** e quindi selezionare **Chiudi.**

   ![Finestra Accedi a un utente per un singolo dispositivo](../media/sign-in-user.png)

## <a name="related-article"></a>Articolo correlato

- [Gestire i dispositivi in Teams](device-management.md)
- [Aggiornare i dispositivi di Teams in remoto](remote-update.md)
