---
title: Usare la ricerca nella directory con ambito di Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come usare la ricerca nella directory con ambito Microsoft Teams per fornire visualizzazioni personalizzate della directory.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ede4b60878dbdd44edf369b0a3c1bb861ffe366
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094026"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Usare la ricerca nella directory con ambito di Microsoft Teams

La ricerca nella directory con ambito Microsoft Teams consente alle organizzazioni di creare limiti virtuali che controllano il modo in cui gli utenti possono trovare e comunicare con altri utenti dell'organizzazione. 

Microsoft Teams consente alle organizzazioni di fornire visualizzazioni personalizzate della directory agli utenti. Microsoft Teams usa i [criteri Information Barrier per](/microsoft-365/compliance/information-barriers) supportare queste visualizzazioni personalizzate. Una volta abilitati i criteri, l'ambito dei risultati restituiti dalle ricerche di altri utenti, ad esempio per avviare una chat o per aggiungere membri a un team, sarà in base ai criteri configurati. Gli utenti non saranno in grado di cercare o individuare alcun team quando è attiva la ricerca con ambito, ma i membri esistenti in questi team possono aggiungere utenti, come consentito dai criteri di Protezione delle informazioni attivi.

> [!NOTE]
> Negli ambienti ibridi di Exchange questa caratteristica funziona solo con le cassette postali di Exchange Online e non con le cassette postali locali.

## <a name="when-should-you-use-scoped-directory-searches"></a>Quando usare le ricerche nella directory con ambito?

Gli scenari che traggono vantaggio dalle ricerche nella directory con ambito sono simili a quelli dei criteri della rubrica. Ad esempio, è possibile usare la ricerca nella directory con ambito nelle situazioni seguenti:

- L'organizzazione ha più società all'interno del tenant che si vogliono mantenere separate. 
- L'istituto di istruzione vuole limitare le chat tra docenti e studenti. 
 
Per informazioni su come usare i criteri della rubrica, vedere Criteri [di Protezione delle informazioni in Exchange Online.](/microsoft-365/compliance/information-barriers)

> [!IMPORTANT]
> I criteri della rubrica offrono solo una separazione virtuale degli utenti dal punto di vista della directory. È anche importante tenere presente che tutti i dati degli utenti già memorizzati nella cache, prima dell'applicazione dei criteri della rubrica nuovi o aggiornati, rimarranno disponibili per gli utenti per un massimo di 30 giorni.

## <a name="turn-on-scoped-directory-search"></a>Attivare la ricerca nella directory con ambito

1. Usare i criteri Information Barrier per configurare l'organizzazione in sottogruppi virtuali. Per altre informazioni, vedere [Definire i criteri di protezione delle informazioni.](/microsoft-365/compliance/information-barriers-policies)

2. Nell'interfaccia di amministrazione di Microsoft Teams selezionare **Impostazioni di Teams a livello di**  >  **organizzazione.**

3. In **Cerca**, accanto a Cerca nella directory ambito **in Teams con** un criterio rubrica di Exchange , attivare l'interruttore **.**

    ![Ricerca nella directory con ambito nell'interfaccia di amministrazione di Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> La replica di questa modifica può richiedere alcune ore.