---
title: Migrazione della federazione di XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: "Le versioni precedenti fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che poteva essere distribuito come ruolo server distinto per consentire la Federazione con le distribuzioni XMPP. La funzionalità XMPP non è più disponibile & deprecata in Skype for Business Server 2019. Se si vuole continuare a usare la funzionalità XMPP, è possibile avvalersi dell'ambiente coexitence con la versione legacy (Skype for Business Server 2015/Lync Server 2013). La funzionalità XMPP viene installata in due parti: come proxy XMPP che viene eseguito nel server perimetrale legacy e il gateway XMPP che viene eseguito nel server front-end legacy."
ms.openlocfilehash: d8640d90427d5d7ae9c19a092dc10f0d299ae2be
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813434"
---
# <a name="migrating-xmpp-federation"></a>Migrazione della federazione di XMPP

Le versioni precedenti fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che poteva essere distribuito come ruolo server distinto per consentire la Federazione con le distribuzioni XMPP. La funzionalità XMPP non è più disponibile ed è deprecata in Skype for Business Server 2019. Se si vuole continuare a usare la funzionalità XMPP, è possibile farlo in un ambiente di coesistenza con una versione legacy (Skype for Business Server 2015 o Lync Server 2013). La funzionalità XMPP viene installata in due parti: come proxy XMPP che viene eseguito nel server perimetrale legacy e il gateway XMPP che viene eseguito nel server front-end legacy. 
  
Da una prospettiva di migrazione, gli utenti che vogliono avvalersi della funzionalità XMPP devono rimanere nel server legacy e non devono essere spostati in un pool di Skype for Business Server 2019, ma continuano a usare il gateway XMPP legacy. Questo è possibile solo quando il partner federato XMPP è configurato in Skype for Business Server 2015 o Lync Server 2013. Non è consigliabile eseguire la migrazione del server perimetrale legacy a Skype for Business Server 2019 se si vuole continuare a usare la funzionalità XMPP. Tuttavia, puoi avere la coesistenza del server perimetrale legacy (con proxy XMPP) e del server Edge di Skype for business 2019.
  

    

