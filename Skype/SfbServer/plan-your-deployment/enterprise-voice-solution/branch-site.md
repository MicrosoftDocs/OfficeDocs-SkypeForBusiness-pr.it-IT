---
title: Trunking SIP del sito della filiale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Informazioni sul trunking SIP nei siti di filiale in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 158c1cff28ba0c21f5c995a1fe5b7dfdf2f9f150
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803256"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a>Trunking SIP del sito della filiale in Skype for Business Server
 
Informazioni sul trunking SIP nei siti di filiale in Skype for Business Server VoIP aziendale.
  
In alcuni casi potrebbe essere necessario implementare il trunking SIP distribuito in siti di succursale selezionati. Per determinare se è necessario un trunk SIP per un sito di succursale e per informazioni dettagliate sulle opzioni di topologia supportate per la distribuzione di trunk SIP nei siti di succursale, vedere [trunking SIP in Skype for Business Server](sip-trunking.md).
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a>Esempio di analisi dei requisiti trunk SIP del sito filiale

Quando si decide di distribuire un trunk SIP di un sito di succursale, è necessario eseguire un'analisi costi specifica del sito. Ad esempio, un'organizzazione con un sito centrale a Redmond, Washington e un sito di succursale di New York dovrebbe eseguire un'analisi per determinare se implementare un trunk SIP dal sito di New York a un provider di servizi locale.
  
Per determinare se un trunk SIP distribuito a New York è economicamente vantaggioso, identificare i numeri DID (Direct inwarded Dialing) che utilizzeranno il trunk SIP e analizzare il numero di chiamate effettuate da New York in aree diverse da Redmond (425). È possibile avere terminato il sito della filiale nel sito centrale. Ad esempio, il sito centrale di Redmond può ospitare i numeri DID per il sito della filiale di New York. Se il costo per l'implementazione di un trunk SIP distribuito è inferiore al costo di tali chiamate, valutare l'implementazione di un trunk SIP presso il sito della filiale di New York. 
  
## <a name="other-branch-site-sip-trunk-requirements"></a>Altri requisiti trunk SIP del sito di succursale

La scelta tra un trunk SIP di distribuzione invece di un gateway si basa sulla differenza tra gli oneri per il pedaggio pubblico Switched Telephone Network (PSTN) di ogni opzione. Se si distribuisce un trunk SIP del sito di succursale, è necessario determinare anche i requisiti di flessibilità e larghezza di banda. Se il collegamento tra il sito della filiale e il sito centrale è resiliente e dispone di larghezza di banda sufficiente, è possibile distribuire un trunk SIP o un gateway. Non è necessario distribuire un Survivable Branch Appliance nel sito della filiale. Se il collegamento tra il sito della filiale e il sito centrale non è resiliente, distribuire un Survivable Branch Appliance oppure distribuire un Survivable Branch Server con un gateway o un trunk SIP nel sito della filiale. 
  

