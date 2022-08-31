---
title: Gestire chi può avviare riunioni immediate e pianificare riunioni
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Informazioni su come usare le impostazioni dei criteri riunione di Teams per controllare chi può avviare riunioni immediate e pianificare riunioni.
ms.openlocfilehash: 6736ecd20ef4b0e9eb082e83bd8212597da5f7ab
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466290"
---
# <a name="manage-who-can-start-instant-meetings-and-schedule-meetings"></a>Gestire chi può avviare riunioni immediate e pianificare riunioni

Gli amministratori possono limitare gli utenti che possono avviare riunioni immediate e pianificare riunioni in Teams. Ciò può risultare particolarmente utile per motivi di privacy e sicurezza, in cui è consigliabile evitare che determinati utenti configutino le riunioni.

Le impostazioni dei criteri riunione sono attivate per impostazione predefinita. Queste impostazioni sono disponibili nell'interfaccia di amministrazione di Teams in **Criteri riunione** > .

- **Riunione immediata nei canali**: controlla se un utente può avviare una riunione immediata in un canale.
- **Pianificazione delle riunioni del canale**: controlla se un utente può pianificare una riunione in un canale.
- **Pianificazione di una riunione privata**: controlla se un utente può pianificare una riunione privata in Teams. Una riunione è privata quando non viene pubblicata in un canale in un team.
- **Componente aggiuntivo di Outlook**: controlla se un utente può pianificare una riunione privata da Outlook. Una riunione è privata quando non viene pubblicata in un canale in un team.
- **Riunione immediata nelle riunioni private**: controlla se un utente può avviare una riunione privata immediata.

> [!NOTE]
> Se la riunione è stata inviata da un delegato, a cui sono state concesse le autorizzazioni per inviare inviti alle riunioni per conto di un'altra persona, ad esempio un responsabile, l'impostazione dei criteri della riunione viene applicata alla persona che ha concesso l'autorizzazione (il responsabile).

## <a name="channel-meetings"></a>Riunioni di canale

Se si hanno requisiti di conformità che impongono a specifiche persone di avviare riunioni istantanee del canale e pianificare riunioni del canale, è possibile creare o aggiornare i criteri per le riunioni in modo da limitare queste impostazioni. È quindi possibile creare un criterio distinto attribuito agli utenti a cui si vogliono avviare riunioni istantanee del canale e pianificare riunioni del canale.

1. Nell'interfaccia di amministrazione di Teams passare a **Criteri****riunione riunioni** >  e scegliere il criterio da aggiornare. Per creare un nuovo criterio, fare clic su **Aggiungi**.
1. In **Generale**, attiva o disattiva le opzioni seguenti:
    1. Se vuoi limitare chi può avviare riunioni immediate in un canale, imposta **Riunione immediata nei canali** su **Disattivato**.
    1. Per limitare gli utenti autorizzati a pianificare riunioni in un canale, impostare **Pianificazione delle riunioni del canale** su **Disattivato**.
1. Fare clic su **Salva** nella parte inferiore della pagina.

## <a name="private-meetings"></a>Riunioni private

Se si hanno requisiti di conformità che impongono a specifiche persone di avviare riunioni private immediate e pianificare riunioni private, è possibile creare o aggiornare i criteri delle riunioni per limitare queste impostazioni. È quindi possibile creare un criterio distinto attribuito agli utenti che si desidera avviare riunioni immediate e pianificare riunioni private.

1. Nell'interfaccia di amministrazione di Teams passare a **Criteri****riunione riunioni** >  e scegliere il criterio da aggiornare. Per creare un nuovo criterio, fare clic su **Aggiungi**.
1. In **Generale**, attiva o disattiva le opzioni seguenti:
    1. Se si vuole limitare chi può avviare riunioni private immediate, impostare **Riunione immediata nelle riunioni private** su **Disattivato**.
    1. Se si vuole limitare chi può pianificare riunioni private in un canale, impostare pianificazione delle **riunioni private** e componente **aggiuntivo di Outlook** su **Disattivato**.
1. Fare clic su **Salva** nella parte inferiore della pagina.

## <a name="turning-off-meeting-policy-settings"></a>Disattivazione delle impostazioni dei criteri riunione

Dopo aver disattivato una di queste impostazioni dei criteri riunione, qualsiasi utente assegnato al criterio non potrà avviare o pianificare riunioni di quel tipo. I collegamenti di partecipazione alla riunione e gli ID conferenza di tutte le riunioni esistenti di quel tipo avviate o pianificate in precedenza dall'utente non funzioneranno. Le conversazioni, i file, le lavagne, le registrazioni, le trascrizioni e altri contenuti correlati alla riunione vengono mantenuti e gli utenti possono ancora accedervi.

Se un'impostazione dei criteri riunione è disattivata e quindi attivata di nuovo per un utente, tutte le riunioni pianificate in precedenza dall'utente diventano attive e le persone possono parteciparvi usando il collegamento per partecipare alla riunione o tramite telefono.

## <a name="related-topics"></a>Argomenti correlati

[Modificare la data di scadenza delle riunioni - controlli per l'utente finale](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Gestire i criteri di riunione in Teams](meeting-policies-overview.md)

[Assegnare i criteri agli utenti in Teams](policy-assignment-overview.md)

[Panoramica di PowerShell per Teams](teams-powershell-overview.md)

[Limiti e specifiche per Microsoft Teams](/microsoftteams/limits-specifications-teams)
