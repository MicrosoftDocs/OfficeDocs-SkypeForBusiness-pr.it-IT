---
title: TLS e MTLS per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: I protocolli Transport Layer Security (TLS) e Mutual Transport Layer Security (MTLS) garantiscono comunicazioni crittografate e autenticazione endpoint su Internet. Skype for Business Server usa questi due protocolli per creare la rete di server attendibili e per assicurarsi che tutte le comunicazioni tramite la rete siano crittografate. Tutte le comunicazioni SIP tra server si verificano su MTLS. Le comunicazioni SIP da client a server si verificano su TLS.
ms.openlocfilehash: fe8619dd499388472612c67ddf1801a027ed1e5d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194879"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS e MTLS per Skype for Business Server
 
I protocolli Transport Layer Security (TLS) e Mutual Transport Layer Security (MTLS) garantiscono comunicazioni crittografate e autenticazione endpoint su Internet. Skype for Business Server usa questi due protocolli per creare la rete di server attendibili e per assicurarsi che tutte le comunicazioni tramite la rete siano crittografate. Tutte le comunicazioni SIP tra server si verificano su MTLS. Le comunicazioni SIP da client a server si verificano su TLS.
  
TLS consente agli utenti, tramite il loro software client, di autenticare i server Skype for Business Server a cui si connettono. Su una connessione TLS, il client richiede un certificato valido dal server. Per essere valido, il certificato deve essere stato emesso da una CA che sia anche considerata affidabile dal client e il nome DNS del server deve corrispondere al nome DNS sul certificato. Se il certificato è valido, il client utilizza la chiave pubblica nel certificato per crittografare le chiavi di crittografia simmetriche da utilizzare per la comunicazione, quindi solo il proprietario originale del certificato può utilizzare la propria chiave privata per decrittografare il contenuto della comunicazione. La connessione risultante è affidabile e da quel momento non viene contestata da altri server o client affidabili. In questo contesto, il Secure Sockets Layer (SSL) utilizzato con i servizi web può essere associato come basato su TLS.
  
Le connessioni da server a server si basano su MTLS per l'autenticazione reciproca. Su una connessione MTLS, il server che genera un messaggio e il server che lo riceve si scambiano i certificati da una CA reciprocamente attendibile. I certificati dimostrano l'identità di ciascun server all'altro. Nelle distribuzioni di Skype for Business Server i certificati emessi dalla CA dell'organizzazione che si trovano durante il periodo di validità e non revocati dalla CA emittente vengono considerati automaticamente validi da tutti i client e i server interni, poiché tutti i membri di una società attiva Il dominio della directory considera attendibile la CA aziendale in tale dominio. Negli scenari federati la CA emittente deve essere considerata attendibile da entrambi i partner federati. Ogni partner può usare una CA diversa, se lo si desidera, purché tale CA sia attendibile anche per l'altro partner. Questo tipo di attendibilità è più semplice per gli Edge Server che hanno il certificato della CA radice del partner nelle rispettive autorità di certificazione radice attendibili oppure per l'uso di una CA di terze parti considerata attendibile da entrambe le entità.
  
TLS e MTLS contribuiscono a prevenire attacchi di intercettazione e attacchi man-in-the-middle. In un attacco man-in-the-Middle, l'aggressore reindirizza le comunicazioni tra due entità di rete tramite il computer dell'aggressore senza la conoscenza di una delle parti. La specifica TLS e Skype for Business Server dei server attendibili (solo quelli specificati in Generatore di topologia) attenuano il rischio di un attacco di tipo man-in-Middle parzialmente sul livello dell'applicazione usando la crittografia end-to-end coordinata tramite la chiave pubblica crittografia tra i due endpoint e un utente malintenzionato dovrebbe avere un certificato valido e attendibile con la chiave privata corrispondente e rilasciato al nome del servizio a cui il client comunica per decrittografare la comunicazione. In definitiva, tuttavia, devi seguire le procedure di sicurezza ottimali con l'infrastruttura di rete (in questo caso il DNS aziendale). Skype for Business Server presuppone che il server DNS sia attendibile nello stesso modo in cui i controller di dominio e i cataloghi globali sono attendibili, ma il DNS garantisce un livello di protezione dagli attacchi di Hijack DNS impedendo al server di un aggressore di rispondere eseguire correttamente una richiesta al nome contraffatto.
  

