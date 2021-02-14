---
title: Includere il desk di sicurezza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Pianificazione di come includere il desk di sicurezza dell'organizzazione in una distribuzione E9-1-1, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 756af940eb327bc4744454e9ed9ef7a7fbfd517d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813406"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="acfae-103">Includere il desk di sicurezza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="acfae-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="acfae-104">Pianificazione di come includere il desk di sicurezza dell'organizzazione in una distribuzione E9-1-1, in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="acfae-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="acfae-p101">Nella propria azienda potrebbe essere necessario coinvolgere il desk di sicurezza in una chiamata di emergenza. Per decidere come integrare il desk di sicurezza nella distribuzione del servizio per chiamate di emergenza E9-1-1, è consigliabile rispondere alle domande riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="acfae-p101">Your company may require the security desk to become involved in an emergency call. To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="acfae-107">**Si desidera che il desk di sicurezza riceva notifica in caso di una chiamata di emergenza?**</span><span class="sxs-lookup"><span data-stu-id="acfae-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="acfae-108">È possibile configurare i criteri percorso in modo che Skype for Business Server invii avvisi di messaggistica istantanea agli indirizzi SIP di Skype for Business di uno o più membri del personale di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="acfae-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="acfae-109">Questi avvisi contengono il nome, il numero e la posizione della persona che effettua la chiamata di emergenza e consentono al personale della sicurezza di fornire più facilmente assistenza per la situazione di emergenza.</span><span class="sxs-lookup"><span data-stu-id="acfae-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="acfae-110">**Si desidera invitare il desk di sicurezza in conferenza per ogni chiamata di emergenza?**</span><span class="sxs-lookup"><span data-stu-id="acfae-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="acfae-p103">Se supportato dal provider dei servizi di emergenza, è possibile configurare i criteri di percorso in modo da includere un numero di richiamata per ogni chiamata di emergenza. Questo numero viene quindi utilizzato dal provider per invitare il personale della sicurezza dell'organizzazione a partecipare in conferenza alle chiamate di emergenza. Nei criteri di percorso, questa funzionalità di conferenza può essere configurata come unidirezionale (solo ascolto) o bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="acfae-p103">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call. This number is then used by the provider to conference your organization's security personnel into emergency calls. This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="acfae-p104">Se lo si desidera, è possibile configurare personale di emergenza diverso per i singoli criteri di percorso. In questo modo è possibile personalizzare la risposta per aree diverse nella società o creare comportamenti diversi per le chiamate di emergenza che hanno origine dall'interno anziché dall'esterno della rete. Per specificare il personale a cui inviare la notifica, è possibile usare gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="acfae-p104">If desired, you can configure different emergency personnel for each location policy. This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network. You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

