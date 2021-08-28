---
title: Skype Sistema sala e Skype for Business federati
ms.author: v-cichur
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
description: Leggere questo argomento per informazioni su come configurare Skype Room System per Skype for Business partner federati.
ms.openlocfilehash: 2f0a44538839fd6c722021f806bd8623f0c210ec
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620512"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Sistema sala e Skype for Business federati
 
Leggere questo argomento per informazioni su come configurare Skype Room System per Skype for Business partner federati.
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a>Skype Sistema sala e Skype for Business federati

Skype Room System si basa sul collegamento Partecipa Skype for Business riunione nella convocazione riunione del calendario. Il collegamento di partecipazione si trova in genere nel corpo di una convocazione di riunione. Tuttavia, Skype Room System dipende da questo collegamento per essere presente nelle proprietà MAPI del messaggio. Quando questa convocazione di riunione viene inviata Skype for Business organizzazioni remote (partner federati), per impostazione predefinita il Skype Room System dell'organizzazione remota non mostrerà il collegamento di partecipazione alla riunione nel calendario. Infatti, qualsiasi utente Outlook nell'organizzazione remota non sarà in grado di partecipare alla riunione di Skype for Business con un clic destro dell'elemento del calendario o all'interno del promemoria della riunione. Devono aprire l'invito alla riunione e fare clic su Partecipa Skype for Business riunione nel corpo del messaggio. 
  
Il motivo di questa limitazione è che Outlook e Microsoft Exchange non utilizzano un metodo speciale per creare pacchetti di informazioni per l'invio di messaggi su Internet. Questo metodo, definito TNEF (Transport Neutral Encapsulation Format), è disabilitato per impostazione predefinita per i messaggi inviati esternamente da un'Exchange organizzazione. Per visualizzare un collegamento di partecipazione alla riunione in un Skype Room System remoto, l'organizzazione mittente deve abilitare TNEF utilizzando il comando seguente:
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

Dopo aver abilitato TNEF per l'organizzazione remota, qualsiasi messaggio inviato tramite Internet all'organizzazione viene inviato come allegato in formato TNEF. Con TNEF abilitato, quando viene inviata una convocazione di riunione Skype for Business al partner federato Skype for Business, Skype Room System sarà in grado di eseguire il rendering di Partecipa a una riunione Skype for Business e gli utenti remoti potranno partecipare Skype for Business riunioni. 
