---
title: TLS e MTLS per Skype for Business Server
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
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Transport Layer Security (TLS) e i protocolli MTLS (Mutual Transport Layer Security) forniscono comunicazioni crittografate e autenticazione endpoint su Internet. Skype for Business Server utilizza questi due protocolli per creare la rete di server attendibili e garantire che tutte le comunicazioni sulla rete siano crittografate. Tutte le comunicazioni SIP tra server avvengono tramite MTLS. Le comunicazioni SIP da client a server avvengono tramite TLS.
ms.openlocfilehash: 7acc75ef35a9fe9c3f155ca31f06ac38df371e37
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832016"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS e MTLS per Skype for Business Server
 
Transport Layer Security (TLS) e i protocolli MTLS (Mutual Transport Layer Security) forniscono comunicazioni crittografate e autenticazione endpoint su Internet. Skype for Business Server utilizza questi due protocolli per creare la rete di server attendibili e garantire che tutte le comunicazioni sulla rete siano crittografate. Tutte le comunicazioni SIP tra server avvengono tramite MTLS. Le comunicazioni SIP da client a server avvengono tramite TLS.
  
TLS consente agli utenti, tramite il software client, di autenticare i server Skype for Business Server a cui si connettono. In una connessione TLS, il client richiede al server un certificato valido. Per essere valido, il certificato deve essere stato emesso da una CA considerata attendibile anche dal client e il nome DNS del server deve corrispondere al nome DNS nel certificato. Se il certificato è valido, il client utilizza la chiave pubblica del certificato per crittografare le chiavi di crittografia simmetrica da utilizzare nella comunicazione, in modo che solo il proprietario originale del certificato possa utilizzare la sua chiave privata per decrittografare il contenuto. La connessione risultante è considerata attendibile e, da questo punto di vista, non riceve richieste di autenticazione da altri client o server trusted. In questo contesto, SSL (Secure Sockets Layer), utilizzato con i servizi Web, può essere associato come basato su TLS.
  
Le connessioni da server a server si basano su MTLS per l'autenticazione reciproca. In una connessione a MTLS, il server che ha creato un messaggio e il server che lo riceve ricevono i certificati di Exchange da una CA mutuamente attendibile. I certificati dimostrano l'identità di ogni server all'altro. Nelle distribuzioni di Skype for Business Server, i certificati emessi dall'autorità di certificazione dell'organizzazione che si trovano durante il periodo di validità e non revocati dalla CA emittente vengono considerati automaticamente validi da tutti i client e i server interni, poiché tutti i membri di un dominio di Active Directory considerano attendibile l'autorità di certificazione aziendale del dominio. Negli scenari federati, è necessario che la CA di emissione sia considerata attendibile da entrambi i partner federati. Ogni partner può utilizzare una CA diversa, se lo si desidera, purché tale CA sia anche considerata attendibile dall'altro partner. Questa relazione di trust è più semplice per i server perimetrali che dispongono del certificato CA radice del partner nelle rispettive autorità di certificazione radice attendibili o per l'utilizzo di una CA di terze parti considerata attendibile da entrambi gli interlocutori.
  
TLS e MTLS aiutano a impedire sia gli attacchi di intercettazione che di tipo man-in-the-Middle. In un attacco man-in-the-Middle, l'utente malintenzionato reindirizza le comunicazioni tra due entità di rete nel computer dell'utente malintenzionato senza la conoscenza di entrambe le parti. La specifica di TLS e Skype for Business Server dei server attendibili (solo quelli specificati in Generatore di topologie) consente di ridurre il rischio di un attacco di tipo man-in-the Middle parzialmente sul livello dell'applicazione utilizzando la crittografia end-to-end coordinata utilizzando la crittografia a chiave pubblica tra i due endpoint. e un utente malintenzionato deve disporre di un certificato valido e attendibile con la chiave privata corrispondente e rilasciato al nome del servizio al quale il client comunica per decrittografare la comunicazione. In definitiva, tuttavia, è necessario attenersi alle migliori procedure di sicurezza con l'infrastruttura di rete (in questo caso DNS aziendale). Skype for Business Server presuppone che il server DNS sia considerato attendibile nello stesso modo in cui i controller di dominio e i cataloghi globali sono considerati attendibili, ma il DNS fornisce un livello di protezione contro gli attacchi del dirottamento DNS impedendo al server di un utente malintenzionato di rispondere correttamente a una richiesta al nome falsificato.
  

