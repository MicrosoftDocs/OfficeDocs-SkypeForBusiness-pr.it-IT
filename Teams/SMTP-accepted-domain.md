---
title: Aggiungere il dominio SMTP teams come dominio del mittente consentito in Exchange Online
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
f1.keywords:
- NOCSH
description: Informazioni su come aggiungere il dominio SMTP di Microsoft teams come dominio del mittente consentito in Exchange Online per inviare notifiche ai membri del team.
appliesto:
- Microsoft Teams
ms.openlocfilehash: dc35a4797cf5b5fde001090e386f9c172c5b9458
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137266"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="625de-103">Aggiungere il dominio SMTP di Microsoft teams come dominio del mittente consentito in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="625de-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="625de-104">Se si crea un gruppo di Office 365 nella console di amministrazione o tramite Outlook, Exchange Online viene usato per inviare le notifiche di un membro del team che viene aggiunto a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="625de-104">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group.</span></span> <span data-ttu-id="625de-105">Questi messaggi vengono generati dal tenant in quanto rappresentano il nome di dominio completo SMTP predefinito per l'utente.</span><span class="sxs-lookup"><span data-stu-id="625de-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Screenshot dell'intestazione di un messaggio che mostra l'aggiunta di un utente a un gruppo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="625de-107">Teams USA anche Microsoft Exchange Online per inviare notifiche ai membri del team quando sono state aggiunte.</span><span class="sxs-lookup"><span data-stu-id="625de-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they've been added.</span></span> <span data-ttu-id="625de-108">La differenza che rappresenta il nome di dominio completo del messaggio SMTP è "@email. teams.microsoft.com" per i tenant commerciali/commerciali e "@GCC-email.teams.com" per gli inquilini pubblici e potrebbe essere intercettata tramite filtro della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="625de-108">The difference being the domain FQDN of the SMTP message is "@email.teams.microsoft.com" for Commercial/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![Screenshot dell'intestazione di un messaggio che mostra l'aggiunta di un utente a un gruppo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="625de-110">Per ottenere risultati ottimali e un'operazione ottimale, è consigliabile aggiungere il dominio SMTP di Microsoft teams all'elenco "domini mittenti consentiti" nella configurazione della posta indesiderata di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="625de-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your "allowed sender domains" list in your Exchange Online spam configuration:</span></span>

![Screenshot della sezione Consenti elenchi di impostazioni di configurazione della posta indesiderata](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
