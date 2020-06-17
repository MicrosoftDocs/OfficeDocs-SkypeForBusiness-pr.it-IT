---
title: Migrazione della federazione di XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: "Le versioni precedenti fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che potrebbe essere distribuito come ruolo server separato per consentire la Federazione con le distribuzioni XMPP. La funzionalità XMPP non è più disponibile & deprecata in Skype for Business Server 2019. Se si desidera proseguire con la funzionalità XMPP, è possibile avvalersi dell'ambiente coexitence con la versione legacy (Skype for Business Server 2015/Lync Server 2013). La funzionalità XMPP è installata in due parti: come proxy XMPP che viene eseguito nel server perimetrale legacy e il gateway XMPP in esecuzione nel front end server legacy."
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752648"
---
# <a name="migrating-xmpp-federation"></a>Migrazione della federazione di XMPP

Le versioni precedenti fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che potrebbe essere distribuito come ruolo server separato per consentire la Federazione con le distribuzioni XMPP. La funzionalità XMPP non è più disponibile ed è obsoleta in Skype for Business Server 2019. Se si desidera continuare con la funzionalità XMPP, è possibile farlo in un ambiente di coesistenza con una versione legacy (Skype for Business Server 2015 o Lync Server 2013). La funzionalità XMPP è installata in due parti: come proxy XMPP che viene eseguito nel server perimetrale legacy e il gateway XMPP in esecuzione nel front end server legacy. 
  
Dal punto di vista della migrazione, gli utenti che desiderano usufruire della caratteristica XMPP devono rimanere nel server legacy e non devono essere spostati in un pool di Skype for Business Server 2019 ma continuano a usare il gateway XMPP legacy. Ciò è possibile solo quando il partner federato XMPP è configurato in Skype for Business Server 2015 o Lync Server 2013. Non è necessario eseguire la migrazione del server perimetrale legacy a Skype for Business Server 2019 se si desidera continuare con la funzionalità XMPP. Tuttavia, è possibile avere la coesistenza del server perimetrale legacy (con proxy XMPP) e del server perimetrale di Skype for business 2019.
  

    

