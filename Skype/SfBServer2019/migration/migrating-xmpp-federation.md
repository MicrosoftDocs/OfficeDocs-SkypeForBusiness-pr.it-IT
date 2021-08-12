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
description: "Le versioni precedenti hanno fornito un gateway XMPP (Extensible Messaging and Presence Protocol) che poteva essere distribuito come ruolo server separato per consentire la federazione con le distribuzioni XMPP. La funzionalità XMPP non è più disponibile & deprecata in Skype for Business Server 2019. Se si desidera continuare con la funzionalità XMPP, che può essere utilizzata nell'ambiente di coesistenza con la versione legacy (Skype for Business Server 2015/ Lync Server 2013). La funzionalità XMPP viene installata in due parti: come proxy XMPP eseguito nel server perimetrale legacy e come gateway XMPP eseguito nel Front End Server legacy."
ms.openlocfilehash: f1dc49a9f93d87bf2b253963cf0955594b337f9bd186c3034ac7780cb50ccddb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303430"
---
# <a name="migrating-xmpp-federation"></a>Migrazione della federazione di XMPP

Le versioni precedenti hanno fornito un gateway XMPP (Extensible Messaging and Presence Protocol) che poteva essere distribuito come ruolo server separato per consentire la federazione con le distribuzioni XMPP. La funzionalità XMPP non è più disponibile ed è deprecata Skype for Business Server 2019. Se si desidera continuare con la funzionalità XMPP, è possibile farlo in un ambiente di coesistenza con una versione legacy (Skype for Business Server 2015 o Lync Server 2013). La funzionalità XMPP viene installata in due parti: come proxy XMPP eseguito nel server perimetrale legacy e come gateway XMPP eseguito nel Front End Server legacy. 
  
Dal punto di vista della migrazione, gli utenti che desiderano utilizzare la funzionalità XMPP devono rimanere nel server legacy e non devono essere spostati in un pool di Skype for Business Server 2019, ma continuare a utilizzare il gateway XMPP legacy. Ciò è possibile solo quando il partner federato XMPP è configurato in Skype for Business Server 2015 o Lync Server 2013. Non eseguire la migrazione del server perimetrale legacy a Skype for Business Server 2019 se si desidera continuare con la funzionalità XMPP. Tuttavia, è possibile coesistenza del server perimetrale legacy (con proxy XMPP) e del server perimetrale Skype for Business 2019.
  

    

