---
title: Includere lo sportello di sicurezza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Pianificare come includere il desk di sicurezza dell'organizzazione in una distribuzione di E9-1-1, in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 7be3533879f36c897d148194345e1496945359b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187562"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a><span data-ttu-id="e3e19-103">Includere lo sportello di sicurezza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e3e19-103">Include the security desk in Skype for Business Server</span></span>
 
<span data-ttu-id="e3e19-104">Pianificare come includere il desk di sicurezza dell'organizzazione in una distribuzione di E9-1-1, in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="e3e19-104">Planning how to include your organization's security desk in an E9-1-1 deployment, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="e3e19-105">La società può richiedere che il servizio di sicurezza venga coinvolto in una chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="e3e19-105">Your company may require the security desk to become involved in an emergency call.</span></span> <span data-ttu-id="e3e19-106">Per decidere come integrare il servizio di sicurezza nella distribuzione di E9-1-1, è necessario rispondere alle domande seguenti.</span><span class="sxs-lookup"><span data-stu-id="e3e19-106">To help decide how to integrate the Security Desk into you E9-1-1 deployment, you should answer the following questions.</span></span>
  
<span data-ttu-id="e3e19-107">**Si vuole che il desk di sicurezza venga avvisato quando è presente una chiamata di emergenza?**</span><span class="sxs-lookup"><span data-stu-id="e3e19-107">**Do you want the security desk to be notified when there is an emergency call?**</span></span>
  
<span data-ttu-id="e3e19-108">È possibile configurare i criteri di posizione in modo che Skype for Business Server invii avvisi di messaggistica istantanea agli indirizzi SIP di Skype for business di uno o più addetti alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e3e19-108">You can configure the location policy so that Skype for Business Server sends instant messaging (IM) alerts to the Skype for Business SIP addresses of one or more security personnel.</span></span> <span data-ttu-id="e3e19-109">Questi avvisi contengono il nome, il numero e la posizione della persona che effettua la chiamata di emergenza e facilitano il personale di sicurezza nell'assistenza per la situazione di emergenza.</span><span class="sxs-lookup"><span data-stu-id="e3e19-109">These alerts contain the name, number, and location of the person placing the emergency call, and facilitate security personnel in assisting with the emergency situation.</span></span>
    
<span data-ttu-id="e3e19-110">**Si vuole eseguire una conferenza sul banco di sicurezza in ogni chiamata di emergenza?**</span><span class="sxs-lookup"><span data-stu-id="e3e19-110">**Do you want to conference the security desk in on each emergency call?**</span></span>
  
<span data-ttu-id="e3e19-111">Se supportato dal provider del servizio servizi di emergenza, è possibile configurare i criteri di posizione per includere un numero di callback con ogni chiamata di emergenza.</span><span class="sxs-lookup"><span data-stu-id="e3e19-111">If supported by the emergency services service provider, you can configure the location policy to include a callback number with each emergency call.</span></span> <span data-ttu-id="e3e19-112">Questo numero viene quindi usato dal provider per organizzare il personale di sicurezza dell'organizzazione in chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="e3e19-112">This number is then used by the provider to conference your organization's security personnel into emergency calls.</span></span> <span data-ttu-id="e3e19-113">Questa conferenza può essere configurata nel criterio della posizione in modo unidirezionale (solo in ascolto) o bidirezionale (bidirezionali).</span><span class="sxs-lookup"><span data-stu-id="e3e19-113">This conferencing can be configured in the location policy to be one-way (listen-only) or two-way (bidirectional).</span></span>
    
> [!NOTE]
> <span data-ttu-id="e3e19-114">Se lo si desidera, è possibile configurare personale di emergenza diverso per ogni criterio di posizione.</span><span class="sxs-lookup"><span data-stu-id="e3e19-114">If desired, you can configure different emergency personnel for each location policy.</span></span> <span data-ttu-id="e3e19-115">In questo modo, puoi personalizzare la risposta per diverse aree all'interno della tua azienda oppure creare comportamenti diversi per le chiamate di emergenza che hanno origine dall'interno invece che all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="e3e19-115">This allows you to customize the response for different areas within your company, or create different behavior for emergency calls that originate from inside as opposed to outside the network.</span></span> <span data-ttu-id="e3e19-116">È possibile usare i gruppi di distribuzione per specificare il personale che si vuole inviare.</span><span class="sxs-lookup"><span data-stu-id="e3e19-116">You can use distribution groups to specify the personnel you want to notify.</span></span> 
  

