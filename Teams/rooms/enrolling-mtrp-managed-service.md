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
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come registrare Microsoft Teams Rooms account nel servizio Microsoft Teams Rooms Premium gestito.
f1keywords: ''
ms.openlocfilehash: 6ac3a9752fcb285c663e05939ae31b2e60a8a1e6
ms.sourcegitcommit: 3ebf9c5d27263b7e92163f1a61844a5367a4744f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2021
ms.locfileid: "58449034"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Registrare un dispositivo nel servizio Microsoft Teams Rooms Premium gestito

Per registrare un dispositivo Microsoft Teams Rooms nel servizio gestito Teams Rooms Premium, è necessario assegnare altri utenti all'amministratore del servizio gestito e quindi completare i passaggi di registrazione usando tale utente.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Assegnare utenti al ruolo di amministratore del servizio gestito

Completare la procedura seguente per assegnare gli utenti al ruolo di amministratore del servizio gestito:

1. Accedere al portale [Teams Rooms Premium con](https://portal.rooms.microsoft.com/) gli stessi privilegi di amministratore usati per accedere al interfaccia di amministrazione di Microsoft 365.
2. Passare a **Ruoli Impostazioni**  >  **Impostazioni** e quindi selezionare  >   Amministratore servizio **gestito.**
3. In **Amministratore servizio gestito** selezionare la scheda **Attività** e quindi selezionare **Aggiungi**.
4. Seguire la procedura guidata per assegnare un nome all'attività e selezionare gli utenti da aggiungere. L'attività verrà applicata a tutte le chat room e i gruppi di chat room.
5. Al termine della procedura guidata per l'assegnazione, selezionare **Aggiungi attività.**

Gli utenti a cui è assegnato il ruolo di amministratore del servizio gestito sono responsabili della gestione quotidiana e del monitoraggio del portale Teams Rooms Premium servizi gestiti.

Dopo aver assegnato gli utenti al ruolo di [](#enroll-a-teams-rooms-device) amministratore del servizio gestito, passare alla sezione Registrare un dispositivo per aggiungere un dispositivo Teams Rooms al portale dei servizi gestiti.

## <a name="enroll-a-teams-rooms-device"></a>Registrare un Teams Rooms dispositivo

Completare la procedura seguente per registrare un dispositivo nel servizio Teams Rooms Premium gestito:

1. Accedere al portale [Teams Rooms Premium con](https://portal.rooms.microsoft.com/) un utente a cui è stato assegnato il ruolo di amministratore del servizio gestito.
2. Selezionare nella scheda **?** nell'angolo in alto a destra del portale per avviare il menu ? Il menu ? include una [guida all'installazione](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) che contiene istruzioni dettagliate per la registrazione:

    1. Esaminare la **sezione Prerequisiti nella** Guida all'installazione. Verificare che gli URL elencati **nell'elenco URL necessari** per la comunicazione siano aggiunti all'elenco di indirizzi consentiti per il traffico del firewall.
    2. Seguire le istruzioni nella sezione **Abilitazione del Impostazioni TPM** per abilitare la funzionalità TPM (Trusted Platform Module) nel dispositivo.
    3. Seguire le istruzioni nella sezione **Aggiunta Impostazioni** proxy per configurare il dispositivo per l'uso del gateway proxy, se presente.
    4. Seguire le istruzioni nella sezione **Processo** per installare il software dell'agente di monitoraggio e configurare la chiave di autoregistrazione nel dispositivo.

3. Dopo aver configurato l'agente di monitoraggio e la chiave XML univoca nel dispositivo, passare **a** Room > room name > **Status** e quindi selezionare **Enroll**.

    > [!NOTE]
    > Il Teams Rooms del dispositivo rimarrà nello stato **Onboarding** finché un amministratore del servizio gestito non registra il dispositivo usando il portale.

## <a name="link-to-installation-guide"></a>Collegamento alla guida all'installazione

Il menu **?** fornisce un collegamento alla [Guida all'installazione,](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) che a sua volta fornisce le informazioni seguenti:

- Istruzioni sugli URL che devono essere consentiti nell'elenco per consentire l'invio della telemetria della chat room al servizio gestito.
- Istruzioni per l'applicazione dell'Microsoft Teams Rooms Premium di monitoraggio e della chiave XML univoca come parte della registrazione di un dispositivo nel servizio gestito.
- Istruzioni per la risoluzione dei problemi.
