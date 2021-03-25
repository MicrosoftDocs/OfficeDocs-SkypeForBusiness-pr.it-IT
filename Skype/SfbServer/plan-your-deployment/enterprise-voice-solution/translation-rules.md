---
title: Regole di conversione in Skype for Business Server
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
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: Informazioni sulle regole di conversione e sulla normalizzazione delle stringhe di composizione in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: d02e4d3b84c03ee40dddbcb9b174adb66dcd6cd0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110632"
---
# <a name="translation-rules-in-skype-for-business-server"></a>Regole di conversione in Skype for Business Server

Informazioni sulle regole di conversione e sulla normalizzazione delle stringhe di composizione in Skype for Business Server VoIP aziendale.

 VoIP aziendale richiede che tutte le stringhe di composizione siano normalizzate nel formato E.164 allo scopo di eseguire la ricerca di numeri inversa (RNL). Le regole di conversione sono supportate sia per i numeri chiamati che per i numeri chiamanti. Il peer principale ,ovvero il gateway associato, il PBX (Private Branch Exchange) o il trunk SIP, potrebbe richiedere che i numeri siano in un formato di composizione locale. Per convertire i numeri dal formato E.164 a quello locale, è possibile definire una o più regole di conversione per modificare l'URI richiesta prima di eseguirne il routing al trunk peer. È possibile, ad esempio, scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.

Eseguendo la conversione delle route in uscita sul server, è possibile ridurre i requisiti di configurazione in ogni singolo trunk peer per convertire i numeri di telefono in un formato di composizione locale. Quando si pianificano i gateway e il numero di gateway da associare a un cluster Mediation Server specifico, può essere utile raggruppare i trunk peer con requisiti di composizione locali simili. In questo modo è possibile ridurre il numero di regole di conversione necessarie e il tempo necessario per scriverle.

> [!IMPORTANT]
> L'associazione di una o più regole di conversione a una VoIP aziendale trunk deve essere utilizzata come alternativa alla configurazione delle regole di conversione nel trunk peer. Non associare regole di conversione a una VoIP aziendale trunk se sono state configurate regole di conversione nel trunk peer, perché le due regole potrebbero essere in conflitto.

## <a name="example-translation-rules"></a>Esempi di regole di traduzione

Gli esempi di regole di traduzione seguenti indicano come sviluppare regole nel server per convertire numeri dal formato E.164 a un formato locale per il trunk peer.

Per informazioni dettagliate su come implementare le regole di conversione, vedere [Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules) nella documentazione relativa alla distribuzione.

|**Descrizione**|**Cifre iniziali**|**Lunghezza**|**Cifre da rimuovere**|**Cifre da aggiungere**|**Formato corrispondente**|**Translation**|**Esempio**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Composizione convenzionale di interurbane negli Stati Uniti  <br/> (rimuovere il '+')  <br/> |+1  <br/> |Esattamente 12  <br/> |1  <br/> |0  <br/> |^\+(1\d {10} ) $  <br/> |$1  <br/> |+14255551010 diventa 14255551010  <br/> |
|Composizione di interurbane internazionali negli Stati Uniti  <br/> (rimuovere '+' e aggiungere 011)  <br/> |+  <br/> |Almeno 11  <br/> |1  <br/> |011  <br/> |^\+(\d {9} \d+)$  <br/> |011$1  <br/> |+441235551010 diventa 011441235551010  <br/> |