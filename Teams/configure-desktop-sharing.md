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
ms.openlocfilehash: 857c9c4d830cb3264a83a41b555d26ee004751de
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581747"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Configurare la condivisione desktop in Microsoft Teams
============================================

La condivisione del desktop consente agli utenti di presentare una schermata o un'app durante una riunione o in una chat. Gli amministratori possono configurare la condivisione dello schermo in Microsoft Teams per consentire agli utenti di condividere l'intero schermo, un'app o un file. È possibile consentire agli utenti di fornire o richiedere il controllo, consentire la condivisione di PowerPoint, aggiungere una lavagna e consentire le note condivise. Inoltre, è possibile configurare se consentire agli utenti esterni o anonimi di richiedere il controllo dello schermo condiviso.

Per configurare la condivisione dello schermo, creare un nuovo criterio riunioni e assegnarlo agli utenti da gestire.

**Nell'[interfaccia di amministrazione di Microsoft Teams](https://admin.teams.microsoft.com/)**

1. Selezionare **Riunioni** > **Criteri riunione**.

    ![Screenshot che mostra Criteri riunione selezionato](media/configure-desktop-sharing-image1.png)

2. Nella pagina **Criteri riunione**, selezionare **Nuovo criterio**.

    ![Screenshot che mostra il messaggio di Criteri riunione](media/configure-desktop-sharing-image2.png)

3. Assegnare un titolo univoco al criterio e immettere una breve descrizione.

4. In **Condivisione di contenuti**, scegliere una **Modalità di condivisione dello schermo** nell'elenco a discesa:

   - **Schermo intero**: consente agli utenti di condividere l'intero desktop.
   - **Applicazione singola**: consente agli utenti di limitare la condivisione dello schermo a una singola applicazione attiva.
   - **Disabilitata**: disabilita la condivisione dello schermo.

    ![Screenshot che mostra le opzioni di condivisione dello schermo](media/configure-desktop-sharing-image3.png)

5. Abilitare o disabilitare le impostazioni seguenti:

    - **Consentire a un partecipante di concedere o richiedere il controllo**: consente ai membri del team di concedere o richiedere il controllo dell'applicazione o del desktop del relatore.
    - **Consentire a un partecipante esterno di dare o richiedere il controllo** , ovvero un criterio per utente. Indipendentemente dal modo in cui l'organizzatore della riunione ha impostato, l'organizzazione ha impostato questo set per un utente non controlla quali partecipanti esterni possono eseguire. Questo parametro controlla se i partecipanti esterni possono avere il controllo o richiedere il controllo dello schermo del condivisore, a seconda di quello che il condivisore ha impostato nei criteri della riunione dell'organizzazione.
    - **Consentire la condivisione di PowerPoint**: consente di creare riunioni nelle quali è possibile caricare e condividere le presentazioni di PowerPoint.
    - **Consentire la lavagna**: consente agli utenti di condividere una lavagna.
    - **Consentire le note condivise**: consente agli utenti di creare note condivise.

6. Fare clic su **Salva**.

## <a name="use-powershell-to-configure-shared-desktop"></a>Usare PowerShell per configurare il desktop condiviso

Inoltre, è possibile usare il cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) per controllare la condivisione del desktop. Impostare i seguenti parametri:

- Descrizione
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[Altre informazioni sull'utilizzo del cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).

