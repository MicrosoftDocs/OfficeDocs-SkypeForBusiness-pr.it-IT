---
title: Aggiungere il dominio SMTP di Microsoft teams come dominio del mittente consentito in Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: Informazioni su come aggiungere il dominio SMTP di Microsoft teams come dominio del mittente consentito in Exchange Online per inviare notifiche ai membri del team.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ae8be5c4b596b8815b8677b6214163924cbb183
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572553"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Aggiungere il dominio SMTP di Microsoft teams come dominio del mittente consentito in Exchange Online 
=============================================================================

Se si crea un gruppo di Office 365 nella console di amministrazione o tramite Outlook, Exchange Online viene usato per inviare le notifiche di un membro del team che viene aggiunto a un gruppo. Questi messaggi vengono generati dal tenant in quanto rappresentano il nome di dominio completo SMTP predefinito per l'utente.

![Screenshot dell'intestazione di un messaggio che mostra l'aggiunta di un utente a un gruppo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams USA anche Microsoft Exchange Online per inviare notifiche ai membri del team quando sono state aggiunte. La differenza che rappresenta il nome di dominio completo del messaggio SMTP è "@email. teams.microsoft.com" per i tenant commerciali/commerciali e "@GCC-email.teams.com" per gli inquilini pubblici e potrebbe essere intercettata tramite filtro della posta indesiderata.

![Screenshot dell'intestazione di un messaggio che mostra l'aggiunta di un utente a un gruppo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Per ottenere risultati ottimali e un'operazione ottimale, è consigliabile aggiungere il dominio SMTP di Microsoft teams all'elenco "domini mittenti consentiti" nella configurazione della posta indesiderata di Exchange Online:

![Screenshot della sezione Consenti elenchi di impostazioni di configurazione della posta indesiderata](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
