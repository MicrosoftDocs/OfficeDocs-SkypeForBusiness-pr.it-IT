---
title: Creare le directory conferenze in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Riepilogo: informazioni su come creare le directory conferenze in Skype for Business Server.'
ms.openlocfilehash: 6a7b8d110f06b089f166fc6ff2eb35ae35632370
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828136"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Creare le directory conferenze in Skype for Business Server
 
**Riepilogo:** Informazioni su come creare le directory conferenze in Skype for Business Server.
  
Le directory conferenze mantengono un mapping tra l'ID riunione alfanumerico utilizzato da un partecipante per partecipare a una conferenza quando si utilizza Skype for business e l'ID conferenza solo numerico utilizzato da un partecipante di conferenze telefoniche con accesso esterno per partecipare alla conferenza. 
  
## <a name="create-a-conference-directory"></a>Creare una directory conferenze

La creazione di più directory conferenze garantirà che gli ID conferenza rimarranno invariati fino a quando non verrà creata una quantità significativa di conferenze. 
  
In un'organizzazione che dispone di un numero tipico di conferenze per utente, si consiglia di creare una directory conferenze per ogni 999 utenti nel pool. Usando questa linea guida, gli ID conferenza possono generalmente essere mantenuti piccoli. Tuttavia, una volta che il numero di directory conferenze (tra i pool) è superiore a 9, la lunghezza dell'ID conferenza crescerà per supportare altre conferenze.
  
Il formato di un ID conferenza è il seguente: 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Per creare una directory conferenze, utilizzare il cmdlet **New-CsConferenceDirectory** . Ad esempio, il comando seguente consente di creare una directory conferenze con identità 42, ospitata nel pool atl-cs-001.litwareinc.com:
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Per ulteriori informazioni, vedere [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
  

