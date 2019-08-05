---
title: Risolvere i problemi di connettività con il client Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Risolvere i problemi di connettività con il client Microsoft teams, causato principalmente dal firewall o dalla connessione proxy, e come risolverlo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d208671415e44ca5ec83313d0d8af666534f2b20
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "36180485"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="542c7-103">Risolvere i problemi di connettività con il client Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="542c7-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="542c7-104">La maggior parte dei problemi individuati con il client Microsoft teams può essere ricondotta alla connettività firewall o proxy.</span><span class="sxs-lookup"><span data-stu-id="542c7-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="542c7-105">Verificare che gli URL, gli indirizzi IP e le porte necessari vengano aperti nel firewall o nel proxy ridurrà la risoluzione dei problemi non necessaria.</span><span class="sxs-lookup"><span data-stu-id="542c7-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="542c7-106">Per informazioni specifiche su URL e IPs necessari per Microsoft teams, vedere gli [URL di Office 365 e](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) l'articolo del supporto degli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="542c7-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="542c7-107">Gli scenari seguenti richiedono l'apertura di URL e porte specifici nel firewall.</span><span class="sxs-lookup"><span data-stu-id="542c7-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="542c7-108">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="542c7-108">Authentication</span></span>

-   <span data-ttu-id="542c7-109">Connettività client di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="542c7-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="542c7-110">Collaborazione</span><span class="sxs-lookup"><span data-stu-id="542c7-110">Collaboration</span></span>

-   <span data-ttu-id="542c7-111">Media</span><span class="sxs-lookup"><span data-stu-id="542c7-111">Media</span></span>

-   <span data-ttu-id="542c7-112">Servizi condivisi</span><span class="sxs-lookup"><span data-stu-id="542c7-112">Shared Services</span></span>

-   <span data-ttu-id="542c7-113">Integrazione di terze parti</span><span class="sxs-lookup"><span data-stu-id="542c7-113">Third Party Integration</span></span>

-   <span data-ttu-id="542c7-114">Interoperabilità di Skype for business</span><span class="sxs-lookup"><span data-stu-id="542c7-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="542c7-115">Interoperabilità dei client Skype for business</span><span class="sxs-lookup"><span data-stu-id="542c7-115">Skype for Business Client Interoperability</span></span>
