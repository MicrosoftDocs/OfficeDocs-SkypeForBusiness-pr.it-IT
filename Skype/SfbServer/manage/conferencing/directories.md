---
title: Creare directory conferenze in Skype for Business Server
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
description: 'Riepilogo: informazioni su come creare directory conferenze in Skype for Business Server.'
ms.openlocfilehash: b1b1a09b00a7b0c87caff474d52e000db1e95a4a79ba8e54cb4a15a3f4ca32de
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319109"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a>Creare directory conferenze in Skype for Business Server
 
**Riepilogo:** Informazioni su come creare directory conferenze in Skype for Business Server.
  
Le directory conferenze mantengono un mapping tra l'ID riunione alfanumerico utilizzato da un partecipante per partecipare a una conferenza quando si utilizza Skype for Business e l'ID conferenza solo numerico utilizzato da un partecipante alla conferenza telefonica con accesso esterno per partecipare alla conferenza. 
  
## <a name="create-a-conference-directory"></a>Creare una directory conferenze

La creazione di più directory conferenze garantisce che gli ID conferenza rimangano brevi fino a quando non viene creata una quantità significativa di conferenze. 
  
In un'organizzazione con un numero tipico di conferenze per utente, è consigliabile creare una directory conferenze per ogni 999 utenti del pool. Utilizzando questa linea guida, gli ID conferenza in genere possono essere mantenuti piccoli. Tuttavia, una volta che il numero di directory conferenze (tra i pool) supera 9, la lunghezza dell'ID conferenza crescerà per supportare conferenze aggiuntive.
  
Il formato di un ID conferenza è il seguente: 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

Per creare una directory conferenze, utilizzare il cmdlet **New-CsConferenceDirectory.** Ad esempio, il comando seguente crea una directory conferenze con identità 42, ospitata nel pool atl-cs-001.litwareinc.com:
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

Per ulteriori informazioni, vedere [New-CsConferenceDirectory](/powershell/module/skype/new-csconferencedirectory?view=skype-ps).
