---
title: Domini attendibili per Skype room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Leggere questo argomento per informazioni su come configurare domini attendibili per Skype room System e Skype for business.
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834116"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="0acb6-103">Domini attendibili per Skype room System</span><span class="sxs-lookup"><span data-stu-id="0acb6-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="0acb6-104">Leggere questo argomento per informazioni su come configurare domini attendibili per Skype room System e Skype for business.</span><span class="sxs-lookup"><span data-stu-id="0acb6-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="0acb6-105">Domini attendibili</span><span class="sxs-lookup"><span data-stu-id="0acb6-105">Trusted domains</span></span>

<span data-ttu-id="0acb6-106">Il client Skype for business Visualizza una finestra di dialogo che consente agli utenti di accettare il certificato dal server Skype for business se il dominio SIP dell'account utente che effettua l'accesso è diverso dal nome presentato nel nome dell'oggetto o dell'oggetto alt del certificato.</span><span class="sxs-lookup"><span data-stu-id="0acb6-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="0acb6-107">Se il certificato configurato per Skype for Business Server nell'organizzazione non dispone del nome di dominio SIP dell'account di sistema della sala Skype in subject or subject Alt Name, è necessario configurare i domini presentati nel certificato nella chiave del registro di sistema Trusted Domains sul computer della console di Skype room System.</span><span class="sxs-lookup"><span data-stu-id="0acb6-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="0acb6-108">Il manuale dell'amministratore del sistema di Skype room System ha spiegato come e dove aggiungere domini attendibili nel client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="0acb6-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="0acb6-109">Ad esempio, si supponga che i certificati configurati su Skype for Business Server dispongano del nome alternativo Subject/Subject di "CONTOSO. LOCAL "e uno dei domini SIP assegnati a un utente per l'indirizzo di accesso di Skype room System è" confrm1@contoso.net ".</span><span class="sxs-lookup"><span data-stu-id="0acb6-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="0acb6-110">Poiché contoso.net non è presente nel certificato, nel computer del sistema di chat room Skype è necessario configurare "contoso. local" come dominio attendibile nel registro di sistema, come spiegato nella Guida dell'amministratore del sistema di Skype room System fornito dal produttore.</span><span class="sxs-lookup"><span data-stu-id="0acb6-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

