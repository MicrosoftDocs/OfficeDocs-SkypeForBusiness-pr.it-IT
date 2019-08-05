---
title: Richiesta di certificato (restituita)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: "La pagina di stato della richiesta di certificato online presenta informazioni importanti che derivano dalla creazione e dall'emissione di una richiesta di certificato online. Questa pagina fornisce l'identificazione personale del certificato che identifica in modo univoco il certificato. Per impostazione predefinita, la casella di controllo assegna questo certificato agli usi dei certificati Skype for Business Server è selezionata. Se si fa clic su fine, il certificato verrà assegnato automaticamente a Lync Server 2013 per gli scopi definiti durante la procedura di creazione della richiesta di certificato. Per impostazione predefinita, gli scopi che il certificato verrà assegnato sono i seguenti:"
ms.openlocfilehash: 61e6ea918fea931251470603e2db0b699234267d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195309"
---
# <a name="certificate-request-returned"></a>Richiesta di certificato (restituita)
 
La pagina di **stato della richiesta di certificato online** presenta informazioni importanti che derivano dalla creazione e dall'emissione di una richiesta di certificato online. Questa pagina fornisce l'identificazione personale del certificato che identifica in modo univoco il certificato. Per impostazione predefinita, la casella **di controllo assegna questo certificato agli usi dei certificati Skype for Business Server** è selezionata. Se si fa clic su **fine**, il certificato verrà assegnato automaticamente a Lync Server 2013 per gli scopi definiti durante la procedura di creazione della richiesta di certificato. Per impostazione predefinita, gli scopi che il certificato verrà assegnato sono i seguenti:
  
- Server predefinito per Mutual Transport Layer Security (MTLS)-connessioni ai client e ad altri server
    
- Servizi Web interni-client e connessioni server nel sito servizi Web interni per Transport Layer Security/Secure Sockets Layer (TLS/SSL)
    
- Servizi Web esterni-connessioni client e server nel sito servizi Web esterni per TLS/SSL
    
Fare clic sulla **visualizzazione dei dettagli** del certificato per visualizzare il certificato per verificare che le proprietà del certificato siano quelle desiderate e che il certificato sia pronto per essere applicato e usato nel server.
  
Fare clic su **fine** per completare il processo di richiesta di certificato online. Se è stata selezionata la casella **di controllo assegna questo certificato agli usi dei certificati Skype for Business Server**, il certificato verrà assegnato automaticamente. Se si è scelto di deselezionare questa casella di controllo, è necessario assegnare il certificato in un passaggio separato. 
  
> [!IMPORTANT]
> Se il certificato radice dell'autorità di certificazione (CA) emittente non si trova nell'archivio Autorità di certificazione radice attendibile del computer o se i certificati intermedi della CA non si trovano nell'archivio appropriato, verrà visualizzato lo stato di riepilogo, come illustrato nell'immagine seguente. Non è possibile assegnare il certificato. Per completare il processo di assegnazione del certificato, è necessario importare il certificato radice della CA emittente e gli eventuali certificati intermedi della CA e quindi assegnare il certificato facendo clic su **assegna** nella pagina della creazione guidata certificato principale.
  

