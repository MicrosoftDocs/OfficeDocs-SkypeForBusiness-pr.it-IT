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
ms.localizationpriority: medium
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: Il cmdlet Search-CcLog esegue una ricerca nei registri delle chiamate in ingresso e in uscita nella directory Skype for Business Cloud Connector Edition log dell'appliance.
ms.openlocfilehash: b96e0bea7c8a7ac9d3a12c135c828440eea9fb32
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618692"
---
# <a name="search-cclog"></a>Search-CcLog
 
Il cmdlet Search-CcLog esegue una ricerca nei registri delle chiamate in ingresso e in uscita nella directory Skype for Business Cloud Connector Edition log dell'appliance.
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene eseguita una ricerca nei registri delle chiamate in ingresso e in uscita nella directory di registro dell'appliance utilizzando il nome file predefinito:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente viene eseguita una ricerca nei registri delle chiamate in ingresso e in uscita utilizzando il percorso e il nome del file specificato:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Search-CsClsLogging offre un'opzione della riga di comando per la ricerca nei file di log generati dal servizio di registrazione personalizzata.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | Obbligatorio <br/> |System.Datetime  <br/> | Data e ora di inizio della ricerca delle voci di log. Specificate nel fuso orario locale. <br/> |
|EndTime  <br/> |Obbligatorio  <br/> |System.Datetime  <br/> |Data e ora di fine della ricerca delle voci di registro. Specificate nel fuso orario locale.  <br/> |
|FileName  <br/> |Obbligatorio  <br/> |System.String  <br/> |Specifica il percorso completo del file di testo contenente i risultati della ricerca.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Search-CcLog non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

