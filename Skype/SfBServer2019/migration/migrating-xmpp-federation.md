---
title: Migrazione della Federazione XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: "Le versioni precedenti fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che poteva essere distribuito come ruolo server distinto per consentire la Federazione con le distribuzioni XMPP. La funzionalità XMPP non è più disponibile & deprecata in Skype for Business Server 2019. Se si vuole continuare a usare la funzionalità XMPP, è possibile avvalersi dell'ambiente coexitence con la versione legacy (Skype for Business Server 2015/Lync Server 2013). La funzionalità XMPP viene installata in due parti: come proxy XMPP che viene eseguito nel server perimetrale legacy e il gateway XMPP che viene eseguito nel server front-end legacy."
ms.openlocfilehash: 0c7c3dbb9c7cda4f6825f66326422dced85a9c3c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238137"
---
# <a name="migrating-xmpp-federation"></a>Migrazione della Federazione XMPP

Le versioni precedenti fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che poteva essere distribuito come ruolo server distinto per consentire la Federazione con le distribuzioni XMPP. La funzionalità XMPP non è più disponibile ed è deprecata in Skype for Business Server 2019. Se si vuole continuare a usare la funzionalità XMPP, è possibile farlo in un ambiente di coesistenza con una versione legacy (Skype for Business Server 2015 o Lync Server 2013). La funzionalità XMPP viene installata in due parti: come proxy XMPP che viene eseguito nel server perimetrale legacy e il gateway XMPP che viene eseguito nel server front-end legacy. 
  
Da una prospettiva di migrazione, gli utenti che vogliono avvalersi della funzionalità XMPP devono rimanere nel server legacy e non devono essere spostati in un pool di Skype for Business Server 2019, ma continuano a usare il gateway XMPP legacy. Questo è possibile solo quando il partner federato XMPP è configurato in Skype for Business Server 2015 o Lync Server 2013. Non è consigliabile eseguire la migrazione del server perimetrale legacy a Skype for Business Server 2019 se si vuole continuare a usare la funzionalità XMPP. Tuttavia, puoi avere la coesistenza del server perimetrale legacy (con proxy XMPP) e del server Edge di Skype for business 2019.
  

    

