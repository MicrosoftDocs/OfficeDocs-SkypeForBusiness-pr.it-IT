---
title: Configurare la condivisione desktop in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni su come configurare un criterio di riunione per consentire agli utenti di condividere i propri desktop nelle chat o nelle riunioni di Teams.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad66efadda775c11ab653cbe1bc46b2c5a4ab3c3a80edf77265dddabbb71c4a1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347281"
---
# <a name="configure-desktop-sharing-in-microsoft-teams"></a>Configurare la condivisione desktop in Microsoft Teams

La condivisione del desktop consente agli utenti di presentare una schermata o un'app durante una riunione o in una chat. Gli amministratori possono configurare la condivisione dello schermo in Microsoft Teams per consentire agli utenti di condividere l'intero schermo, un'app o un file. È possibile consentire agli utenti di fornire o richiedere il controllo, consentire la condivisione di PowerPoint, aggiungere una lavagna e consentire le note condivise. Inoltre, è possibile configurare se consentire agli utenti esterni o anonimi di richiedere il controllo dello schermo condiviso. I partecipanti esterni nelle riunioni di Teams possono essere classificati come segue:

- Utente anonimo
- Utenti guest
- Utente B2B
- Utente federato

Per configurare la condivisione dello schermo, creare un nuovo criterio riunioni e assegnarlo agli utenti da gestire.

**Nell'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/)**

1. Selezionare **Riunioni** > **Criteri riunione**.

    ![Criteri riunione selezionati](media/configure-desktop-sharing-image1.png)

2. Nella pagina **Criteri riunione** selezionare **Aggiungi**.

    ![Messaggio Criteri riunione](media/addMeeting.png)

3. Assegnare un titolo univoco al criterio e immettere una breve descrizione.

4. In **Condivisione di contenuti**, scegliere una **Modalità di condivisione dello schermo** nell'elenco a discesa:

   - **Schermo intero**: consente agli utenti di condividere l'intero desktop.
   - **Applicazione singola**: consente agli utenti di limitare la condivisione dello schermo a una singola applicazione attiva.
   - **Disabilitata**: disabilita la condivisione dello schermo.

    ![Opzioni della modalità di condivisione](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > Non è necessario abilitare il criterio di chiamata per consentire agli utenti di usare la condivisione dello schermo dalla chat. Tuttavia, l'audio viene disattivato finché non riattiva l'audio. Inoltre, l'utente che condivide lo schermo può fare clic **su Aggiungi audio** per abilitare l'audio. Se il criterio di chiamata è disabilitato, gli utenti non potranno aggiungere audio alla condivisione dello schermo da una sessione di chat.

5. Abilitare o disabilitare le impostazioni seguenti:

    - **Consentire a un partecipante di concedere o richiedere il controllo**: consente ai membri del team di concedere o richiedere il controllo dell'applicazione o del desktop del relatore.
    - **Consentire a un partecipante esterno di concedere o richiedere il controllo:** si tratta di un criterio per utente. Se un'organizzazione ha impostato questa opzione per un utente, non controlla cosa possono fare i partecipanti esterni, indipendentemente dall'impostazione configurata dall'organizzatore della riunione. Questo parametro controlla se i partecipanti esterni possono ricevere o richiedere il controllo dello schermo del relatore, a seconda delle impostazioni configurate dal relatore nei criteri di riunione dell'organizzazione.
    - **Consentire la condivisione di PowerPoint**: consente di creare riunioni nelle quali è possibile caricare e condividere le presentazioni di PowerPoint.
    - **Consentire la lavagna**: consente agli utenti di condividere una lavagna.
    - **Consentire le note condivise**: consente agli utenti di creare note condivise.

6. Fare clic su **Salva**.

## <a name="use-powershell-to-configure-shared-desktop"></a>Usare PowerShell per configurare il desktop condiviso

Inoltre, è possibile usare il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) per controllare la condivisione del desktop. Impostare i seguenti parametri:

- Descrizione
- ScreenSharingMode
- AllowPrivateCalling
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[Altre informazioni sull'utilizzo del cmdlet csTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).