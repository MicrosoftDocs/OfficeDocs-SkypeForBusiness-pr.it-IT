---
title: Risolvere i problemi di connettività con il client Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Risolvere i problemi di connettività con il client Microsoft teams, causato principalmente dal firewall o dalla connessione proxy, e come risolverlo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7779e46fc0a1c8a282c5cde38ecac6389824a268
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "37517056"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="ee9bf-103">Risolvere i problemi di connettività con il client Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ee9bf-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="ee9bf-104">La maggior parte dei problemi individuati con il client Microsoft teams può essere ricondotta alla connettività firewall o proxy.</span><span class="sxs-lookup"><span data-stu-id="ee9bf-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="ee9bf-105">Verificare che gli URL, gli indirizzi IP e le porte necessari vengano aperti nel firewall o nel proxy ridurrà la risoluzione dei problemi non necessaria.</span><span class="sxs-lookup"><span data-stu-id="ee9bf-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="ee9bf-106">Per informazioni specifiche su URL e IPs necessari per Microsoft teams, vedere gli [URL di Office 365 e](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) l'articolo del supporto degli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="ee9bf-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="ee9bf-107">Gli scenari seguenti richiedono l'apertura di URL e porte specifici nel firewall.</span><span class="sxs-lookup"><span data-stu-id="ee9bf-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="ee9bf-108">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="ee9bf-108">Authentication</span></span>

-   <span data-ttu-id="ee9bf-109">Connettività client di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ee9bf-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="ee9bf-110">Collaborazione</span><span class="sxs-lookup"><span data-stu-id="ee9bf-110">Collaboration</span></span>

-   <span data-ttu-id="ee9bf-111">Media</span><span class="sxs-lookup"><span data-stu-id="ee9bf-111">Media</span></span>

-   <span data-ttu-id="ee9bf-112">Servizi condivisi</span><span class="sxs-lookup"><span data-stu-id="ee9bf-112">Shared Services</span></span>

-   <span data-ttu-id="ee9bf-113">Integrazione di terze parti</span><span class="sxs-lookup"><span data-stu-id="ee9bf-113">Third Party Integration</span></span>

-   <span data-ttu-id="ee9bf-114">Interoperabilità di Skype for business</span><span class="sxs-lookup"><span data-stu-id="ee9bf-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="ee9bf-115">Interoperabilità dei client Skype for business</span><span class="sxs-lookup"><span data-stu-id="ee9bf-115">Skype for Business Client Interoperability</span></span>
