---
title: Trunking SIP dei siti di succursale in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Informazioni sul trunking SIP nei siti di succursale in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: f8b875fca8adc1ac78c0b24cf3e53fab2ec2cd89
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813716"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Trunking SIP dei siti di succursale in Skype for Business Server
 
Informazioni sul trunking SIP nei siti di succursale in Skype for Business Server VoIP aziendale.
  
In alcuni casi, potrebbe essere necessario implementare il trunking SIP distribuito in siti di succursale selezionati. Per determinare se è necessario un trunk SIP per un sito di succursale e per informazioni dettagliate sulle opzioni di topologia supportate per la distribuzione di trunk SIP nei siti di succursale, vedere [SIP trunking in Skype for Business Server](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Analisi dei requisiti di un trunk SIP per un sito di succursale di esempio

Quando si decide di distribuire un trunk SIP di un sito di succursale, è necessario eseguire un'analisi costi specifica del sito. Ad esempio, un'organizzazione che dispone di un sito centrale a Redmond, Washington e di un sito di succursale di New York dovrebbe eseguire un'analisi per determinare se implementare un trunk SIP dal sito di New York a un provider di servizi locale.
  
Per stabilire se l'implementazione nel sito di Roma di un trunk SIP distribuito è una soluzione conveniente, identificare i numeri DID (Direct Inward Dialing) che utilizzeranno il trunk SIP e quindi analizzare il numero di chiamate effettuate dal sito di Roma ad aree diverse da Milano. È possibile disporre di una terminazione per il sito di succursale nel sito centrale. Ad esempio, il sito centrale Redmond può ospitare numeri DID per il sito di succursale di New York. Se il costo di implementazione di un trunk SIP distribuito è inferiore al costo di tali chiamate, è consigliabile implementare un trunk SIP nel sito di succursale di New York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Altri requisiti per il trunk SIP di un sito di succursale

La scelta tra la distribuzione di un trunk SIP anziché di un gateway si basa sulla differenza tra i costi delle chiamate interurbane PSTN per ogni opzione. Se si distribuisce un trunk SIP di un sito di succursale, è inoltre necessario determinare la resilienza e i requisiti di larghezza di banda. Se il collegamento tra il sito di succursale e il sito centrale è resiliente e dispone di larghezza di banda sufficiente, è possibile distribuire un trunk SIP o un gateway. Non è necessario distribuire un Survivable Branch Appliance nel sito di succursale. Se il collegamento tra il sito di succursale e il sito centrale non è resiliente, distribuire un Survivable Branch Appliance o distribuire un Survivable Branch Server con un gateway o un trunk SIP nel sito di succursale. 
  

