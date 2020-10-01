---
title: Configurare i servizi di audioconferenza per piccole e medie imprese
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: jonorton, tonysmit
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Informazioni su come impostare i servizi di audioconferenza nella piccola o media impresa per le persone che hanno bisogno di usare un telefono per chiamare le riunioni. '
ms.openlocfilehash: 648a6342adf0fc035dcd33c6eb11efb40b0d4eed
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328436"
---
# <a name="set-up-audio-conferencing-for-small-and-medium-businesses"></a>Configurare i servizi di audioconferenza per piccole e medie imprese

Con i servizi di audioconferenza, gli utenti possono chiamare riunioni di teams usando un telefono invece di usare l'app Teams nel dispositivo mobile o nel computer in uso.  

Se si è una piccola o media impresa con un massimo di 300 utenti e attualmente non si hanno licenze per i servizi di audioconferenza, è possibile ottenere una conferenza audio gratuita per un anno. Questa offerta gratuita è disponibile a partire dal 1 ° ottobre 2020.

La licenza per i componenti aggiuntivi per i servizi di audioconferenza può essere applicata agli utenti che hanno licenze Microsoft 365 Business Basic, business standard, Business Premium, Enterprise E1 o Enterprise E3. Per altre informazioni, vedere [licenze per i componenti aggiuntivi](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) per i team

> [!NOTE]
> Se si dispone di Enterprise E5 o Microsoft 365 Business Voice, non sarà possibile usare l'offerta di servizi di audioconferenza gratuita perché queste licenze includono già i servizi di audioconferenza.

In questo articolo illustreremo come configurare i servizi di audioconferenza. È necessario soltanto configurare l'audioconferenza solo per gli utenti che intendono programmare o condurre riunioni. I partecipanti alla riunione che chiamano le riunioni non hanno bisogno di licenze o altre configurazioni. Per altre informazioni, vedere Servizi di [audioconferenza](audio-conferencing-in-office-365.md).

## <a name="step-1-get-audio-conferencing-licenses"></a>Passaggio 1: ottenere le licenze per i servizi di audioconferenza

Ottenere una licenza per i servizi di audioconferenza per ogni persona che guiderà le riunioni. Per eseguire questa operazione, usare l'interfaccia di amministrazione di Microsoft 365.

1. Nell'interfaccia di amministrazione di Microsoft 365 accedere a **Billing**  >  **servizi di acquisto**di fatturazione e quindi nella parte inferiore della pagina selezionare **componenti**aggiuntivi. 
2. Selezionare Dettagli promo per l'adozione di servizi di **audioconferenza Microsoft 365**  >  **Details**.
3. Immettere il numero di licenze necessarie per gli organizzatori della riunione e quindi completare l'ordine.

> [!NOTE]
> Deselezionare o selezionare **assegna automaticamente a tutti gli utenti senza licenze**, a seconda che si voglia assegnare automaticamente una licenza di audioconferenza a tutti gli utenti che non hanno questa licenza.

## <a name="step-2-assign-an-audio-conferencing-license-to-users-who-lead-meetings"></a>Passaggio 2: assegnare una licenza di audioconferenza agli utenti che conducono riunioni

Assegnare una licenza a ogni persona che porterà riunioni. Per eseguire questa operazione, usare l'interfaccia di amministrazione di Microsoft 365.

### <a name="assign-a-license-to-one-user"></a>Assegnare una licenza a un utente

1. Nell'interfaccia di amministrazione di Microsoft 365 **passa a utenti**  >  **attivi**.  
2. Selezionare la riga dell'utente a cui si vuole assegnare la licenza e quindi nel riquadro selezionare **licenze e app**.
3. Selezionare la casella di controllo **audioconferenza Microsoft 365** e quindi fare clic su **Salva modifiche**. 

### <a name="assign-a-license-to-multiple-users"></a>Assegnare una licenza a più utenti

1. Nell'interfaccia di amministrazione di Microsoft 365 **passa a utenti**  >  **attivi**.  
2. Selezionare i cerchi accanto agli utenti a cui si vuole assegnare la licenza e quindi selezionare **Gestisci licenze di prodotto**.
3. Nel riquadro **Gestisci licenze di prodotto** selezionare **assegna altro**.
4. Selezionare la casella di controllo **audioconferenza Microsoft 365** e quindi fare clic su **Salva modifiche**.  

