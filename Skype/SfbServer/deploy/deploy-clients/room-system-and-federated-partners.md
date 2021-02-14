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
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Partner federati Skype Room System e Skype for Business
 
Leggere questo argomento per informazioni su come configurare Skype Room System per i partner federati Skype for Business.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Partner federati Skype Room System e Skype for Business

Skype Room System si basa sul collegamento Partecipa a una riunione Skype for Business nella convocazione di riunione del calendario. Il collegamento di partecipazione si trova in genere nel corpo di una convocazione di riunione. Tuttavia, Skype Room System dipende da questo collegamento per essere presente nelle proprietà MAPI del messaggio. Quando questa convocazione di riunione viene inviata alle organizzazioni remote (partner federati Skype for Business), per impostazione predefinita il sistema skype room dell'organizzazione remota non mostrerà il collegamento di partecipazione alla riunione nel calendario. Infatti, qualsiasi utente di Outlook nell'organizzazione remota non sarà in grado di partecipare alla riunione Skype for Business con un clic destro del mouse sull'elemento del calendario o dall'interno del promemoria della riunione. Devono aprire l'invito alla riunione e fare clic su Partecipa alla riunione Skype for Business nel corpo del messaggio. 
  
Il motivo di questa limitazione è che Outlook e Microsoft Exchange non utilizzano un metodo speciale per creare un pacchetto di informazioni per l'invio di messaggi tramite Internet. Questo metodo, denominato TNEF (Transport Neutral Encapsulation Format), è disabilitato per impostazione predefinita per i messaggi inviati esternamente da un'organizzazione di Exchange. Per visualizzare un collegamento di partecipazione alla riunione in un Skype Room System remoto, l'organizzazione mittente deve abilitare TNEF utilizzando il comando seguente:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Dopo aver abilitato TNEF per l'organizzazione remota, qualsiasi messaggio inviato tramite Internet all'organizzazione viene inviato come allegato in formato TNEF. Con TNEF abilitato, quando una convocazione di riunione Skype for Business viene inviata al partner federato Skype for Business, Skype Room System sarà in grado di eseguire il rendering della riunione Skype for Business e gli utenti remoti potranno partecipare alle riunioni skype for Business. 
