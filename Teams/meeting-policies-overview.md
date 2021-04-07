---
title: Gestire i criteri di riunione
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: Informazioni su come gestire le impostazioni dei criteri di riunione in Teams e usarle per controllare le funzionalità disponibili per i partecipanti alle riunioni programmate dagli utenti.
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598732"
---
# <a name="manage-meeting-policies-in-teams"></a>Gestire i criteri di riunione in Teams

<a name="bkautomatically-admit-people"> </a>

<a name="bkallow-a-participant-to-give-or-request-control"> </a>

<a name="bkallow-transcription"> </a>

I criteri riunione vengono usati per controllare le funzionalità disponibili per i partecipanti alle riunioni programmate dagli utenti nell'organizzazione. È possibile usare il criterio globale (predefinito a livello di organizzazione) creato automaticamente oppure creare e assegnare criteri personalizzati. Si possono gestire i criteri di riunione nell'interfaccia di amministrazione di Microsoft Teams o tramite [PowerShell](teams-powershell-overview.md).

> [!NOTE]
> Per informazioni sull'utilizzo dei ruoli per gestire le autorizzazioni dei relatori e dei partecipanti delle riunioni, vedere [Ruoli in una riunione di Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

È possibile implementare i criteri nei modi descritti di seguito. La scelta influisce sull'esperienza di riunione per gli utenti prima, durante o dopo una riunione.

|Tipo di implementazione  |Descrizione  |
|---------|---------|
|Per organizzatore    |Quando si implementa un criterio per organizzatore, tutti i partecipanti alla riunione ereditano il criterio dell'organizzatore. Ad esempio, **Ammetti automaticamente le persone** è un criterio per organizzatore e controlla se gli utenti accedono direttamente alla riunione oppure attendono nella sala di attesa per le riunioni pianificate dall'utente a cui è assegnato il criterio.          |
|Per utente    |Quando si implementano criteri per utente, viene applicato solo il criterio per utente per limitare l'uso di determinate funzionalità da parte dell'organizzatore e/o dei partecipanti alla riunione. Ad esempio, **Consenti l'uso di Riunione immediata nei canali** è un criterio per utente.     |
|Per organizzatore e per utente     |Quando si implementa una combinazione di criteri per organizzatore e per utente, l'uso di alcune funzionalità da parte dei partecipanti alla riunione è limitato, in base ai criteri applicati al singolo utente e ai criteri dell'organizzatore. Ad esempio, **Consenti registrazione cloud** è un criterio per organizzazione e per utente. Attivare questa impostazione per consentire all'organizzatore della riunione e ai partecipanti di avviare o interrompere una registrazione.

È possibile modificare le impostazioni nel criterio globale o creare e assegnare uno o più criteri personalizzati. Se non si creano e assegnano criteri personalizzati, gli utenti riceveranno il criterio globale.

> [!NOTE]
> Il pulsante Dettagli riunione sarà disponibile se un utente ha le licenze di audioconferenza abilitate o se l'utente è autorizzato a partecipare alle audioconferenze; in caso contrario, i dettagli della riunione non saranno disponibili.

## <a name="create-a-custom-meeting-policy"></a>Creare un criterio di riunione personalizzato

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** > **Criteri riunione**.
2. Fare clic su **Aggiungi**.
3. Immettere un nome e una descrizione per il criterio. Il nome non può contenere caratteri speciali o più di 64 caratteri.
4. Scegliere le impostazioni desiderate.
5. Fare clic su **Salva**.

Ad esempio, si supponga di avere un gruppo di utenti e di voler limitare la larghezza di banda necessaria per la riunione. È possibile creare un nuovo criterio personalizzato denominato "Larghezza di banda limitata" e disabilitare le impostazioni seguenti:

In **Audio e video**:

- Disattivare Consenti registrazione cloud.
- Disattivare Consenti video IP.

In **Condivisione di contenuti**:

- Disabilitare la modalità di condivisione dello schermo.
- Disattivare Consenti la lavagna.
- Disattivare Consenti note condivise.

Assegnare poi il criterio agli utenti.

## <a name="edit-a-meeting-policy"></a>Modificare un criterio di riunione

È possibile modificare il criterio globale e i criteri personalizzati creati.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni** > **Criteri riunione**.
2. Selezionare il criterio facendo clic a sinistra del nome del criterio, quindi selezionare **Modifica**.
3. Da lì, apportare le modifiche desiderate.
4. Fare clic su **Salva**.

> [!NOTE]
> A ogni utente può essere assegnato un solo criterio di riunione per volta.

## <a name="assign-a-meeting-policy-to-users"></a>Assegnare un criterio riunione agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> Non è possibile eliminare un criterio a cui sono utenti. È prima di tutto necessario assegnare un criterio diverso a tutti gli utenti interessati, quindi sarà possibile eliminare il criterio originale.

## <a name="meeting-policy-settings"></a>Impostazioni dei criteri di riunione

Quando si seleziona un criterio esistente nella pagina **Criteri riunione** o si seleziona **Aggiungi** per aggiungere un nuovo criterio, è possibile configurare le impostazioni per gli elementi seguenti.

- [Generale](meeting-policies-in-teams-general.md)
- [Audio e video](meeting-policies-audio-and-video.md)
- [Condivisione di contenuti](meeting-policies-content-sharing.md)
- [Partecipanti e ospiti](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare i criteri agli utenti in Teams](assign-policies.md)
- [Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams](meeting-policies-restricted-anonymous-access.md)