---
title: Registrare un Teams Rooms dispositivo nel servizio Microsoft Teams Rooms Premium gestito
author: v-smandalika
ms.author: v-smandalika
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come registrare Microsoft Teams Rooms account nel servizio Microsoft Teams Rooms Premium gestito.
f1keywords: ''
ms.openlocfilehash: d00c4f84447e8ba41f0328cca9b907db45e8fdb7
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070415"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Registrare un dispositivo nel servizio Microsoft Teams Rooms Premium gestito

Per registrare un dispositivo Microsoft Teams Rooms nel servizio gestito di Teams Rooms Premium, è necessario assegnare uno o più utenti all'amministratore del servizio gestito e quindi completare i passaggi di registrazione usando tale utente.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Assegnare utenti al ruolo di amministratore del servizio gestito

Completare la procedura seguente per assegnare gli utenti al ruolo di amministratore del servizio gestito:

1. Accedere al portale [Teams Rooms Premium con](https://portal.rooms.microsoft.com/) gli stessi privilegi di amministratore usati per accedere al interfaccia di amministrazione di Microsoft 365.
2. Passare a **Impostazioni** >  **Impostazioni** >  **Roles** e quindi selezionare **Amministratore servizio gestito**.
3. In **Amministratore servizio gestito** selezionare la **scheda Attività** e quindi selezionare **Aggiungi**.
4. Seguire la procedura guidata per assegnare un nome all'attività e selezionare gli utenti da aggiungere. L'attività verrà applicata a tutte le chat room e i gruppi di chat room.
5. Al termine della procedura guidata per l'assegnazione, selezionare **Aggiungi attività**.

Gli utenti a cui è assegnato il ruolo di amministratore del servizio gestito sono responsabili della gestione quotidiana e del monitoraggio del portale Teams Rooms Premium servizi gestiti.

Dopo aver assegnato gli utenti al ruolo di amministratore del servizio gestito, continuare a registrare un dispositivo [Teams Rooms](enroll-a-device.md) per aggiungere un dispositivo di Teams Rooms al portale dei servizi gestiti.

<!-- ## Enroll a Teams Rooms device

 To enroll a device in the Teams Rooms Premium managed service, see [Monitoring device software installation](monitor-software-installation-guide.md).

2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

    1. Review the **Pre-requisites** section in the Installation guide. Confirm that the URLs listed in the **URLs Required for Communication** list are added to your firewall's traffic allow list.
    2. Follow the instructions in the **Enabling TPM Settings** section to enable the Trusted Platform Module (TPM) functionality on your device.
    3. Follow the instructions in the **Adding Proxy Settings** section to configure your device to use your proxy gateway, if you have one.
    4. Follow the instructions in the **Process** section to install the monitoring agent software and configure the self enrollment key on your device.

3. After the monitoring agent and unique XML key are configured on your device, navigate to **Rooms** > room name > **Status**, and then select **Enroll**.

    > [!NOTE]
    > The Teams Rooms device will remain in the **Onboarding** state until a Managed Service Administrator enrolls the device using the portal.

    See [Monitoring device software installation](monitoring-software-installation-guide.md).

<!--## Link to Installation guide

The **Help** menu provides a link to the [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) which in turn provides the following information:

- Instructions on URLs that need to be allow-listed to serve to enable room telemetry to be sent to the managed service.
- Instructions for applying the Microsoft Teams Rooms Premium monitoring agent and unique XML key as part of enrolling a device in the managed service.
- Troubleshooting instructions.-->
