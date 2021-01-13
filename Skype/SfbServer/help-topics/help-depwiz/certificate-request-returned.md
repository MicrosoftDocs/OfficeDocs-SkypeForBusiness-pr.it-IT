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
description: "Nella pagina Stato richiesta certificato online vengono presentate informazioni importanti risultanti dalla creazione e dall'emissione della richiesta di certificato online. Viene fornita l'identificazione digitale del certificato che identifica in modo univoco il certificato. Per impostazione predefinita, la casella di controllo assegna questo certificato agli utilizzi del certificato Skype for Business Server è selezionata. Se si fa clic su fine, il certificato verrà automaticamente assegnato a Lync Server 2013 per gli scopi definiti durante la procedura di creazione della richiesta di certificato. Per impostazione predefinita, gli scopi per cui verrà assegnato il certificato sono i seguenti:"
ms.openlocfilehash: 41695f37da725816be6858f0de639bca95a09438
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805146"
---
# <a name="certificate-request-returned"></a>Richiesta di certificato (restituito)
 
Nella pagina **Stato richiesta certificato online** vengono presentate informazioni importanti risultanti dalla creazione e dall'emissione della richiesta di certificato online. Viene fornita l'identificazione digitale del certificato che identifica in modo univoco il certificato. Per impostazione predefinita, la casella **di controllo assegna questo certificato agli utilizzi del certificato Skype for Business Server** è selezionata. Se si fa clic su **fine**, il certificato verrà automaticamente assegnato a Lync Server 2013 per gli scopi definiti durante la procedura di creazione della richiesta di certificato. Per impostazione predefinita, gli scopi per cui verrà assegnato il certificato sono i seguenti:
  
- Impostazione predefinita del server per MTLS (Mutual Transport Layer Security)-connessioni a client e altri server
    
- Connessioni server e client interni ai servizi Web nel sito dei servizi Web interni per TLS/SSL (Transport Layer Security/Secure Sockets Layer)
    
- Connessioni client e server esterne ai servizi Web nel sito dei servizi Web esterni per TLS/SSL
    
Fare clic sul pulsante **Visualizza dettagli certificato** per visualizzare il certificato in modo da verificare che le relative proprietà siano quelle desiderate e che il certificato sia pronto per essere applicato e utilizzato nel server.
  
Fare clic su **Fine** per completare il processo di richiesta del certificato online. Se è stata selezionata la casella **di controllo assegna questo certificato agli utilizzi del certificato Skype for Business Server**, il certificato verrà assegnato automaticamente. Se si è scelto di deselezionare questa casella di controllo, sarà necessario assegnare il certificato in un passaggio separato. 
  
> [!IMPORTANT]
> Se il certificato radice dell'autorità di certificazione (CA) emittente non si trova nell'archivio Autorità di certificazione radice attendibile del computer o se i certificati di CA intermedi non sono presenti nell'archivio appropriato, verrà visualizzato lo stato di riepilogo, come illustrato nell'immagine seguente. Non si ha pertanto la possibilità di assegnare il certificato. Per completare il processo di assegnazione del certificato, è perciò necessario importare il certificato radice della CA emittente e gli eventuali certificati della CA intermedia e quindi assegnarlo facendo clic su **Assegna** nella pagina principale della Configurazione guidata certificati.
  

