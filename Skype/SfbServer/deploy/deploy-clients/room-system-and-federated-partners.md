---
title: Skype room System e partner federati di Skype for business
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Leggere questo argomento per informazioni su come configurare Skype room System per i partner federati di Skype for business.
ms.openlocfilehash: 8ded7ba9be24cf1ac700be0ead1c7e0c3637becd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002996"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype room System e partner federati di Skype for business
 
Leggere questo argomento per informazioni su come configurare Skype room System per i partner federati di Skype for business.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype room System e partner federati di Skype for business

Skype room System si basa sul collegamento partecipa a una riunione Skype for business nella convocazione di riunione del calendario. Il collegamento di join si trova in genere nel corpo di una convocazione di riunione. Tuttavia, Skype room System dipende da questo collegamento per essere presente nelle proprietà MAPI del messaggio. Quando la convocazione di riunione viene inviata a organizzazioni remote (partner federati di Skype for business), per impostazione predefinita il sistema di chat room Skype dell'organizzazione remota non visualizzerà il collegamento alla riunione nel calendario. Infatti, qualsiasi utente di Outlook nell'organizzazione remota non sarà in grado di partecipare alla riunione Skype for business con un clic con il pulsante destro del mouse sull'elemento del calendario o all'interno del promemoria della riunione. Devono aprire l'invito alla riunione e fare clic su partecipa alla riunione Skype for business nel corpo del messaggio. 
  
Il motivo di questa limitazione è che Outlook e Microsoft Exchange non usano un metodo speciale per il pacchetto di informazioni per l'invio di messaggi tramite Internet. Questo metodo, denominato TNEF (Transport Neutral Encapsulation Format), è disabilitato per impostazione predefinita per i messaggi inviati esternamente da un'organizzazione di Exchange. Per visualizzare un collegamento a una riunione in un sistema di chat room remota, l'organizzazione di invio deve abilitare il formato TNEF usando il comando seguente:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Dopo l'abilitazione di TNEF per l'organizzazione remota, qualsiasi messaggio inviato tramite Internet all'organizzazione viene inviato come allegato in formato TNEF. Con TNEF abilitato, quando una convocazione di riunione Skype for business viene inviata al partner federato di Skype for business, Skype room System sarà in grado di eseguire il rendering della riunione di Skype for business e gli utenti remoti potranno partecipare alle riunioni di Skype for business. 
