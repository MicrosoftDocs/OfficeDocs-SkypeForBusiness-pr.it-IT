---
title: Regole di traduzione in Skype for Business Server
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
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Informazioni sulle regole di traduzione e sulla normalizzazione delle stringhe di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: c82b925c9ef168d8a5f5e7ac730a93a53a432e2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802396"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Regole di traduzione in Skype for Business Server

Informazioni sulle regole di traduzione e sulla normalizzazione delle stringhe di chiamata in Skype for Business Server VoIP aziendale.

 Enterprise Voice richiede che tutte le stringhe di chiamata vengano normalizzate in formato E. 164 allo scopo di eseguire la ricerca di numeri inversa (RNL). Le regole di traduzione sono supportate sia per i numeri chiamati che per i numeri chiamante. Il peer Thetrunk, ovvero il gateway associato, il PBX (Private Branch Exchange) o il trunk SIP, può richiedere che i numeri siano in formato di chiamata locale. Per tradurre i numeri dal formato E. 164 a un formato di chiamata locale, è possibile definire una o più regole di traduzione per modificare l'URI della richiesta prima di instradarlo al peer trunk. Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.

Eseguendo la conversione della route in uscita sul server, è possibile ridurre i requisiti di configurazione per ogni singolo peer trunk per tradurre i numeri di telefono in un formato di chiamata locale. Quando si pianificano i gateway e il numero di gateway da associare a un cluster di Mediation Server specifico, potrebbe essere utile raggruppare i peer trunk con requisiti di selezione locali simili. In questo articolo è possibile ridurre il numero di regole di traduzione necessarie e il tempo necessario per scriverle.

> [!IMPORTANT]
> L'associazione di una o più regole di traduzione con una configurazione trunk VoIP aziendale dovrebbe essere usata come alternativa alla configurazione delle regole di traduzione nel trunk peer. Non associare regole di traduzione a una configurazione trunk VoIP aziendale se sono state configurate regole di traduzione nel peer trunk, perché le due regole potrebbero essere in conflitto.

## <a name="example-translation-rules"></a>Esempio di regole di traduzione

Gli esempi seguenti di regole di traduzione mostrano come sviluppare regole nel server per tradurre i numeri dal formato E. 164 a un formato locale per il peer trunk.

Per informazioni dettagliate su come implementare le regole di traduzione, vedere [definizione delle regole di traduzione](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) nella documentazione relativa alla distribuzione.

|**Descrizione**|**Cifre iniziali**|**Lunghezza**|**Cifre da rimuovere**|**Cifre da aggiungere**|**Modello di corrispondenza**|**Conversione**|**Esempio**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Chiamata a lunga distanza convenzionale negli Stati Uniti  <br/> (Elimina il ' +')  <br/> |+ 1  <br/> |Esattamente 12  <br/> |1  <br/> |0  <br/> |^\+(1 \ d{10}) $  <br/> |$1  <br/> |+ 14255551010 diventa 14255551010  <br/> |
|Chiamate interurbane internazionali degli Stati Uniti  <br/> (Strip out ' +' e Add 011)  <br/> |+  <br/> |Almeno 11  <br/> |1  <br/> |011  <br/> |^\+(\d{9}\d +) $  <br/> |011 $1  <br/> |+ 441235551010 diventa 011441235551010  <br/> |


