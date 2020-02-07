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
f1.keywords:
- NOCSH
description: Informazioni su come aggiungere il dominio SMTP di Microsoft teams come dominio del mittente consentito in Exchange Online per inviare notifiche ai membri del team.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a3455c56ab3d51b83d2d5bc27d41824b6fe16ae9
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834766"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="8c0a6-103">Aggiungere il dominio SMTP di Microsoft teams come dominio del mittente consentito in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8c0a6-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="8c0a6-104">Se si crea un gruppo di Office 365 nella console di amministrazione o tramite Outlook, Exchange Online viene usato per inviare le notifiche di un membro del team che viene aggiunto a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="8c0a6-104">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group.</span></span> <span data-ttu-id="8c0a6-105">Questi messaggi vengono generati dal tenant in quanto rappresentano il nome di dominio completo SMTP predefinito per l'utente.</span><span class="sxs-lookup"><span data-stu-id="8c0a6-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Screenshot dell'intestazione di un messaggio che mostra l'aggiunta di un utente a un gruppo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="8c0a6-107">Teams USA anche Microsoft Exchange Online per inviare notifiche ai membri del team quando sono state aggiunte.</span><span class="sxs-lookup"><span data-stu-id="8c0a6-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="8c0a6-108">La differenza che rappresenta il nome di dominio completo del messaggio SMTP è "@email. teams.microsoft.com" per i tenant commerciali/commerciali e "@GCC-email.teams.com" per gli inquilini pubblici e potrebbe essere intercettata tramite filtro della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="8c0a6-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” for Commercial/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![Screenshot dell'intestazione di un messaggio che mostra l'aggiunta di un utente a un gruppo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="8c0a6-110">Per ottenere risultati ottimali e un'operazione ottimale, è consigliabile aggiungere il dominio SMTP di Microsoft teams all'elenco "domini mittenti consentiti" nella configurazione della posta indesiderata di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="8c0a6-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “allowed sender domains” list in your Exchange Online spam configuration:</span></span>

![Screenshot della sezione Consenti elenchi di impostazioni di configurazione della posta indesiderata](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
