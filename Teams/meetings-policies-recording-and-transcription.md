---
title: Gestire i criteri delle riunioni per la registrazione e la trascrizione
author: KarliStites
ms.author: kastites
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
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
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: Informazioni su come gestire le impostazioni dei criteri delle riunioni in Teams per la registrazione e la trascrizione.
ms.openlocfilehash: ee558ae87d7bea781cae3d2bc267f82bc1fdb18a
ms.sourcegitcommit: faeb8976299375e7658499ff31d25e8ef6003144
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2022
ms.locfileid: "62224073"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Impostazioni dei criteri di riunione per la registrazione & trascrizione

Questo articolo descrive le impostazioni dei criteri di riunione specifiche per la registrazione e la trascrizione, tra cui:

- [Consenti la trascrizione](#allow-transcription)
- [Consenti registrazione cloud](#allow-cloud-recording)
- [Archiviare registrazioni al di fuori del paese o dell'area geografica](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>Consenti la trascrizione

Questa è una combinazione di criterio per organizzatore e criterio per utente. Questa impostazione controlla la disponibilità di didascalie e funzionalità di trascrizione durante la riproduzione di registrazioni delle riunioni. La persona che ha avviato la registrazione ha bisogno di questa impostazione attivata per usare queste funzionalità con la registrazione.

Se si attiva questa impostazione, viene creata una copia della trascrizione archiviata con la registrazione della riunione, che consente di eseguire **ricerche,** **CC** e **trascrizioni** nella registrazione della riunione.

La trascrizione per le riunioni registrate è attualmente supportata solo per gli utenti che impostano la lingua o parlano inglese nelle riunioni Teams riunioni.

## <a name="allow-cloud-recording"></a>Consenti la registrazione cloud

Questa impostazione è una combinazione di criteri per organizzatore e per utente e controlla se le riunioni possono essere registrate. La registrazione può essere avviata dall'organizzatore della riunione o da un altro partecipante alla riunione, se l'impostazione dei criteri è attivata per il partecipante e se si tratta di un utente autenticato della stessa organizzazione.

Le persone esterne all'organizzazione, ad esempio gli utenti federati e anonimi, non possono avviare la registrazione. Gli utenti guest non possono avviare o interrompere la registrazione.

![Screenshot che mostra le opzioni di registrazione](media/meeting-policies-recording.png)

Osserviamo l'esempio seguente.

|Utente |Criterio di riunione  |Consenti registrazione cloud |
|---------|---------|---------|
|Daniela | Globale   | Disattivato |
|Amanda | CriterioRiunionePosizione1 | Attivato|
|Luca (utente esterno) | Non applicabile | Non applicabile|

- Le riunioni organizzate da Daniela non possono essere registrate.
- Non è possibile registrare le riunioni organizzate da Daniela.
- Le riunioni organizzate da Amanda possono essere registrate.
- Daniela non può registrare le riunioni organizzate da Amanda.
- Giovanni non può registrare le riunioni organizzate da Amanda.

Per altre informazioni sulla registrazione di una riunione cloud, vedere [Registrazione delle riunioni cloud di Teams](cloud-recording.md).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Archiviare registrazioni al di fuori del paese o dell'area geografica

Questo criterio controlla se i record delle riunioni possono essere archiviati in modo permanente in un altro paese o area geografica. Se è abilitato, non è possibile eseguire la migrazione delle registrazioni. Per altre informazioni sulle riunioni nel cloud e sulla posizione in cui sono archiviate le registrazioni, vedere Teams [registrazione delle riunioni cloud.](cloud-recording.md)

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri agli utenti in Teams](policy-assignment-overview.md)
- [Registrazione delle riunioni nel cloud](cloud-recording.md)
