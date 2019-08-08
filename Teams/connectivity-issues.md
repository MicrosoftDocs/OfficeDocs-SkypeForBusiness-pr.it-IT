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
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Risolvere i problemi di connettività con il client Microsoft teams, causato principalmente dal firewall o dalla connessione proxy, e come risolverlo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79718ebc58205cd63ab291f0985e4dd7e452be3e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236841"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="3dd6c-103">Risolvere i problemi di connettività con il client Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3dd6c-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="3dd6c-104">La maggior parte dei problemi individuati con il client Microsoft teams può essere ricondotta alla connettività firewall o proxy.</span><span class="sxs-lookup"><span data-stu-id="3dd6c-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="3dd6c-105">Verificare che gli URL, gli indirizzi IP e le porte necessari vengano aperti nel firewall o nel proxy ridurrà la risoluzione dei problemi non necessaria.</span><span class="sxs-lookup"><span data-stu-id="3dd6c-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="3dd6c-106">Per informazioni specifiche su URL e IPs necessari per Microsoft teams, vedere gli [URL di Office 365 e](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) l'articolo del supporto degli indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="3dd6c-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="3dd6c-107">Gli scenari seguenti richiedono l'apertura di URL e porte specifici nel firewall.</span><span class="sxs-lookup"><span data-stu-id="3dd6c-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="3dd6c-108">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="3dd6c-108">Authentication</span></span>

-   <span data-ttu-id="3dd6c-109">Connettività client di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3dd6c-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="3dd6c-110">Collaborazione</span><span class="sxs-lookup"><span data-stu-id="3dd6c-110">Collaboration</span></span>

-   <span data-ttu-id="3dd6c-111">Media</span><span class="sxs-lookup"><span data-stu-id="3dd6c-111">Media</span></span>

-   <span data-ttu-id="3dd6c-112">Servizi condivisi</span><span class="sxs-lookup"><span data-stu-id="3dd6c-112">Shared Services</span></span>

-   <span data-ttu-id="3dd6c-113">Integrazione di terze parti</span><span class="sxs-lookup"><span data-stu-id="3dd6c-113">Third Party Integration</span></span>

-   <span data-ttu-id="3dd6c-114">Interoperabilità di Skype for business</span><span class="sxs-lookup"><span data-stu-id="3dd6c-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="3dd6c-115">Interoperabilità dei client Skype for business</span><span class="sxs-lookup"><span data-stu-id="3dd6c-115">Skype for Business Client Interoperability</span></span>
