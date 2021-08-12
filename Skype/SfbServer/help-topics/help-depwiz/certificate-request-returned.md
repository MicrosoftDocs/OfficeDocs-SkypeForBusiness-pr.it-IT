---
title: Richiesta di certificato (Returned)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: "Nella pagina Stato richiesta certificato online vengono presentate informazioni importanti risultanti dalla creazione e dall'emissione della richiesta di certificato online. Viene fornita l'identificazione digitale del certificato che identifica in modo univoco il certificato. Per impostazione predefinita, la casella di controllo Assegna questo certificato Skype for Business Server'utilizzo del certificato è selezionata. Se si fa clic su Fine, il certificato verrà assegnato automaticamente a Lync Server 2013 per gli scopi definiti durante i passaggi di creazione della richiesta di certificato. Per impostazione predefinita, gli scopi per cui verrà assegnato il certificato sono i seguenti:"
ms.openlocfilehash: bf3dfc7e37d81a85e66fa428504b48096f3da6f4c0cffcb22685f19d0146a7d7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301752"
---
# <a name="certificate-request-returned"></a>Richiesta di certificato (restituito)
 
Nella pagina **Stato richiesta certificato online** vengono presentate informazioni importanti risultanti dalla creazione e dall'emissione della richiesta di certificato online. Viene fornita l'identificazione digitale del certificato che identifica in modo univoco il certificato. Per impostazione predefinita, la casella di controllo Assegna questo **certificato Skype for Business Server'utilizzo dei** certificati è selezionata. Se si fa **clic su Fine**, il certificato verrà assegnato automaticamente a Lync Server 2013 per gli scopi definiti durante i passaggi di creazione della richiesta di certificato. Per impostazione predefinita, gli scopi per cui verrà assegnato il certificato sono i seguenti:
  
- Server Default for Mutual Transport Layer Security (MTLS) - Connessioni a client e altri server
    
- Servizi Web interni - Connessioni client e server nel sito dei servizi Web interni per Transport Layer Security/Secure Sockets Layer (TLS/SSL)
    
- Servizi Web esterni - Connessioni client e server nel sito dei servizi Web esterni per TLS/SSL
    
Fare clic sul pulsante **Visualizza dettagli certificato** per visualizzare il certificato in modo da verificare che le relative proprietà siano quelle desiderate e che il certificato sia pronto per essere applicato e utilizzato nel server.
  
Fare clic su **Fine** per completare il processo di richiesta del certificato online. Se è stata selezionata la casella di controllo Assegna questo certificato **Skype for Business Server utilizzo** del certificato, il certificato verrà assegnato automaticamente. Se si è scelto di deselezionare questa casella di controllo, sarà necessario assegnare il certificato in un passaggio separato. 
  
> [!IMPORTANT]
> Se il certificato radice dell'Autorità di certificazione emittente non si trova nell'archivio autorità di certificazione radice attendibile del computer o se i certificati ca intermedi non si trova nell'archivio appropriato, verrà visualizzato lo stato riepilogativo, come illustrato nell'immagine seguente. Non si ha pertanto la possibilità di assegnare il certificato. Per completare il processo di assegnazione del certificato, è perciò necessario importare il certificato radice della CA emittente e gli eventuali certificati della CA intermedia e quindi assegnarlo facendo clic su **Assegna** nella pagina principale della Configurazione guidata certificati.
  

