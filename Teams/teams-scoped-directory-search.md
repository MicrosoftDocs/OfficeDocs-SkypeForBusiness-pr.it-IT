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
description: Informazioni su come usare Microsoft Teams ricerca nella directory con ambito per fornire visualizzazioni personalizzate della directory.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: df03c4d59b55780f38b5f99983a11fd5dc905e40
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587015"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Usare la ricerca nella directory con ambito di Microsoft Teams

Microsoft Teams ricerca nella directory con ambito consente alle organizzazioni di creare limiti virtuali che controllano il modo in cui gli utenti possono trovare e comunicare con altri utenti dell'organizzazione. 

Microsoft Teams consente alle organizzazioni di fornire visualizzazioni personalizzate della directory agli utenti. Microsoft Teams criteri [Disassamento informazioni](/microsoft-365/compliance/information-barriers) per supportare queste visualizzazioni personalizzate. Una volta abilitati i criteri, l'ambito dei risultati restituiti dalle ricerche di altri utenti, ad esempio per avviare una chat o per aggiungere membri a un team, sarà in base ai criteri configurati. Gli utenti non saranno in grado di cercare o individuare alcun team quando è attiva la ricerca con ambito, ma i membri esistenti in questi team possono aggiungere utenti, come consentito dai criteri di Protezione delle informazioni attivi.

> [!NOTE]
> In Exchange ibridi, questa caratteristica funziona solo con le cassette postali Exchange Online e non con le cassette postali locali.

Vedere anche [Criteri della Rubrica in Exchange Online](/exchange/address-books/address-book-policies/address-book-policies).

## <a name="when-should-you-use-scoped-directory-searches"></a>Quando usare le ricerche nella directory con ambito?

Gli scenari che traggono vantaggio dalle ricerche nella directory con ambito sono simili a quelli dei criteri della rubrica. Ad esempio, è possibile usare la ricerca nella directory con ambito nelle situazioni seguenti:

- L'organizzazione ha più società all'interno del tenant che si vogliono mantenere separate. 
- L'istituto di istruzione vuole limitare le chat tra docenti e studenti. 
 
Per informazioni su come usare i criteri della rubrica, vedere Criteri di Protezione delle informazioni [in Exchange Online](/microsoft-365/compliance/information-barriers).

> [!IMPORTANT]
> I criteri della rubrica offrono solo una separazione virtuale degli utenti dal punto di vista della directory. È anche importante tenere presente che tutti i dati degli utenti già memorizzati nella cache, prima dell'applicazione dei criteri della rubrica nuovi o aggiornati, rimarranno disponibili per gli utenti per un massimo di 30 giorni.

## <a name="turn-on-scoped-directory-search"></a>Attivare la ricerca nella directory con ambito

1. Usare i criteri Information Barrier per configurare l'organizzazione in sottogruppi virtuali. Per altre informazioni, vedere [Definire i criteri di protezione delle informazioni.](/microsoft-365/compliance/information-barriers-policies)

2. Nell'Microsoft Teams di amministrazione selezionare **Impostazioni** a livello di  >  **organizzazione Teams impostazioni**.

3. In **Cerca**, accanto a **Ambito ricerca directory in Teams usando** un criterio rubrica Exchange , attivare l'interruttore . 

    ![Ricerca nella directory con ambito nell Microsoft Teams di amministrazione](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> La replica di questa modifica può richiedere alcune ore.
