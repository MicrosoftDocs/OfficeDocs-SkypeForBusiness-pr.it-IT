---
title: Configurare le audioconferenze per piccole e medie imprese
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Informazioni su come impostare le audioconferenze nelle piccole e medie imprese per le persone che devono usare un telefono per accedere alle riunioni. '
ms.openlocfilehash: 80e372e62ffdac9907521eb9426b465c9d0b6e92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821286"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Configurare le audioconferenze per piccole e medie imprese

Con le audioconferenze, le persone possono accedere alle riunioni di Teams usando un telefono invece di usare l'app Teams sul proprio dispositivo mobile o dal proprio computer.  

Se sei una piccola o media azienda con un massimo di 300 utenti e attualmente non hai licenze per i servizi di audioconferenza, puoi ottenere audioconferenze gratuite per un anno. Questa offerta gratuita è disponibile a partire dal 1° ottobre 2020.

La licenza per il componente aggiuntivo Audioconferenza può essere applicata agli utenti che hanno licenze per Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1 o Enterprise E3. Per altre informazioni, vedere [Licenze per i componenti aggiuntivi di Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> Se si dispone di Enterprise E5 o Microsoft 365 Business Voice, non sarà possibile usare l'offerta gratuita di audioconferenza perché queste licenze includono già i servizi di audioconferenza.

Questo articolo illustra come configurare le audioconferenze. È necessario soltanto configurare l'audioconferenza solo per gli utenti che intendono programmare o condurre riunioni. I partecipanti alle riunioni che a chiamano le riunioni non hanno bisogno di licenze o altre configurazioni. Per ulteriori informazioni, consulta [Audioconferenza.](audio-conferencing-in-office-365.md)

## <a name="set-up-audio-conferencing"></a>Configurare l’audioconferenza

Quando si configurano le audioconferenze, al bridge di conferenza viene assegnato automaticamente un numero di telefono per poterlo utilizzare negli inviti alle riunioni. Il numero di telefono assegnato come numero predefinito del bridge di conferenza sarà un numero del paese o dell'area geografica dell'organizzazione. Questo numero di telefono è un numero a pagamento, a cui possono essere applicati costi per chiamate interurbane.

> [!NOTE]
> Puoi anche utilizzare un numero verde, che richiede alcuni passaggi aggiuntivi. Per ulteriori informazioni sui numeri di telefono per il bridge di conferenza, consulta i numeri di telefono per i servizi [di audioconferenza](#audio-conferencing-phone-numbers) più avanti in questo articolo.

### <a name="step-1-get-audio-conferencing-licenses"></a>Passaggio 1: Ottenere licenze per i servizi di audioconferenza

Ottenere una licenza per i servizi di audioconferenza per ogni persona che condurrà le riunioni. A questo scopo, usare l'interfaccia di amministrazione di Microsoft 365.

1. Nell'interfaccia di amministrazione di Microsoft 365 passare a Acquisto di fatturazione e quindi, in fondo alla pagina, selezionare  >   **Componenti aggiuntivi.**
2. Seleziona **Microsoft 365 Audioconferenze Adoption Promo**  >  **Details** e quindi **Seleziona Ottieni ora.**
3. Immettere il numero di licenze necessarie per gli organizzatori della riunione, quindi completare l'ordine.

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Screenshot della licenza promozionale Adoption per audioconferenze":::

    > [!NOTE]
    > Deseleziona o seleziona Assegna automaticamente a tutti gli utenti senza **licenza,** a seconda che si voglia assegnare automaticamente una licenza per i servizi di audioconferenza a tutti gli utenti che non dispongono di questa licenza.

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Passaggio 2: Assegnare una licenza per i servizi di audioconferenza agli utenti che conducono le riunioni

Assegnare una licenza a ogni persona che condurrà le riunioni. A questo scopo, usare l'interfaccia di amministrazione di Microsoft 365.

#### <a name="assign-a-license-to-one-user"></a>Assegnare una licenza a un utente

1. Nell'interfaccia di amministrazione di Microsoft 365 passare a **Utenti**  >  **attivi.**  
2. Selezionare la riga dell'utente a cui si vuole assegnare la licenza e quindi, nel riquadro, **selezionare Licenze e app.**
3. Selezionare la **casella di controllo Audioconferenza di Microsoft 365** e quindi **selezionare Salva modifiche.**

#### <a name="assign-a-license-to-multiple-users"></a>Assegnare una licenza a più utenti

1. Nell'interfaccia di amministrazione di Microsoft 365 passare a **Utenti**  >  **attivi.**  
2. Selezionare i cerchi accanto agli utenti a cui si vuole assegnare la licenza e quindi selezionare **Gestisci licenze di prodotto.**
3. Nel riquadro **Gestisci licenze di** prodotto seleziona Assegna **altro.**
4. Selezionare la **casella di controllo Audioconferenza di Microsoft 365** e quindi **selezionare Salva modifiche.**  

## <a name="schedule-teams-meetings-in-outlook"></a>Pianificare riunioni di Teams in Outlook

Gli organizzatori della riunione ora possono pianificare riunioni in Outlook. In Outlook, passare a **Calendario** e quindi selezionare il pulsante **Nuova riunione di Teams.** I numeri di accesso esterno della riunione e l'ID conferenza vengono aggiunti automaticamente all'invito alla riunione inviato ai partecipanti alla riunione. Per altre informazioni, vedere [Pianificare una riunione di Teams in Outlook.](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)

> [!NOTE]
> Se si vuole, è possibile personalizzare gli inviti alle riunioni per aggiungere il logo della società, i collegamenti al sito Web di supporto e alla dichiarazione di non responsabilità legale e un piè di pagina di solo testo. Per altre informazioni, vedere [Personalizzare gli inviti alle riunioni.](meeting-settings-in-teams.md#customize-meeting-invitations)

## <a name="audio-conferencing-phone-numbers"></a>Numeri di telefono per audioconferenze

Sono disponibili due tipi di numeri per il bridge di conferenza. È possibile utilizzare **numeri condivisi** (come nella sezione Configurazione dei servizi di [audioconferenza](#set-up-audio-conferencing) di questo articolo) o **numeri dedicati.** Ecco altre informazioni su ognuno di essi.

### <a name="shared-numbers"></a>Numeri condivisi

Un numero condiviso è un numero condiviso tra tutte le organizzazioni. I numeri condivisi sono numeri a numero verde e vengono assegnati automaticamente quando si configurano le audioconferenze.

Per visualizzare il numero predefinito assegnato al bridge di conferenza, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams vai a Bridge conferenza riunioni, quindi trova il numero della sede più vicina  >  a te.

### <a name="dedicated-numbers"></a>Numeri dedicati

Un numero dedicato è un numero disponibile solo per gli utenti. Un numero dedicato può essere un numero a numero verde o un numero verde. Per utilizzare un numero dedicato, devi prima ottenere il numero, assegnarlo al bridge di conferenza e quindi assegnarlo a ogni persona che condurrà le riunioni.

Ci sono un paio di modi per ottenere un numero dedicato. Puoi ottenere un numero da Microsoft o trasferire (trasferire) un numero esistente dal provider di servizi corrente a Microsoft. Per altre informazioni su come eseguire questa operazione, vedere Recupero [di numeri di servizio.](getting-service-phone-numbers.md)

Tenere presente che se si usa un numero verde, è necessario assegnare prima una licenza di Crediti comunicazioni a ogni persona che condurrà le riunioni. Per ulteriori informazioni, consulta [Configurare i Crediti comunicazioni per la propria organizzazione.](set-up-communications-credits-for-your-organization.md)

Dopo aver assegnato il numero, assegnarlo al bridge di conferenza. Usare l'interfaccia di amministrazione di Microsoft Teams per eseguire questa operazione.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passa **a**  >  **Bridge conferenza riunioni.**
2. Seleziona **Aggiungi,** quindi seleziona **Numero a verde o** Numero **verde.**
3. Nel riquadro **Aggiungi numero di** telefono selezionare il numero e quindi scegliere **Applica.**

Assegnare quindi il numero a ogni persona che condurrà le riunioni. Usare l'interfaccia di amministrazione di Microsoft Teams per eseguire questa operazione.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, selezionare **Utenti,** fare clic sul nome visualizzato dell'utente e selezionare **Modifica.**
2. Seleziona **Modifica** accanto a **Audioconferenza,** quindi nel riquadro  **Audioconferenza** seleziona  un numero negli elenchi di numeri a numero verde o a numero verde e quindi seleziona **Applica.**

## <a name="related-topics"></a>Argomenti correlati

- [Audioconferenza](audio-conferencing-in-office-365.md)
- [Configurare le audioconferenze per Teams](set-up-audio-conferencing-in-teams.md)
- [Numeri di telefono per i servizi di audioconferenza](phone-numbers-for-audio-conferencing-in-teams.md)
- [Domande ricorrenti sulle audioconferenze](audio-conferencing-common-questions.md)
- [Recupero di numeri di servizio](getting-service-phone-numbers.md)
- [Licenze per i componenti aggiuntivi di Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
