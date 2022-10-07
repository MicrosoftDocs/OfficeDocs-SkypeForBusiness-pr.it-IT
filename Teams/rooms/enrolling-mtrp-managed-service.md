---
title: Accesso al portale Pro Management
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come accedere al portale di gestione di Microsoft Teams Rooms Pro.
f1keywords: ''
ms.openlocfilehash: 64d2613b586a5c87f42b6a376a6c3a0d9ad3a799
ms.sourcegitcommit: 43db97b84ca70b1e6accfa7214d4106e4177a642
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2022
ms.locfileid: "68218080"
---
# <a name="accessing-the-pro-management-portal"></a>Accesso al portale Pro Management

Per accedere al portale di gestione di Teams Rooms Pro, è necessario assegnare uno o più utenti all'amministratore del servizio gestito e quindi completare i passaggi di registrazione usando tale utente.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Assegnare utenti al ruolo di amministratore del servizio gestito

Completare la procedura seguente per assegnare agli utenti il ruolo di amministratore del servizio gestito:

1. Accedere al [portale di gestione di Teams Rooms Pro](https://portal.rooms.microsoft.com/) con gli stessi privilegi di amministratore usati per accedere al interfaccia di amministrazione di Microsoft 365.
2. Passare a **Ruoli** **impostazioni impostazioni** >  >  e quindi selezionare **Amministratore del servizio gestito**.
3. In **Amministratore del servizio gestito** seleziona la scheda **Assegnazioni** e quindi **aggiungi**.
4. Seguire la procedura guidata per assegnare un nome all'attività e selezionare gli utenti da aggiungere. L'assegnazione verrà applicata a tutti i gruppi di sale e gruppi di sale.
5. Al termine dell'assegnazione guidata, selezionare **Aggiungi attività**.

Gli utenti a cui è assegnato il ruolo di amministratore del servizio gestito sono responsabili della gestione quotidiana e del monitoraggio di Teams Rooms.

Dopo aver assegnato agli utenti il ruolo Amministratore del servizio gestito, passare a [Registra un dispositivo Teams Rooms](enroll-a-device.md) per aggiungere un dispositivo Teams Rooms al portale del servizio gestito.

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
