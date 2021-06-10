---
title: Configurare audioconferenze per piccole e medie imprese
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
description: 'Informazioni su come impostare i servizi di audioconferenza nelle piccole o medie imprese per le persone che devono usare un telefono per accedere alle riunioni. '
ms.openlocfilehash: e7a3461453255a7a61f6a1095e9cb9697070771c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122350"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Configurare audioconferenze per piccole e medie imprese

Con le audioconferenze, le persone possono accedere alle riunioni Teams tramite telefono invece di usare l'app Teams sul dispositivo mobile o dal computer.  

Se si è una piccola o media azienda con un massimo di 300 utenti e attualmente non si hanno licenze di audioconferenza, è possibile ottenere servizi di audioconferenza gratuiti per un anno. Questa offerta gratuita è disponibile a partire dal 1° ottobre 2020.

La licenza del componente aggiuntivo Audioconferenza può essere applicata agli utenti con licenze Microsoft 365 Business Basic, Business Standard, Business Premium, Enterprise E1 o Enterprise E3. Per altre informazioni, vedere Teams [licenze per i componenti aggiuntivi](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

> [!NOTE]
> Se hai Enterprise E5 o Microsoft 365 Business Voice, non potrai usare l'offerta di audioconferenza gratuita perché queste licenze includono già audioconferenza.

Questo articolo illustra come configurare le audioconferenze. È necessario soltanto configurare l'audioconferenza solo per gli utenti che intendono programmare o condurre riunioni. I partecipanti alla riunione che chiamano alle riunioni non hanno bisogno di licenze o altre impostazioni. Per altre informazioni, vedere [Audioconferenza.](audio-conferencing-in-office-365.md)

## <a name="set-up-audio-conferencing"></a>Configurare l’audioconferenza

Quando si configurano le audioconferenze, al bridge di conferenza viene assegnato automaticamente un numero di telefono in modo che possa essere usato negli inviti alle riunioni. Il numero di telefono assegnato come numero predefinito del bridge di conferenza sarà uno del paese o dell'area geografica dell'organizzazione. Questo numero di telefono è un numero a pagamento, in cui possono essere applicati addebiti a lunga distanza.

> [!NOTE]
> È anche possibile usare un numero verde, che richiede alcuni passaggi aggiuntivi. Per altre informazioni sui numeri di telefono per il bridge di conferenza, vedere Numeri di telefono per i servizi di [audioconferenza](#audio-conferencing-phone-numbers) più avanti in questo articolo.

### <a name="step-1-get-audio-conferencing-licenses"></a>Passaggio 1: Ottenere licenze di audioconferenza

Ottieni una licenza per i servizi di audioconferenza per ogni persona che condurrà le riunioni. Usare l'Microsoft 365 di amministrazione per eseguire questa operazione.

1. Nell'Microsoft 365 di amministrazione, passare a **Servizi** di acquisto fatturazione e quindi nella parte inferiore della pagina  >  selezionare **Componenti aggiuntivi.**
2. Selezionare **Microsoft 365 dettagli promozionali sull'adozione di audioconferenze** e quindi selezionare Scarica  >   **adesso.**
3. Immettere il numero di licenze necessarie per gli organizzatori della riunione e quindi completare l'ordine.

    :::image type="content" source="media/audio-conferencing-smb-add.png" alt-text="Screenshot della licenza promozionale Per l'adozione di audioconferenze":::

    > [!NOTE]
    > Deselezionare o selezionare l'opzione Assegna automaticamente a tutti gli utenti senza **licenze,** a seconda che si voglia assegnare automaticamente una licenza di audioconferenza a tutti gli utenti che non hanno questa licenza.

### <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Passaggio 2: Assegnare una licenza di audioconferenza agli utenti che conducono le riunioni

Assegnare una licenza a ogni persona che condurrà le riunioni. Usare l'Microsoft 365 di amministrazione per eseguire questa operazione.

#### <a name="assign-a-license-to-one-user"></a>Assegnare una licenza a un utente

1. Nell'Microsoft 365 di amministrazione passare a **Utenti**  >  **attivi**.  
2. Selezionare la riga dell'utente a cui si vuole assegnare la licenza e quindi nel riquadro selezionare **Licenze e app.**
3. Selezionare la **Microsoft 365 audioconferenza** e quindi selezionare **Salva modifiche**.

#### <a name="assign-a-license-to-multiple-users"></a>Assegnare una licenza a più utenti

1. Nell'Microsoft 365 di amministrazione passare a **Utenti**  >  **attivi**.  
2. Selezionare i cerchi accanto agli utenti a cui si vuole assegnare la licenza e quindi selezionare **Gestisci licenze prodotto.**
3. Nel riquadro **Gestisci licenze prodotto** selezionare Assegna **altro**.
4. Selezionare la **Microsoft 365 audioconferenza** e quindi selezionare **Salva modifiche**.  

## <a name="schedule-teams-meetings-in-outlook"></a>Pianificare Teams riunioni in Outlook

Gli organizzatori della riunione possono ora pianificare le riunioni in Outlook. In Outlook passare a **Calendario** e quindi selezionare il **pulsante Nuovo Teams riunione.** I numeri di accesso esterno della riunione e l'ID conferenza vengono aggiunti automaticamente all'invito alla riunione inviato ai partecipanti alla riunione. Per altre informazioni, vedere [Pianificare una riunione Teams in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).

> [!NOTE]
> Se si vuole, è possibile personalizzare gli inviti alle riunioni per aggiungere il logo della società, i collegamenti al sito Web del supporto tecnico e alla dichiarazione di non responsabilità legale e un piè di pagina di solo testo. Per altre informazioni, vedere [Personalizzare gli inviti alle riunioni.](meeting-settings-in-teams.md#customize-meeting-invitations)

## <a name="audio-conferencing-phone-numbers"></a>Numeri di telefono per audioconferenze

Per il bridge di conferenza è possibile usare due tipi di numeri. È possibile usare **i numeri condivisi** (come nella sezione Configurare le audioconferenze più indietro in questo articolo) o **numeri dedicati.** [](#set-up-audio-conferencing) Ecco altre informazioni su ognuno di essi.

### <a name="shared-numbers"></a>Numeri condivisi

Un numero condiviso è un numero condiviso in tutte le organizzazioni. I numeri condivisi sono numeri a pedaggio e vengono assegnati automaticamente quando si configurano le audioconferenze.

Per visualizzare il numero predefinito assegnato al bridge di conferenza, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a Bridge di conferenza riunioni e quindi trovare il numero della posizione più  >  vicina.

### <a name="dedicated-numbers"></a>Numeri dedicati

Un numero dedicato è un numero disponibile solo per gli utenti. Un numero dedicato può essere un numero a pedaggio o un numero verde. Per usare un numero dedicato, è necessario prima ottenere il numero, assegnarlo al bridge di conferenza e quindi assegnare il numero a ogni persona che condurrà le riunioni.

Esistono due modi per ottenere un numero dedicato. È possibile ottenere un numero da Microsoft o trasferire (porta) un numero esistente dal provider di servizi corrente a Microsoft. Per altre informazioni su come eseguire questa operazione, vedere Recupero [dei numeri di servizio.](getting-service-phone-numbers.md)

Tenere presente che se si usa un numero verde, è necessario assegnare prima una licenza Crediti comunicazioni a ogni persona che condurrà le riunioni. Per altre informazioni, vedere [Configurare i crediti comunicazioni per l'organizzazione.](set-up-communications-credits-for-your-organization.md)

Dopo aver assegnato il numero, assegnarlo al bridge di conferenza. Usare l'Microsoft Teams di amministrazione per eseguire questa operazione.

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare a Bridge  >  **di conferenza riunioni.**
2. Selezionare **Aggiungi** e quindi **selezionare Numero a pedaggio** o Numero **verde.**
3. Nel riquadro **Aggiungi numero di** telefono selezionare il numero e quindi scegliere **Applica**.

Assegnare quindi il numero a ogni persona che condurrà le riunioni. Usare l'Microsoft Teams di amministrazione per eseguire questa operazione.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione selezionare **Utenti,** fare clic sul nome visualizzato dell'utente e selezionare **Modifica.**
2. Selezionare **Modifica** accanto a **Audioconferenza** e quindi, nel riquadro  **Audioconferenza,** selezionare un numero negli elenchi Numero a pedaggio o Numero verde e quindi selezionare **Applica**. 

## <a name="related-topics"></a>Argomenti correlati

- [Audioconferenza](audio-conferencing-in-office-365.md)
- [Configurare le audioconferenze per Teams](set-up-audio-conferencing-in-teams.md)
- [Numeri di telefono per i servizi di audioconferenza](phone-numbers-for-audio-conferencing-in-teams.md)
- [Domande ricorrenti sulle audioconferenze](audio-conferencing-common-questions.md)
- [Recupero dei numeri di servizio](getting-service-phone-numbers.md)
- [Teams licenze per i componenti aggiuntivi](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Assegnare licenze agli utenti](/microsoft-365/admin/manage/assign-licenses-to-users)