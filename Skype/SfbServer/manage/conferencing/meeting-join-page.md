---
title: Configurare la pagina di partecipazione alla riunione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Riepilogo: informazioni su come configurare la pagina di partecipazione alla riunione in Skype for Business Server.'
ms.openlocfilehash: 7381db4983b5a2c1ec6dccf474f0b381e079e222
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818517"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="cc371-103">Configurare la pagina di partecipazione alla riunione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="cc371-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="cc371-104">**Riepilogo:** Informazioni su come configurare la pagina di partecipazione alla riunione in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc371-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="cc371-105">Quando un utente fa clic su un collegamento a una riunione in una convocazione di riunione, la pagina di partecipazione alla riunione rileva se un client Skype for business è già installato nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="cc371-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="cc371-106">Se un client è già installato, il client si apre e si unisce alla riunione.</span><span class="sxs-lookup"><span data-stu-id="cc371-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="cc371-107">Se un client non è installato, per impostazione predefinita viene aperto il client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="cc371-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="cc371-108">Configurare la pagina di partecipazione alle riunioni</span><span class="sxs-lookup"><span data-stu-id="cc371-108">Configure the meeting join page</span></span>

<span data-ttu-id="cc371-109">È possibile modificare il comportamento della pagina di partecipazione alla riunione se si vuole consentire agli utenti di partecipare a riunioni con altre versioni del client.</span><span class="sxs-lookup"><span data-stu-id="cc371-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="cc371-110">Queste opzioni di configurazione sono state rimosse dal pannello di controllo di Skype for Business Server, ma le configuri usando il cmdlet Set-CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="cc371-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="cc371-111">**Set di pagine di join di riunione-parametri di CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="cc371-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="cc371-112">**Parametro Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="cc371-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="cc371-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="cc371-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc371-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="cc371-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="cc371-115">Questo parametro è stato deprecato per l'uso con la versione locale di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc371-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="cc371-116">Se impostato su true, gli utenti che partecipano a una riunione usando un'applicazione client diversa da Skype for business avranno la possibilità di partecipare alla riunione usando l'applicazione client corrente.</span><span class="sxs-lookup"><span data-stu-id="cc371-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="cc371-117">Il valore predefinito è False.</span><span class="sxs-lookup"><span data-stu-id="cc371-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="cc371-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="cc371-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="cc371-119">Questo parametro è stato deprecato per l'uso con la versione locale di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="cc371-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="cc371-120">Se impostato su true, le opzioni alternative per partecipare a una conferenza online vengono espanse e visualizzate automaticamente agli utenti.</span><span class="sxs-lookup"><span data-stu-id="cc371-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="cc371-121">Se impostato su false (il valore predefinito), queste opzioni saranno disponibili, ma l'utente dovrà visualizzare l'elenco di opzioni.</span><span class="sxs-lookup"><span data-stu-id="cc371-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

