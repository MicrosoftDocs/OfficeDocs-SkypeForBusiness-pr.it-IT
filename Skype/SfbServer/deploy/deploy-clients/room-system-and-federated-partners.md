---
title: Skype Room System e Skype for Business federati
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Leggere questo argomento per informazioni su come configurare Skype room per Skype for Business partner federati.
ms.openlocfilehash: 57c143559af533e1a2a8ef6577a1fe6e9f9de660
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771668"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Room System e Skype for Business federati
 
Leggere questo argomento per informazioni su come configurare Skype room per Skype for Business partner federati.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Room System e Skype for Business federati

Skype Room System si basa sul collegamento Partecipa Skype for Business riunione nella convocazione riunione del calendario. Il collegamento di partecipazione si trova in genere nel corpo di una convocazione di riunione. Tuttavia, Skype Room System dipende dal collegamento presente nelle proprietà MAPI del messaggio. Quando questa convocazione di riunione viene inviata Skype for Business organizzazioni remote (partner federati), per impostazione predefinita il Skype Room System dell'organizzazione remota non mostrerà il collegamento di partecipazione alla riunione nel calendario. Infatti, qualsiasi utente Outlook nell'organizzazione remota non sarà in grado di partecipare alla riunione di Skype for Business con un clic destro dell'elemento del calendario o all'interno del promemoria della riunione. Devono aprire l'invito alla riunione e fare clic su Partecipa Skype for Business riunione nel corpo del messaggio. 
  
Il motivo di questa limitazione è che Outlook e Microsoft Exchange non utilizzano un metodo speciale per creare un pacchetto di informazioni per l'invio di messaggi attraverso Internet. Questo metodo, denominato Transport Neutral Encapsulation Format (TNEF), è disabilitato per impostazione predefinita per i messaggi inviati esternamente da Exchange organizzazione. Per visualizzare un collegamento di partecipazione a una riunione in un Skype Room System remoto, l'organizzazione mittente deve abilitare TNEF utilizzando il comando seguente:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Dopo aver abilitato TNEF per l'organizzazione remota, qualsiasi messaggio inviato tramite Internet all'organizzazione viene inviato come allegato in formato TNEF. Con TNEF abilitato, quando una convocazione di riunione di Skype for Business viene inviata al partner federato Skype for Business, Skype Room System sarà in grado di eseguire il rendering di Join Skype for Business Meeting e gli utenti remoti potranno partecipare Skype for Business riunioni. 
