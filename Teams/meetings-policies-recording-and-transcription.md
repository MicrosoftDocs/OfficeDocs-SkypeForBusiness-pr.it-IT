---
title: Gestire i criteri delle riunioni per la registrazione e la trascrizione
author: mkbond007
ms.author: mabond
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
description: Informazioni su come gestire le impostazioni dei criteri riunione in Teams per la registrazione e la trascrizione.
ms.openlocfilehash: 06a05d2eb8a8c1542b79fa4c37b68ea4a3aa6d32
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436765"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Impostazioni dei criteri riunione per la registrazione & trascrizione

Questo articolo descrive le impostazioni dei criteri di riunione specifiche per la registrazione e la trascrizione in una riunione di Teams. Queste impostazioni sono disponibili nell'interfaccia di amministrazione del team in **Criteri riunione** > .

## <a name="transcription"></a>Trascrizione

Questa è una combinazione di criterio per organizzatore e criterio per utente. Questa impostazione controlla la disponibilità di didascalie e funzionalità di trascrizione durante la riproduzione di registrazioni delle riunioni. La persona che ha avviato la registrazione deve attivare questa impostazione per permettere alle funzionalità di operare in fase di registrazione.

Con l’attivazione di questa impostazione, viene creata una copia della trascrizione archiviata con la registrazione della riunione, che permette di eseguire **ricerche**, **CC** e **trascrizioni** nella registrazione della riunione.

## <a name="cloud-recording"></a>Registrazione cloud

Questa impostazione è una combinazione di criteri per organizzatore e per utente e controlla se le riunioni possono essere registrate. La registrazione può essere avviata dall'organizzatore della riunione o da un altro partecipante alla riunione, se l'impostazione dei criteri è attivata per il partecipante e se si tratta di un utente autenticato della stessa organizzazione.

Le persone esterne all'organizzazione, ad esempio gli utenti federati e anonimi, non possono avviare la registrazione. I guest non possono avviare o interrompere la registrazione.

![Screenshot che mostra le opzioni di registrazione](media/meeting-policies-recording.png)

Osserviamo l'esempio seguente.

| Utente                 | Criterio di riunione         | Consenti registrazione cloud |
|----------------------|------------------------|-----------------------|
| Daniela              | Globale                 | Disattivato                   |
| Amanda               | CriterioRiunionePosizione1 | Attivato                    |
| Giovanni (esterno) | Non applicabile         | Non applicabile        |

- Le riunioni organizzate da Daniela non possono essere registrate.
- Amanda non riesce a registrare le riunioni organizzate da Daniela.
- Le riunioni organizzate da Amanda possono essere registrate.
- Daniela non può registrare le riunioni organizzate da Amanda.
- John non riesce a registrare le riunioni organizzate da Amanda.

Per altre informazioni sulla registrazione di una riunione cloud, vedere [Registrazione delle riunioni cloud di Teams](cloud-recording.md).

## <a name="meetings-automatically-expire"></a>Le riunioni scadono automaticamente

Questa impostazione controlla se le registrazioni delle riunioni scadono automaticamente. Dopo aver attivato questa impostazione, avrai l'opzione di impostare una scadenza predefinita, misurata in giorni.

:::image type="content" source="media/meeting-expiration-policy.jpg" alt-text="Screenshot dall'interfaccia di amministrazione di Teams dell'impostazione di scadenza automatica delle riunioni.":::

Questa impostazione offre un semplice strumento che riduce la quantità di spazio di archiviazione usato per le registrazioni meno recenti. Il sistema OneDrive e SharePoint monitorerà la scadenza impostata in tutte le registrazioni delle riunioni e sposterà automaticamente le registrazioni nel Cestino alla data di scadenza.

### <a name="default-expiration-time"></a>Ora di scadenza predefinita

Tutte le registrazioni delle riunioni appena create avranno una scadenza predefinita di 120 giorni; tutte le registrazioni create dopo che questa funzionalità è stata attivata verranno eliminate 120 giorni dopo la data di creazione.

> [!NOTE]
> La scadenza predefinita massima per gli utenti A1 è di 30 giorni.

#### <a name="changing-default-expiration-time"></a>Modifica dell'ora di scadenza predefinita

Gli amministratori possono modificare l'impostazione Data di scadenza predefinita in PowerShell o nell'interfaccia di amministrazione di Teams. Le modifiche avranno effetto solo sulle registrazioni delle riunioni appena create da quel momento in poi; non influiranno su registrazioni create prima di tale data.

