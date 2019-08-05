---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: Il cmdlet Update-CcServerCertificate rinnova i certificati per Skype for Business Cloud Connector Edition quando è vicino alla scadenza o è già scaduto.
ms.openlocfilehash: 34da35e607f8941da9c962386509f8a0b87ec122
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190574"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
Il cmdlet Update-CcServerCertificate rinnova i certificati per Skype for Business Cloud Connector Edition quando è vicino alla scadenza o è già scaduto. 
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente rinnova i certificati per l'archivio di gestione centrale, il Mediation Server e il server perimetrale quando i certificati sono a scadenza quasi scaduta o già scaduti:
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a>Esempio 2

Nell'esempio successivo vengono rinnovati i certificati per Mediation Server e Edge Server quando la scadenza è prossima o è già scaduta:
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

I certificati interni del connettore Cloud rilasciati a Central Management store, Mediation Server e Edge Server sono validi per due anni dopo il rilascio da parte di un servizio autorità di certificazione. Se i certificati sono a scadenza quasi scaduta o già scaduti, eseguire il cmdlet Update-CcServerCertificate per rinnovare i certificati. 
  
Questo comando sostituisce il cmdlet Renew-CcServerCertificate in Cloud Connector 2,0 e versioni successive.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
|Ruoli  <br/> |Facoltativo  <br/> |System. Array  <br/> | Matrice di ruoli del server del connettore Cloud. <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Update-CcServerCertificate non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

