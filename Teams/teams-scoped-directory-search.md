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
description: Informazioni su come usare la ricerca nell'ambito di Microsoft Teams per fornire visualizzazioni personalizzate della directory.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1ba7de8cea23efc23f1eaa6c568d87b0d3ec750
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558325"
---
# <a name="use-microsoft-teams-scoped-directory-search"></a>Usare la ricerca nella directory con ambito di Microsoft Teams

La ricerca nell'ambito di Microsoft Teams consente alle organizzazioni di creare limiti virtuali che controllano come gli utenti possono trovare e comunicare con altri utenti dell'organizzazione. 

Microsoft Teams consente alle organizzazioni di fornire visualizzazioni personalizzate della directory agli utenti. Microsoft Teams usa [criteri di protezione delle informazioni](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) per supportare queste visualizzazioni personalizzate. Una volta abilitati i criteri, l'ambito dei risultati restituiti dalle ricerche di altri utenti (ad esempio per avviare una chat o per aggiungere membri a un team) verrà rientrato nell'ambito in base ai criteri configurati. Gli utenti non saranno in grado di cercare o individuare alcun team quando è attivo l'ambito di ricerca, ma i membri esistenti in questi team possono aggiungere utenti, come consentito dai criteri di protezione delle informazioni attive.

> [!NOTE]
> Negli ambienti ibridi di Exchange questa caratteristica funziona solo con le cassette postali di Exchange Online e non con le cassette postali locali.

## <a name="when-should-you-use-scoped-directory-searches"></a>Quando usare le ricerche nella directory con ambito?

Gli scenari che traggono vantaggio dalle ricerche nella directory con ambito sono simili a quelli dei criteri della Rubrica. Ad esempio, è possibile usare la ricerca nella directory con ambito nelle situazioni seguenti:

- L'organizzazione ha più società all'interno del tenant che si vogliono mantenere separate. 
- L'istituto di istruzione vuole limitare le chat tra docenti e studenti. 
 
Per informazioni su come usare i criteri della rubrica, vedere Criteri per le [barriere linguistiche in Exchange Online.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)

> [!IMPORTANT]
> I criteri della rubrica forniscono solo una separazione virtuale degli utenti dal punto di vista della directory. È anche importante tenere presente che i dati utente già memorizzati nella cache prima dell'applicazione dei criteri della rubrica nuovi o aggiornati rimarranno disponibili per gli utenti per un massimo di 30 giorni.

## <a name="turn-on-scoped-directory-search"></a>Attivare la ricerca nella directory con ambito

1. Usare i criteri di protezione delle informazioni per configurare l'organizzazione in sottogruppi virtuali. Per altre informazioni, vedere [Definire i criteri di protezione delle informazioni.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-policies)

2. Nell'interfaccia di amministrazione di Microsoft Teams, selezionare Impostazioni di Teams **a livello di**  >  **organizzazione.**

3. In **Cerca,** accanto a Ricerca nella directory di ambito in Teams usando i criteri della rubrica **di Exchange (ABP),** attiva **l'interruttore.**

    ![Ricerca nella directory con ambito nell'interfaccia di amministrazione di Microsoft Teams](media/teams-scoped-directory-search-image1.png)


> [!IMPORTANT]
> Il replica di questa modifica può richiedere alcune ore.
