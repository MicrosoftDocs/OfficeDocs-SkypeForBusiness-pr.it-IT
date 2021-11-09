---
title: Trunking SIP del sito di succursale in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Informazioni sul trunking SIP nei siti di succursale in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: b8c1c930bb2500ca9330b14cce7fd5b341db60a9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829900"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Trunking SIP del sito di succursale in Skype for Business Server
 
Informazioni sul trunking SIP nei siti di succursale in Skype for Business Server VoIP aziendale.
  
In alcuni casi, potrebbe essere necessario implementare il trunking SIP distribuito nei siti di succursale selezionati. Per determinare se è necessario un trunk SIP per un sito di succursale e per informazioni dettagliate sulle opzioni di topologia supportate per la distribuzione dei trunk SIP nei siti di succursale, vedere [Trunking SIP in Skype for Business Server](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Analisi dei requisiti di un trunk SIP per un sito di succursale di esempio

Quando si decide di distribuire un trunk SIP del sito di succursale, è necessario eseguire un'analisi dei costi specifica del sito. Ad esempio, un'azienda con un sito centrale a Redmond, Washington e un sito di succursale a New York, deve eseguire un'analisi per determinare se implementare un trunk SIP dal sito di New York a un provider di servizi locale.
  
Per stabilire se l'implementazione nel sito di Roma di un trunk SIP distribuito è una soluzione conveniente, identificare i numeri DID (Direct Inward Dialing) che utilizzeranno il trunk SIP e quindi analizzare il numero di chiamate effettuate dal sito di Roma ad aree diverse da Milano. È possibile avere la terminazione DID per il sito di succursale nel sito centrale. Ad esempio, il sito centrale Redmond può ospitare numeri DID per il sito di succursale di New York. Se il costo dell'implementazione di un trunk SIP distribuito è inferiore al costo di tali chiamate, prendere in considerazione l'implementazione di un trunk SIP nel sito di succursale di New York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Altri requisiti per il trunk SIP di un sito di succursale

La scelta tra la distribuzione di un trunk SIP anziché di un gateway si basa sulla differenza tra i costi delle chiamate interurbane PSTN per ogni opzione. Se si distribuisce un trunk SIP del sito di succursale, è inoltre necessario determinare i requisiti di resilienza e larghezza di banda. Se il collegamento tra il sito di succursale e il sito centrale è resiliente e dispone di larghezza di banda sufficiente, è possibile distribuire un trunk SIP o un gateway. Non è necessario distribuire un Survivable Branch Appliance nel sito di succursale. Se il collegamento tra il sito di succursale e il sito centrale non è resiliente, distribuire un Survivable Branch Appliance o un Survivable Branch Server con un gateway o un trunk SIP nel sito di succursale. 
  

