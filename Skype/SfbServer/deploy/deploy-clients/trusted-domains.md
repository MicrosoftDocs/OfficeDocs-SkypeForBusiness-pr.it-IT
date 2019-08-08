---
title: Skype room System Trusted Domains
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Leggere questo argomento per informazioni su come configurare i domini attendibili per Skype room System e Skype for business.
ms.openlocfilehash: 2b2aeb98e3b1b6efe585e565c1e288d635fdb26e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235015"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="c098f-103">Skype room System Trusted Domains</span><span class="sxs-lookup"><span data-stu-id="c098f-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="c098f-104">Leggere questo argomento per informazioni su come configurare i domini attendibili per Skype room System e Skype for business.</span><span class="sxs-lookup"><span data-stu-id="c098f-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="c098f-105">Domini attendibili</span><span class="sxs-lookup"><span data-stu-id="c098f-105">Trusted domains</span></span>

<span data-ttu-id="c098f-106">Il client Skype for business Visualizza una finestra di dialogo che consente agli utenti di accettare il certificato da Skype for Business Server se il dominio SIP dell'account utente che esegue l'accesso è diverso dal nome presentato nel nome dell'oggetto o dell'oggetto alternativo del certificato.</span><span class="sxs-lookup"><span data-stu-id="c098f-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="c098f-107">Se il certificato configurato per Skype for Business Server nell'organizzazione non ha un nome di dominio SIP per l'account di sistema room Skype in nome soggetto o oggetto alternativo, è necessario configurare i domini presentati nel certificato sotto i domini attendibili chiave del registro di sistema nel computer della console Skype room System.</span><span class="sxs-lookup"><span data-stu-id="c098f-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="c098f-108">Il sistema Skype room System-fornito dalla guida dell'amministratore della sala Skype spiega come e dove aggiungere domini attendibili nel client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="c098f-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="c098f-109">Supponiamo ad esempio che i certificati configurati in Skype for Business Server abbiano un nome alternativo soggetto/oggetto "CONTOSO". LOCAL "e uno dei domini SIP assegnati a un utente per l'indirizzo di accesso per Skype room System è" confrm1@contoso.net ".</span><span class="sxs-lookup"><span data-stu-id="c098f-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="c098f-110">Dato che contoso.net non è presente nel certificato, nel computer della sala di Skype è necessario configurare "contoso. local" come dominio attendibile nel registro di sistema, come spiegato nel manuale dell'amministratore della sala di Skype room System fornito dal produttore.</span><span class="sxs-lookup"><span data-stu-id="c098f-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

