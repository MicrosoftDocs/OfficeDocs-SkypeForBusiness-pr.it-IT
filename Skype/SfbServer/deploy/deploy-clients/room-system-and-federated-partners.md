---
title: Partner federati Skype Room System e Skype for Business
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
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Leggere questo argomento per informazioni su come configurare Skype Room System per i partner federati Skype for Business.
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820806"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="ac3fb-103">Partner federati Skype Room System e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ac3fb-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="ac3fb-104">Leggere questo argomento per informazioni su come configurare Skype Room System per i partner federati Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ac3fb-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="ac3fb-105">Partner federati Skype Room System e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ac3fb-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="ac3fb-106">Skype Room System si basa sul collegamento Partecipa a una riunione Skype for Business nella convocazione di riunione del calendario.</span><span class="sxs-lookup"><span data-stu-id="ac3fb-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="ac3fb-107">Il collegamento di partecipazione si trova in genere nel corpo di una convocazione di riunione.</span><span class="sxs-lookup"><span data-stu-id="ac3fb-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="ac3fb-108">Tuttavia, Skype Room System dipende da questo collegamento per essere presente nelle proprietà MAPI del messaggio.</span><span class="sxs-lookup"><span data-stu-id="ac3fb-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="ac3fb-109">Quando questa convocazione di riunione viene inviata alle organizzazioni remote (partner federati Skype for Business), per impostazione predefinita il sistema skype room dell'organizzazione remota non mostrerà il collegamento di partecipazione alla riunione nel calendario.</span><span class="sxs-lookup"><span data-stu-id="ac3fb-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="ac3fb-110">Infatti, qualsiasi utente di Outlook nell'organizzazione remota non sarà in grado di partecipare alla riunione Skype for Business con un clic destro del mouse sull'elemento del calendario o dall'interno del promemoria della riunione.</span><span class="sxs-lookup"><span data-stu-id="ac3fb-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="ac3fb-111">Devono aprire l'invito alla riunione e fare clic su Partecipa alla riunione Skype for Business nel corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="ac3fb-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="ac3fb-112">Il motivo di questa limitazione è che Outlook e Microsoft Exchange non utilizzano un metodo speciale per creare un pacchetto di informazioni per l'invio di messaggi tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="ac3fb-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="ac3fb-113">Questo metodo, denominato TNEF (Transport Neutral Encapsulation Format), è disabilitato per impostazione predefinita per i messaggi inviati esternamente da un'organizzazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="ac3fb-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="ac3fb-114">Per visualizzare un collegamento di partecipazione alla riunione in un Skype Room System remoto, l'organizzazione mittente deve abilitare TNEF utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ac3fb-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="ac3fb-115">Dopo aver abilitato TNEF per l'organizzazione remota, qualsiasi messaggio inviato tramite Internet all'organizzazione viene inviato come allegato in formato TNEF.</span><span class="sxs-lookup"><span data-stu-id="ac3fb-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="ac3fb-116">Con TNEF abilitato, quando una convocazione di riunione Skype for Business viene inviata al partner federato Skype for Business, Skype Room System sarà in grado di eseguire il rendering della riunione Skype for Business e gli utenti remoti potranno partecipare alle riunioni skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ac3fb-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 
