---
title: Search-CcLog
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: Il cmdlet Search-CcLog esegue la ricerca nei registri delle chiamate in arrivo e in uscita nella directory del log appliance di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: a512d715f1640184217ce07e0b666954a6541fd2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824232"
---
# <a name="search-cclog"></a>Search-CcLog
 
Il cmdlet Search-CcLog esegue la ricerca nei registri delle chiamate in arrivo e in uscita nella directory del log appliance di Skype for Business Cloud Connector Edition.
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente vengono cercati i registri delle chiamate in arrivo e in uscita nella directory del log appliance usando il nome file predefinito:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente vengono cercati i registri delle chiamate in arrivo e in uscita usando il percorso e il nome del file specificati:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Search-CsClsLogging fornisce un'opzione della riga di comando per la ricerca nei file di log generati dal servizio di registrazione centralizzato.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | Obbligatorio <br/> |System. DateTime  <br/> | Data e ora di inizio per la ricerca delle voci del log. Specificato nel fuso orario locale. <br/> |
|EndTime  <br/> |Obbligatorio  <br/> |System. DateTime  <br/> |Data e ora di fine delle voci del log da cercare. Specificato nel fuso orario locale.  <br/> |
|Nome file  <br/> |Obbligatorio  <br/> |System.String  <br/> |Specifica il percorso completo del file di testo contenente i risultati della ricerca.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Search-CcLog non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

