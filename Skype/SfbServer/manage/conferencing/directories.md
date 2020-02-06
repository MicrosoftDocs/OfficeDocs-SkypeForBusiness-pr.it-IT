---
title: Creare directory conferenza in Skype for Business Server
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
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 'Riepilogo: informazioni su come creare directory conferenza in Skype for Business Server.'
ms.openlocfilehash: 368248f18291b049b3478f20d3de4a11d4ae6f1c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818567"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Creare directory conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come creare directory conferenza in Skype for Business Server.
  
Le directory conferenza mantengono una mappatura tra l'ID riunione alfanumerico usato da un partecipante per partecipare a una conferenza quando si usa Skype for business e l'ID conferenza numerico che viene usato da un partecipante di conferenza telefonica con accesso esterno per partecipare alla conferenza. 
  
## <a name="create-a-conference-directory"></a>Creare una directory conferenza

La creazione di più directory conferenza garantirà che gli ID conferenza rimarranno invariati finché non verrà creata una quantità significativa di conferenze. 
  
In un'organizzazione con un numero tipico di conferenze per ogni utente, è consigliabile creare una directory conferenza per ogni utenti di 999 nel pool. Usando questa linea guida, gli ID conferenza possono in genere essere mantenuti piccoli. Tuttavia, una volta che il numero di directory conferenza (tra i pool) supera 9, la lunghezza dell'ID conferenza crescerà per supportare altre conferenze.
  
Il formato di un ID conferenza è il seguente: 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Per creare una directory conferenza, usare il cmdlet **New-CsConferenceDirectory** . Ad esempio, il comando seguente crea una directory conferenza con identità 42, ospitata nel pool atl-cs-001.litwareinc.com:
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Per altre informazioni, vedere [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
  