## <a name="step-3-find-or-get-a-phone-number-for-your-conferencing-bridge"></a>Passaggio 3: trovare o ottenere un numero di telefono per il Bridge di conferenza

È necessario un numero di telefono (detto anche numero di servizio) per il Bridge di conferenza in modo che possa essere usato negli inviti alle riunioni. Puoi scegliere di usare un **numero condiviso** o un **numero dedicato**. Entrambi i tipi di numeri possono essere usati da qualsiasi chiamante per partecipare a una riunione.

### <a name="use-a-shared-number"></a>Usare un numero condiviso

Un numero condiviso è un numero condiviso in tutte le organizzazioni. I numeri condivisi vengono assegnati automaticamente quando si configurano i servizi di audioconferenza. Questi numeri condivisi sono numeri a pagamento, in cui possono essere applicati costi interurbani.

Per trovare il numero predefinito assegnato al Bridge per i servizi di conferenza, nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, accedere a **Meetings**  >  **Bridge conferenza**riunioni e quindi trovare il numero per il percorso più vicino.

### <a name="get-a-dedicated-number"></a>Ottenere un numero dedicato

Un numero dedicato è un numero disponibile solo per gli utenti. Un numero dedicato può essere un numero a pagamento o un numero verde. Per usare un numero dedicato, è necessario prima di tutto ottenere il numero e quindi assegnarlo al Bridge di conferenza.  

Ci sono un paio di modi per ottenere un numero dedicato. È possibile ottenere un numero da Microsoft o trasferire (porta) un numero esistente dal provider di servizi corrente a Microsoft. Per altre informazioni su come eseguire questa operazione, vedere [recupero di numeri di servizio](getting-service-phone-numbers.md).

> [!NOTE]
> Se si usa un numero verde, è necessario prima di tutto assegnare una licenza per i crediti di comunicazione a ogni persona che guiderà le riunioni. Per altre informazioni, vedere [configurare i crediti per le comunicazioni per l'organizzazione](set-up-communications-credits-for-your-organization.md).

Dopo aver ottenuto il numero, assegnarlo al Bridge conferenza. Per eseguire questa operazione, usare l'interfaccia di amministrazione di Microsoft teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams **Meetings**passa a  >  **Bridge conferenza**riunioni.
2. Selezionare **Aggiungi**e quindi selezionare numero a **pagamento** o **numero verde**.
3. Nel riquadro **Aggiungi numero di telefono** selezionare il numero e quindi fare clic su **applica**.

## <a name="step-4-assign-a-dial-in-number-to-users-who-lead-meetings"></a>Passaggio 4: assegnare un numero di accesso esterno agli utenti che conducono riunioni

Assegnare un numero di accesso esterno per ogni persona che porterà riunioni. Per eseguire questa operazione, usare l'interfaccia di amministrazione di Microsoft teams.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare **utenti**, fare clic sul nome visualizzato dell'utente e quindi selezionare **modifica**.
2. Selezionare **modifica**   accanto a servizi di **audioconferenza**e quindi nel riquadro **audioconferenza**   selezionare un numero nell'elenco a **pagamento**   o a numero **verde**   e quindi selezionare **applica**.

## <a name="step-5-schedule-a-teams-meeting-in-outlook"></a>Passaggio 5: pianificare una riunione di teams in Outlook

Per pianificare una riunione, in Outlook passa a **Calendario**e quindi seleziona il pulsante **nuova riunione teams** . I numeri di accesso esterno impostati per l'utente e l'ID conferenza vengono aggiunti automaticamente all'invito alla riunione inviato ai partecipanti alla riunione.

Per altre informazioni, vedere [pianificare una riunione di team in Outlook](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f).

> [!NOTE]
> Se si vuole, è possibile personalizzare gli inviti alle riunioni per aggiungere il logo della società, i collegamenti al sito Web del supporto e il Disclaimer legale e un piè di pagina di solo testo. Vedere [Personalizzare gli inviti alle riunioni](meeting-settings-in-teams.md#customize-meeting-invitations).

## <a name="related-topics"></a>Argomenti correlati

- [Audioconferenza](audio-conferencing-in-office-365.md)
- [Configurare i servizi di audioconferenza per i team](set-up-audio-conferencing-in-teams.md)
- [Domande ricorrenti sulle audioconferenze](audio-conferencing-common-questions.md)
- [Recupero di numeri di servizio](getting-service-phone-numbers.md)
- [Licenze per i componenti aggiuntivi Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [Assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
