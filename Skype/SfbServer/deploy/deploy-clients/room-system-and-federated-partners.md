---
title: Skype room System e partner federati di Skype for business
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Leggere questo argomento per informazioni su come configurare Skype room System per i partner federati di Skype for business.
ms.openlocfilehash: d5ee83857aa439791e2a31ef201e0f365dbb8408
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768719"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="e6a54-103">Skype room System e partner federati di Skype for business</span><span class="sxs-lookup"><span data-stu-id="e6a54-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="e6a54-104">Leggere questo argomento per informazioni su come configurare Skype room System per i partner federati di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="e6a54-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="e6a54-105">Skype room System e partner federati di Skype for business</span><span class="sxs-lookup"><span data-stu-id="e6a54-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="e6a54-106">Skype room System si basa sul collegamento partecipa a una riunione Skype for business nella convocazione di riunione del calendario.</span><span class="sxs-lookup"><span data-stu-id="e6a54-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="e6a54-107">Il collegamento di join si trova in genere nel corpo di una convocazione di riunione.</span><span class="sxs-lookup"><span data-stu-id="e6a54-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="e6a54-108">Tuttavia, Skype room System dipende da questo collegamento per essere presente nelle proprietà MAPI del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e6a54-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="e6a54-109">Quando la convocazione di riunione viene inviata a organizzazioni remote (partner federati di Skype for business), per impostazione predefinita il sistema di chat room Skype dell'organizzazione remota non visualizzerà il collegamento alla riunione nel calendario.</span><span class="sxs-lookup"><span data-stu-id="e6a54-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="e6a54-110">Infatti, qualsiasi utente di Outlook nell'organizzazione remota non sarà in grado di partecipare alla riunione Skype for business con un clic con il pulsante destro del mouse sull'elemento del calendario o all'interno del promemoria della riunione.</span><span class="sxs-lookup"><span data-stu-id="e6a54-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="e6a54-111">Devono aprire l'invito alla riunione e fare clic su partecipa alla riunione Skype for business nel corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e6a54-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="e6a54-112">Il motivo di questa limitazione è che Outlook e Microsoft Exchange non usano un metodo speciale per il pacchetto di informazioni per l'invio di messaggi tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="e6a54-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="e6a54-113">Questo metodo, denominato TNEF (Transport Neutral Encapsulation Format), è disabilitato per impostazione predefinita per i messaggi inviati esternamente da un'organizzazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="e6a54-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="e6a54-114">Per visualizzare un collegamento a una riunione in un sistema di chat room remota, l'organizzazione di invio deve abilitare il formato TNEF usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e6a54-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="e6a54-115">Dopo l'abilitazione di TNEF per l'organizzazione remota, qualsiasi messaggio inviato tramite Internet all'organizzazione viene inviato come allegato in formato TNEF.</span><span class="sxs-lookup"><span data-stu-id="e6a54-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="e6a54-116">Con TNEF abilitato, quando una convocazione di riunione Skype for business viene inviata al partner federato di Skype for business, Skype room System sarà in grado di eseguire il rendering della riunione di Skype for business e gli utenti remoti potranno partecipare alle riunioni di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="e6a54-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 
