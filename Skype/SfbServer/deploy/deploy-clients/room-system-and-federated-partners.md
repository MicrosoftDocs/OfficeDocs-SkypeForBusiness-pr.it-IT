---
title: Skype room System e partner federati di Skype for business
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
description: Leggere questo argomento per informazioni su come configurare Skype room System per i partner federati di Skype for business.
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820806"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype room System e partner federati di Skype for business
 
Leggere questo argomento per informazioni su come configurare Skype room System per i partner federati di Skype for business.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype room System e partner federati di Skype for business

Skype room System si basa sul collegamento di partecipazione alla riunione Skype for business nella convocazione di riunione del calendario. Il collegamento di join viene generalmente trovato nel corpo di una convocazione di riunione. Tuttavia, Skype room System dipende da questo collegamento per essere presente nelle proprietà MAPI del messaggio. Quando la convocazione di riunione viene inviata alle organizzazioni remote (partner federati di Skype for business), per impostazione predefinita, il sistema di Skype room dell'organizzazione remota non visualizzerà il collegamento di partecipazione alle riunioni nel calendario. In effetti, tutti gli utenti di Outlook nell'organizzazione remota non saranno in grado di partecipare alla riunione Skype for business con un clic destro dell'elemento del calendario o all'interno del promemoria della riunione. Devono aprire l'invito alla riunione e fare clic su Unisciti alla riunione Skype for business nel corpo del messaggio. 
  
La causa di questa limitazione è che Outlook e Microsoft Exchange non utilizzano un metodo speciale per il pacchetto di informazioni per l'invio di messaggi su Internet. Questo metodo, denominato TNEF (Transport Neutral Encapsulation Format), è disabilitato per impostazione predefinita per i messaggi inviati esternamente da un'organizzazione di Exchange. Affinché un collegamento di partecipazione alle riunioni venga visualizzato in un sistema di chat room Skype remoto, l'organizzazione di invio deve abilitare TNEF utilizzando il seguente comando:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Dopo che TNEF è abilitato per l'organizzazione remota, tutti i messaggi inviati tramite Internet all'organizzazione vengono inviati come allegati in formato TNEF. Con TNEF abilitato, quando una convocazione di riunione Skype for business viene inviata al partner federato di Skype for business, Skype room System sarà in grado di eseguire il rendering della riunione di Skype for business e gli utenti remoti saranno in grado di partecipare alle riunioni di Skype for business. 