Gli amministratori non possono modificare la data di scadenza per le registrazioni delle riunioni esistenti. Questa operazione viene eseguita per proteggere la decisione dell'utente che è proprietario della registrazione. Questa impostazione consente di controllare sia le riunioni che le chiamate.

Il valore di scadenza è un numero intero per giorni.  Questo può essere impostato nel modo seguente:

- Valore minimo: **1**
- Valore massimo: **99999**
- È anche possibile impostare la scadenza su **-1** in PowerShell in modo che le registrazioni non scada mai.

Esempio di comando di PowerShell:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

### <a name="compliance"></a>Conformità

Non è consigliabile affidarsi alle impostazioni di scadenza delle riunioni per la protezione legale perché gli utenti finali possono modificare la data di scadenza di tutte le registrazioni che controllano.

#### <a name="recording-expiration-settings-and-microsoft-365-retention-policies-in-microsoft-purview"></a>Impostazioni di scadenza della registrazione e criteri di conservazione di Microsoft 365 in Microsoft Purview

La conservazione dei file ha la precedenza sull'eliminazione dei file. La registrazione di una riunione di Teams con un criterio di conservazione Purview non può essere eliminata dai criteri di scadenza della registrazione delle riunioni di Teams fino al termine del periodo di conservazione. Ad esempio, se si ha un criterio di conservazione Purview che indica che un file verrà conservato per cinque anni e un criterio di scadenza della registrazione delle riunioni di Teams impostato per 60 giorni, i criteri di scadenza della registrazione delle riunioni di Teams elimineranno definitivamente la registrazione dopo cinque anni.

Se hai un criterio di scadenza della registrazione delle riunioni di Teams e i criteri di eliminazione Purview con date di eliminazione diverse, il file verrà eliminato al più presto delle due date. Ad esempio, se hai un criterio di eliminazione Purview che indica che un file verrà eliminato dopo un anno e una scadenza della registrazione della riunione di Teams impostata per 120 giorni, i criteri di scadenza della registrazione delle riunioni di Teams elimineranno il file dopo 120 giorni.

Gli utenti possono eliminare manualmente le registrazioni prima della data di scadenza, a meno che non siano presenti criteri di conservazione Purview che ne impediscono la visualizzazione. Se una registrazione ancora nel periodo di conservazione viene eliminata manualmente da un utente, la registrazione verrà mantenuta nella raccolta di archiviazione. Tuttavia, la registrazione verrà visualizzata come eliminata per l'utente finale. Per altre informazioni, vedere [Informazioni sulla conservazione per SharePoint e OneDrive](/microsoft-365/compliance/retention-policies-sharepoint#how-retention-works-for-sharepoint-and-onedrive).

### <a name="deletion-of-recordings"></a>Eliminazione delle registrazioni

La registrazione viene in genere eliminata entro un giorno dalla data di scadenza, ma in rari casi può richiedere fino a cinque giorni. Il proprietario del file riceverà una notifica tramite posta elettronica alla scadenza della registrazione e verrà indirizzato al Cestino per recuperare la registrazione.

> [!NOTE]
> Alla data di scadenza, la registrazione viene spostata nel Cestino e il campo della data di scadenza viene cancellato. Se si recupera la registrazione dal Cestino, non verrà eliminata di nuovo da questa funzionalità perché la data di scadenza è stata cancellata.

### <a name="expiration-of-migrated-recordings-from-stream-classic"></a>Scadenza della migrazione delle registrazioni da Stream (versione classica)

Le registrazioni di cui è stata eseguita la migrazione da Stream (versione classica) non avranno una scadenza impostata. È consigliabile invece che gli amministratori esercizzino solo la migrazione delle registrazioni che vogliono conservare. Per altri dettagli, vedere [la documentazione relativa alla migrazione Stream (versione classica)](/stream/streamnew/stream-classic-to-new-migration-overview).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Archiviare le registrazioni al di fuori del paese o dell'area geografica

Questo criterio controlla se i record delle riunioni possono essere archiviati in modo permanente in un altro paese o area geografica. Se è abilitata, non è possibile eseguire la migrazione delle registrazioni. Per altre informazioni sulle riunioni sul cloud e sulla posizione in cui vengono archiviate le registrazioni, vedere [Registrazione delle riunioni cloud di Teams](cloud-recording.md).

## <a name="related-topics"></a>Argomenti correlati

- [Gestire i criteri di riunione in Teams](meeting-policies-overview.md)
- [Assegnare criteri agli utenti in Teams](policy-assignment-overview.md)
- [Registrazione di riunioni nel cloud](cloud-recording.md)
- [Gestire chi può pianificare le riunioni](manage-who-can-schedule-meetings.md)
