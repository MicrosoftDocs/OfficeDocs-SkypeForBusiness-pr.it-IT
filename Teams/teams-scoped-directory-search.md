---
title: Limitare gli utenti che possono visualizzare durante la ricerca nella directory in Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Informazioni su come limitare gli utenti che possono vedere quando cercano nella directory in Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: c20c5acdafff69e5a43f02093b515b456daa8ff7
ms.sourcegitcommit: 193aec6f3f6b6ac14b07e778b3485eed813f5e99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046428"
---
# <a name="limit-who-users-can-see-when-searching-the-directory-in-teams"></a>Limitare gli utenti che possono visualizzare durante la ricerca nella directory in Teams

Microsoft Teams consente alle organizzazioni di fornire visualizzazioni personalizzate della directory agli utenti. Queste visualizzazioni possono essere utili se:

- L'organizzazione ha più società all'interno del tenant che si vogliono mantenere separate.
- Per i criteri aziendali è necessario impedire a determinati gruppi all'interno dell'organizzazione di comunicare tra loro.
- L'istituto di istruzione vuole limitare le chat tra docenti e studenti.

Sono disponibili due opzioni per limitare gli utenti che possono vedere quando eseguono ricerche nella directory in Teams:

- [Ostacoli all'informazione in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Criteri rubrica in Exchange Online](/exchange/address-books/address-book-policies/address-book-policies)

Se si usa una delle due opzioni, è necessario attivare la ricerca per nome nell'interfaccia di amministrazione di Teams.

È consigliabile usare le barriere alle informazioni se l'organizzazione soddisfa [le licenze e le autorizzazioni richieste](/microsoft-365/compliance/information-barriers#required-licenses-and-permissions).

Per attivare la ricerca per nome

1. Nell'interfaccia di amministrazione Microsoft Teams selezionare **impostazioni Teams** >  **Teams**.

1. In **Cerca per nome**, accanto a **Ambito ricerca directory con un criterio rubrica di Exchange**, attivare l'interruttore.

> [!Note]
> L'applicazione di questa modifica potrebbe richiedere alcune ore.
> 
> Attivando la ricerca per nome, la casella **Cerca team** e l'elenco dei team pubblici vengono nascosti in **Partecipa o crea un team** in Teams. Disabiliterà inoltre la partecipazione a un team digitando `/join` nella casella di comando nella parte superiore di Teams.
